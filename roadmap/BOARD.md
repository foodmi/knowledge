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

### Icone
- [ ] Valider icone 1024x1024 PNG (pas de transparence pour iOS)
- [ ] Generer toutes les tailles via `flutter_launcher_icons`
- [ ] Verifier rendu sur fond clair et sombre

### Screenshots App Store (iOS)
- [ ] Screenshot 1 : "Scanne ton repas en 3 secondes" -- scan AI en action
- [ ] Screenshot 2 : "Resultats nutritionnels instantanes" -- macros breakdown
- [ ] Screenshot 3 : "Suis tes calories automatiquement" -- journal/dashboard
- [ ] Screenshot 4 : "Atteins tes objectifs" -- graphiques progression
- [ ] Screenshot 5 : "Coach IA personnalise" -- chat assistant
- [ ] Screenshot 6 : "30+ langues, Halal, Vegan" -- differenciateur
- [ ] Decliner en 3 tailles : 6.7" (1290x2796), 6.5" (1242x2688), 5.5" (1242x2208)
- [ ] Ajouter cadres + textes marketing (Figma ou Canva)
- [ ] Localiser les textes screenshots en FR, EN, AR, ES, DE

### Screenshots Google Play
- [ ] Memes visuels que iOS, format portrait 9:16
- [ ] Feature Graphic (1024x500) -- banniere avec logo + tagline + apercu app

### Video Preview (optionnel mais +25% conversion)
- [ ] 15-30 secondes, portrait 9:16
- [ ] Montrer le scan en action (le "wow moment")
- [ ] Sous-titres integres (son off par defaut)
- [ ] Localiser sous-titres FR + EN

### Custom Store Listings Google Play (4 CSL)
- [ ] CSL "AI Scanner" : screenshots scan, titre "Foodmi - AI Food Scanner"
- [ ] CSL "Weight Loss" : screenshots progression, titre "Foodmi - Weight Loss Tracker"
- [ ] CSL "Macro Tracker" : screenshots macros, titre "Foodmi - Macro & Protein Tracker"
- [ ] CSL "Halal" : screenshots halal, titre "Foodmi - Halal Calorie Tracker"
- [ ] Chaque CSL a ses propres screenshots et description

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
- [ ] Localiser metadata store en 5 langues min (FR, EN, AR, ES, DE)

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
