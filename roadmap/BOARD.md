# Board -- Kanban FoodMi

## FAIT

- [x] Auth Supabase (email, Google, Apple)
- [x] Onboarding conversationnel 40+ etapes
- [x] RevenueCat (trial 3 jours, abonnement mensuel/annuel)
- [x] Backend Supabase (23 migrations, edge functions, RLS)
- [x] Wiring Genkit IA (ai-proxy edge function, modeles vision/chat/reasoning)
- [x] Website marketing Next.js (13 sections, blog, privacy, terms, 5 langues)
- [x] CI/CD GitHub Actions (build android, build ios, tests)
- [x] i18n app 30 langues (fichiers ARB)
- [x] Support RTL arabe
- [x] UI dashboard, recherche aliment, exercice, profil, settings, progres, chat, scan (donnees en dur)

## EN COURS

- [ ] Deployer website sur Vercel + domaine foodmi.app
- [ ] Fix iOS Bundle ID (`com.adamchafqani.scanflow` -> `com.FoodMi.FoodMi`)
- [ ] Fix iOS flavors (retirer `--flavor`, utiliser `--dart-define`)
- [ ] Retirer AdMob du code (pas de pubs)
- [ ] Remplacer 13x `href="#"` dans le site (store badges + socials)

## TODO -- Visuels Store (Priorite 1)

### Langues de l'app (30 langues dans le repo)

| Code | Langue | Tier | Screenshots | Store metadata |
|------|--------|------|-------------|----------------|
| en | Anglais | 1 | [ ] | [ ] |
| fr | Francais | 1 | [ ] | [ ] |
| ar | Arabe (RTL) | 1 | [ ] | [ ] |
| es | Espagnol | 1 | [ ] | [ ] |
| de | Allemand | 1 | [ ] | [ ] |
| pt | Portugais | 1 | [ ] | [ ] |
| it | Italien | 2 | [ ] | [ ] |
| nl | Neerlandais | 2 | [ ] | [ ] |
| tr | Turc | 2 | [ ] | [ ] |
| ru | Russe | 2 | [ ] | [ ] |
| pl | Polonais | 2 | [ ] | [ ] |
| ja | Japonais | 2 | [ ] | [ ] |
| ko | Coreen | 2 | [ ] | [ ] |
| zh | Chinois | 2 | [ ] | [ ] |
| id | Indonesien | 2 | [ ] | [ ] |
| th | Thai | 2 | [ ] | [ ] |
| vi | Vietnamien | 2 | [ ] | [ ] |
| sv | Suedois | 3 | [ ] | [ ] |
| no | Norvegien | 3 | [ ] | [ ] |
| da | Danois | 3 | [ ] | [ ] |
| fi | Finnois | 3 | [ ] | [ ] |
| ro | Roumain | 3 | [ ] | [ ] |
| hu | Hongrois | 3 | [ ] | [ ] |
| cs | Tcheque | 3 | [ ] | [ ] |
| sk | Slovaque | 3 | [ ] | [ ] |
| sl | Slovene | 3 | [ ] | [ ] |
| hr | Croate | 3 | [ ] | [ ] |
| bg | Bulgare | 3 | [ ] | [ ] |
| el | Grec | 3 | [ ] | [ ] |
| et | Estonien | 3 | [ ] | [ ] |

