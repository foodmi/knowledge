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

Toutes les 30 langues d'un coup au lancement.

| Code | Langue | Screenshots | Store metadata |
|------|--------|-------------|----------------|
| en | Anglais | [ ] | [ ] |
| fr | Francais | [ ] | [ ] |
| ar | Arabe (RTL) | [ ] | [ ] |
| es | Espagnol | [ ] | [ ] |
| de | Allemand | [ ] | [ ] |
| pt | Portugais | [ ] | [ ] |
| it | Italien | [ ] | [ ] |
| nl | Neerlandais | [ ] | [ ] |
| tr | Turc | [ ] | [ ] |
| ru | Russe | [ ] | [ ] |
| pl | Polonais | [ ] | [ ] |
| ja | Japonais | [ ] | [ ] |
| ko | Coreen | [ ] | [ ] |
| zh | Chinois | [ ] | [ ] |
| id | Indonesien | [ ] | [ ] |
| th | Thai | [ ] | [ ] |
| vi | Vietnamien | [ ] | [ ] |
| sv | Suedois | [ ] | [ ] |
| no | Norvegien | [ ] | [ ] |
| da | Danois | [ ] | [ ] |
| fi | Finnois | [ ] | [ ] |
| ro | Roumain | [ ] | [ ] |
| hu | Hongrois | [ ] | [ ] |
| cs | Tcheque | [ ] | [ ] |
| sk | Slovaque | [ ] | [ ] |
| sl | Slovene | [ ] | [ ] |
| hr | Croate | [ ] | [ ] |
| bg | Bulgare | [ ] | [ ] |
| el | Grec | [ ] | [ ] |
| et | Estonien | [ ] | [ ] |

### Icone
- [ ] Valider icone 1024x1024 PNG (pas de transparence pour iOS)
- [ ] Generer toutes les tailles via `flutter_launcher_icons`
- [ ] Verifier rendu sur fond clair et sombre

### Screenshots (8 ecrans par langue)

Contenu des 8 screenshots ASO :

| # | Feature | Tagline EN | Description |
|---|---------|-----------|-------------|
| 1 | Scan | *Scan your meal in 3 seconds* | AI calorie tracking made easy — snap a photo, get instant results |
| 2 | Nutrition | *Analyze everything you eat* | AI breaks down every meal into calories, protein, carbs, fat |
| 3 | Chat | *Chat with your AI dietitian 24/7* | Personalized nutrition advice anytime, anywhere |
| 4 | Diet Plan | *AI creates your personalized diet plan* | Tailored to your body, goals and preferences |
| 5 | Tracker | *Track calories burned daily* | Log activities and see your real net balance |
| 6 | Water | *Track your water intake* | Stay hydrated with daily water tracking |
| 7 | Weight | *Watch the weight drop off* | Before & after photos + weight tracker to see your progress |
| 8 | Barcode | *Free barcode scanner* | Scan any product barcode for instant nutrition info |

Methode : **GPT Image 2 via Fal.ai**
- [ ] Generer les 8 screenshots EN avec GPT Image 2 (device frame iPhone 15 Pro + fond sombre #0E0E11 + mascotte piment FoodMi + tagline)
- [ ] Generer les textes marketing dans les 30 langues
- [ ] Decliner les 8 screenshots pour les 30 langues
- [ ] Exporter pour iOS : 3 tailles x 8 screenshots x 30 langues = 720 images
  - 6.7" (1290x2796)
  - 6.5" (1242x2688)
  - 5.5" (1242x2208)
- [ ] Exporter pour Google Play : 1 taille x 8 screenshots x 30 langues = 240 images
  - Portrait 9:16 (min 320px, max 3840px)

Total : **960 images** -- tout generer d'un coup pour les 30 langues

### Feature Graphic Google Play
- [ ] Banniere 1024x500 avec logo + tagline + apercu app
- [ ] 1 par langue (30 total) via GPT Image 2

### Video Preview (optionnel mais +25% conversion)
- [ ] 15-30 secondes, portrait 9:16
- [ ] Montrer le scan en action (le "wow moment")
- [ ] Sous-titres integres (son off par defaut)
- [ ] Decliner sous-titres pour les 30 langues

### Custom Store Listings Google Play (4 CSL x 30 langues)

| CSL | Titre | Focus screenshots |
|-----|-------|-------------------|
| AI Scanner | "Foodmi - AI Food Scanner" | Scan en action, resultats |
| Weight Loss | "Foodmi - Weight Loss Tracker" | Graphiques poids, objectifs |
| Macro Tracker | "Foodmi - Macro & Protein Tracker" | Macros detailles, proteines |
| Halal | "Foodmi - Halal Calorie Tracker" | Filtre Halal, 30 langues |

- [ ] Chaque CSL a ses propres screenshots et description
- [ ] Chaque CSL traduit pour les 30 langues (pas d'heritage de la listing par defaut)
- [ ] 4 CSL x 30 langues = 120 listings

### Store Metadata (titre, subtitle, keywords, description) par langue

Pour chaque langue :
- [ ] Titre (30 chars) adapte (pas juste traduit -- keywords locaux)
- [ ] Subtitle iOS (30 chars) adapte
- [ ] Keywords iOS (100 chars) -- mots-cles LOCAUX, pas traduction directe
- [ ] Description courte Google Play (80 chars) adaptee
- [ ] Description longue Google Play (4000 chars) avec keywords locaux
- [ ] Release notes

- [ ] Generer tout d'un coup pour les 30 langues

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
