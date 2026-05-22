# App FoodMi -- Architecture Technique

Repo : [foodmi/app](https://github.com/foodmi/app)

## Stack

| Couche | Techno |
|--------|--------|
| Framework | Flutter 3.24+ / Dart 3.10.4 |
| State | Riverpod 2 (annotation + codegen) |
| Routing | go_router 14 |
| Backend | Supabase (PostgreSQL, Auth, Storage, Edge Functions) |
| IA | OpenRouter API (Claude Sonnet 4, GPT-5.3) + Genkit + genkit_openai |
| Auth | Supabase Auth + Google Sign-In |
| Monetisation | RevenueCat (purchases_flutter) |
| Stockage local | Hive (chiffre) + SharedPreferences |
| CI/CD | GitHub Actions (3 workflows: android, ios, test) |
| i18n | 30 langues via ARB files |

## Architecture : Clean Architecture + Feature-First

```
lib/
├── app.dart                    # MaterialApp + ProviderScope + Router
├── main.dart                   # Entry point (dev)
├── main_production.dart        # Entry point (prod)
├── config/                     # Env switching (dev/staging/prod)
├── core/                       # Transversal : theme, router, utils, widgets
├── features/                   # Modules fonctionnels (voir FEATURES.md)
├── services/                   # Services transversaux (IA, sync, notifs, IAP)
├── data/                       # Supabase client
└── l10n/                       # 30 fichiers ARB
```

## Design System

- **Theme** : dark mode uniquement
- **Primary** : `#E84520` (orange)
- **Background** : `#0E0E11`
- **Surface** : `#1A1A2E`
- **Font** : Google Fonts (Inter)
- **Macros** : Calories=#E84520, Proteines=#E74C3C, Glucides=#5CB85C, Lipides=#FFB347
- **Mascotte** : robot FoodMi orange, present sur dashboard/scan/assistant

## Navigation (go_router + ShellRoute)

```
/ -> redirect /onboarding ou /home
├── /onboarding        # Flow 41 etapes
├── /auth              # login, signup, forgot-password
└── /home (Shell)      # 4 tabs + FAB central
    ├── /dashboard
    ├── /progress
    ├── /assistant -> /chat/:id
    ├── /profile -> /settings
    ├── /scan -> /analysis -> /result
    ├── /food -> /search, /detail/:id, /add
    └── /exercise -> /list, /form/:type
```

## Supabase Backend

### Tables principales
profiles, meals, exercises, weight_entries, blood_glucose_entries, blood_pressure_entries, water_intake, ai_conversations, ai_messages, ai_suggestions, foods, recipes

Toutes avec RLS active.

### Edge Functions
- `ai-proxy` -- Route IA (cle API server-side)
- `openrouter-proxy` -- Proxy OpenRouter
- `daily-content-generator` -- Tips quotidiens
- `translate-foods` / `translate-ingredients` -- Traductions
- `scheduled-notifications` -- Notifs cron
- `send-welcome-email` / `send-menu-email` / `send-subscription-email` -- Emails
- `delete-account` -- Suppression RGPD

### Storage Buckets
- `meal-images` (prive) -- Photos repas
- `progress-photos` (prive) -- Photos corporelles
- `food-icons` (public) -- Icones categories
- `avatars` (prive) -- Photos profil

## Environments

| Env | Bundle ID | Supabase |
|-----|-----------|----------|
| Dev | `com.Foodmi.Foodmi.dev` | Projet dev (eu-west-3) |
| Prod | `com.Foodmi.Foodmi` | Projet prod (eu-west-3) |

Dev = auto-premium, no ads, no paywall.

## IA

```
Flutter -> GenkitService -> Supabase Edge Function (ai-proxy) -> OpenRouter
```

### Modeles
- Vision : scan alimentaire, analyse frigo, tickets de caisse
- Chat : assistant nutritionnel
- Reasoning : rapports sante

### Temperatures
- Chat : 0.7
- Analyse : 0.3
- Deterministe : 0.1