**Tier 1** : faire en premier (marches prioritaires)
**Tier 2** : faire semaine 2-3 (gros marches ou fort pouvoir d'achat)
**Tier 3** : faire mois 2+ (volume supplementaire)

### Icone
- [ ] Valider icone 1024x1024 PNG (pas de transparence pour iOS)
- [ ] Generer toutes les tailles via `flutter_launcher_icons`
- [ ] Verifier rendu sur fond clair et sombre

### Screenshots (6 ecrans par langue)

Contenu des 6 screenshots :
1. "Scanne ton repas en 3 secondes" -- scan AI en action
2. "Resultats nutritionnels instantanes" -- macros breakdown
3. "Suis tes calories automatiquement" -- journal/dashboard
4. "Atteins tes objectifs" -- graphiques progression
5. "Coach IA personnalise" -- chat assistant
6. "30+ langues, Halal, Vegan" -- differenciateur

Methode :
- [ ] Creer template Figma/Canva avec cadre device + zone texte
- [ ] Capturer les 6 ecrans dans l'app
- [ ] Generer les textes marketing dans les 30 langues
- [ ] Injecter les textes traduits dans le template (script ou manuellement)
- [ ] Exporter pour iOS : 3 tailles x 6 screenshots x 30 langues = 540 images
  - 6.7" (1290x2796)
  - 6.5" (1242x2688)
  - 5.5" (1242x2208)
- [ ] Exporter pour Google Play : 1 taille x 6 screenshots x 30 langues = 180 images
  - Portrait 9:16 (min 320px, max 3840px)

Total : **720 images** (automatiser avec Figma + script de texte)

Ordre de production :
1. [ ] Tier 1 (6 langues) -- 108 images iOS + 36 Play = **144 images**
2. [ ] Tier 2 (12 langues) -- 216 images iOS + 72 Play = **288 images**
3. [ ] Tier 3 (12 langues) -- 216 images iOS + 72 Play = **288 images**

### Feature Graphic Google Play
- [ ] Banniere 1024x500 avec logo + tagline + apercu app
- [ ] 1 par langue (30 total) ou 1 universel en anglais

### Video Preview (optionnel mais +25% conversion)
- [ ] 15-30 secondes, portrait 9:16
- [ ] Montrer le scan en action (le "wow moment")
- [ ] Sous-titres integres (son off par defaut)
- [ ] Version FR + EN minimum
- [ ] Decliner sous-titres pour les 30 langues si possible

### Custom Store Listings Google Play (4 CSL x 30 langues)

| CSL | Titre | Focus screenshots |
|-----|-------|-------------------|
| AI Scanner | "Foodmi - AI Food Scanner" | Scan en action, resultats |
| Weight Loss | "Foodmi - Weight Loss Tracker" | Graphiques poids, objectifs |
| Macro Tracker | "Foodmi - Macro & Protein Tracker" | Macros detailles, proteines |
| Halal | "Foodmi - Halal Calorie Tracker" | Filtre Halal, 30 langues |

- [ ] Chaque CSL a ses propres screenshots et description
- [ ] Chaque CSL doit etre traduit separement (pas d'heritage de la listing par defaut)
- [ ] Tier 1 d'abord (6 langues x 4 CSL = 24 listings)
- [ ] Tier 2-3 ensuite

### Store Metadata (titre, subtitle, keywords, description) par langue

Pour chaque langue :
- [ ] Titre (30 chars) adapte (pas juste traduit -- keywords locaux)
- [ ] Subtitle iOS (30 chars) adapte
- [ ] Keywords iOS (100 chars) -- mots-cles LOCAUX, pas traduction directe
- [ ] Description courte Google Play (80 chars) adaptee
- [ ] Description longue Google Play (4000 chars) avec keywords locaux
- [ ] Release notes

Ordre :
1. [ ] Tier 1 : EN, FR, AR, ES, DE, PT
2. [ ] Tier 2 : IT, NL, TR, RU, PL, JA, KO, ZH, ID, TH, VI
3. [ ] Tier 3 : SV, NO, DA, FI, RO, HU, CS, SK, SL, HR, BG, EL, ET

## TODO -- Config & Blockers (Priorite 1)

- [ ] Unifier Bundle ID iOS dans Xcode
- [ ] Regenerer provisioning profiles
- [ ] Creer comptes Google Play Console + App Store Connect (si pas fait)
- [ ] Creer app en draft sur les deux stores
- [ ] Deployer site web (Vercel + DNS)
- [ ] Nettoyer les deps pubspec inutilisees (hive, mobile_scanner, health, speech_to_text, flutter_tts, pdf, share_plus, google_mobile_ads, flutter_local_notifications, firebase_messaging, connectivity_plus)

## TODO -- ASO & Store Metadata (Priorite 1)

- [ ] Titre : "Foodmi - AI Calorie Tracker" (27 chars)
- [ ] Subtitle iOS : "Food Scanner & Macro Counter" (28 chars)
- [ ] Keywords iOS (100 chars) : pas repeter titre/subtitle
- [ ] Description longue Google Play (4000 chars, 80+ keywords)
- [ ] Localiser metadata store dans les 30 langues (voir section Visuels Store)

## TODO -- Build & Upload (Priorite 1)

- [ ] Build AAB Android
- [ ] Build IPA iOS
- [ ] Upload sur Play Console
- [ ] Upload sur App Store Connect
- [ ] Configurer produits RevenueCat dans les 2 stores

## TODO -- Review Prep (Priorite 1)

- [ ] Content Rating (IARC) Google Play
- [ ] Data Safety Google Play
- [ ] App Privacy (nutrition labels) Apple
- [ ] Notes for Review HealthKit
- [ ] Compte demo pour Apple reviewer
- [ ] Release notes FR + EN

## TODO -- Submit (Priorite 1)

- [ ] Submit for Review (Apple)
- [ ] Start rollout (Google Play)

## TODO -- Post-Launch (Priorite 2)

- [ ] Recruter 50 beta testers pour reviews J+0
- [ ] Activer Apple Search Ads ($200, longtail keywords)
- [ ] Lancer ProductHunt
- [ ] Premier article Medium
- [ ] 5 reponses Quora
- [ ] Premier post LinkedIn
- [ ] Posts Reddit (r/loseit, r/nutrition, r/caloriecount)
- [ ] Poster sur Indie Hackers

## TODO -- SEO & Marketing (Priorite 3)

- [ ] Configurer Google Analytics sur le site
- [ ] Configurer robots.txt pour AI crawlers (GPTBot, ClaudeBot, etc.)
- [ ] Creer llms.txt
- [ ] Pages comparaison : Foodmi vs MyFitnessPal, vs CalAI
- [ ] Pages programmatiques "Calories in [food]" (top 100 aliments)
- [ ] Soumettre sitemap a Google Search Console + Bing
- [ ] Creer profil Crunchbase
- [ ] Schema.org Organization sur le site

## TODO -- App : connecter au backend (Priorite 2)

- [ ] Scan : brancher la camera + envoyer image a Genkit vision
- [ ] Dashboard : charger donnees reelles depuis Supabase
- [ ] Chat assistant : connecter a Genkit au lieu de la reponse hardcodee
- [ ] Meal logging : creer le module (dossier vide actuellement)
- [ ] Exercice : sauvegarder en Supabase au lieu de juste SnackBar
- [ ] Profil : charger donnees user reelles
- [ ] Settings : brancher les callbacks (tout est `() {}`)
- [ ] Recherche aliment : requeter Supabase au lieu de mock_data
