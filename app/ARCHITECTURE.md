# App Foodmi -- Architecture Technique

Repo : [foodmi/app](https://github.com/foodmi/app)
Dernier commit reference : `f28ede8e` sur `main` (23 juin 2026).

## Stack

| Couche | Techno |
|--------|--------|
| Framework | Flutter / Dart SDK `^3.10.4` |
| Etat | Riverpod 2 |
| Navigation | `MaterialApp` + `Navigator` / `MaterialPageRoute` |
| Backend | Supabase Auth, PostgreSQL, Storage, Edge Functions |
| IA | Genkit + OpenRouter via Supabase Edge Functions |
| Paiements | RevenueCat (`purchases_flutter`, `purchases_ui_flutter`) |
| Crash / telemetry | Sentry optionnel + tables Supabase `app_events` / `app_errors` |
| Local | SharedPreferences, Hive, secure storage |
| i18n | 30 locales ARB + localizations generees |
| CI/CD | GitHub Actions + scripts locaux |

## Entrees et environnements

| Env | Entry point | Android flavor | Bundle / applicationId | App name |
|-----|-------------|----------------|------------------------|----------|
| Dev | `lib/main_dev.dart` | `dev` | `com.Foodmi.Foodmi.dev` | Foodmi Dev |
| Prod | `lib/main_production.dart` | `production` | `com.Foodmi.Foodmi` | Foodmi |

Points importants :

- Android a deux flavors Gradle : `dev` et `production`.
- iOS n'a pas de flavor Xcode separe. Le script `scripts/foodmi_app.sh` force les bons build settings via `--dart-define` et `xcodebuild`.
- Ne pas lancer `flutter run --release -t lib/main_dev.dart` directement sur iOS : utiliser le script.
- Les secrets runtime sont injectes au build ; les secrets operateur Supabase ne doivent jamais aller dans `--dart-define`.

## Structure principale

```text
lib/
  config/                 # AppConfig + env dev/prod
  core/                   # Theme, widgets, utils, secure storage
  data/repositories/      # Repositories Supabase
  features/
    assistant/            # Hub assistant, chat, contenus generes
    auth/                 # Login, reset password, OAuth
    dashboard/            # Journal, calories, eau, glucose, poids
    exercise/             # Exercise logging et analyses IA
    food/                 # Recherche/detail aliments
    health/               # Health hub, tension, cholesterol, vital scan
    journal/              # Recherche aliment et journal repas
    navigation/           # Bottom navigation + scan action
    notifications/        # UI notifications
    onboarding/           # Onboarding conversationnel + paywall
    profile/              # Profil, settings, allergies, conditions sante
    progress/             # Poids, photos progres, comparaisons
    scan/                 # Scan repas, menu/table analysis, resultats
    settings/             # Langue
    splash/               # Splash
  l10n/                   # ARB + localizations
  models/                 # Modeles partages
  providers/              # Riverpod providers
  services/               # IA, Supabase, sync, health, RevenueCat, telemetry
  main.dart
  main_dev.dart
  main_production.dart
```

## Backend Supabase

Tables et domaines principaux :

- profils, preferences utilisateur, onboarding
- meals, foods, recipes, meal categories
- exercises, weight entries, progress photos
- blood glucose, blood pressure, cholesterol, vital/health data
- assistant conversations, generated contents, suggestions
- telemetry `app_events` et `app_errors`

Edge Functions importantes :

- `ai-proxy` / `openrouter-proxy` : appels IA server-side
- generateurs de contenus, tips, menus, emails
- `delete-account` : suppression compte / RGPD

Storage :

- images repas
- progress photos
- food icons
- avatars

## IA

Flux general :

```text
Flutter services -> GenkitService / services IA -> Supabase Edge Function -> OpenRouter
```

Services IA importants :

- `ai_vision_service.dart` : scan repas / menus / analyse image
- `assistant_service.dart` : conversations assistant
- `exercise_analysis_service.dart` : analyse d'exercice
- `health_report_generator_service.dart` : rapport sante
- `progress_analysis_service.dart` : analyse progression
- `system_prompt_builder.dart` : prompts systeme durcis
- schemas `lib/services/schemas/*` pour sorties structurees

## Android

- `applicationId` production : `com.Foodmi.Foodmi`
- namespace Kotlin : `com.foodmi.foodmi`
- `minSdk = 26` (Android 8.0+)
- release signe via `android/keystore.properties`
- permissions sensibles : camera, micro, images, activity recognition, Health Connect
- Play Store pas pret tant que la matrice multi-device n'est pas passee.

Voir `app/PLAY_STORE_READINESS.md`.

## iOS

- bundle production : `com.Foodmi.Foodmi`
- bundle dev : `com.Foodmi.Foodmi.dev`
- HealthKit actif avec entitlements simplifies
- build iOS dev release valide localement sur iPhone 16 Pro
- sortie publique : priorite App Store mainnet, avec RevenueCat Apple et secrets prod

## Notes release

- Dev = premium auto / no paywall effectif pour faciliter les tests.
- Prod = RevenueCat actif ; ne pas soumettre sans produit Apple/Google configure.
- Avant mainnet iOS : verifier `REQUIRE_AI_ENTITLEMENT=true` cote Supabase prod si l'acces IA doit etre reserve aux abonnes.
- Avant Play Store : tester telephones Android, tablettes, pliables, orientations, permissions et Health Connect.
