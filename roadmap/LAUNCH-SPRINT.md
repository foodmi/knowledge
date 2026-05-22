# Sprints Hebdomadaires

Chaque semaine on pioche des taches par type. On coche ce qui est fait, le reste passe a la semaine suivante.

---

## Semaine 1 -- Config + Deploy + Visuels Tier 1

### DEV
- [ ] Unifier Bundle ID iOS dans Xcode
- [ ] Resoudre iOS flavors (--dart-define au lieu de --flavor)
- [ ] Retirer AdMob du code
- [ ] Nettoyer deps pubspec inutilisees
- [ ] GitHub Secrets pour CI/CD
- [ ] Build AAB Android
- [ ] Build IPA iOS

### ADMIN
- [ ] Creer/verifier comptes Play Console + App Store Connect
- [ ] Creer app en draft sur les deux stores
- [ ] Configurer produits RevenueCat dans les 2 stores

### DESIGN
- [ ] Valider icone 1024x1024 PNG
- [ ] Generer toutes tailles icone (`flutter_launcher_icons`)
- [ ] Creer template screenshots (Figma/Canva) avec cadre device + zone texte
- [ ] Capturer les 6 ecrans dans l'app
- [ ] Screenshots Tier 1 : EN, FR, AR, ES, DE, PT (6 langues x 6 screenshots x 4 tailles = 144 images)
- [ ] Feature Graphic Google Play (1024x500)

### MARKETING
- [ ] Titre + Subtitle optimises (EN + FR)
- [ ] Keywords iOS (100 chars) EN + FR
- [ ] Description longue Google Play EN + FR (4000 chars, 80+ keywords)
- [ ] Release notes FR + EN

### WEBSITE
- [ ] Deployer sur Vercel + domaine foodmi.app
- [ ] Remplacer 13x href="#" (store badges + socials)
- [ ] Fix sitemap (retirer /login)
- [ ] Ajouter composant Comparison dans page.tsx

---

## Semaine 2 -- Upload + Review + Visuels Tier 2

### DEV
- [ ] Upload AAB sur Play Console
- [ ] Upload IPA sur App Store Connect
- [ ] Compte demo pour Apple reviewer
- [ ] HealthKit review notes

### ADMIN
- [ ] Content Rating (IARC) Google Play
- [ ] Data Safety Google Play
- [ ] App Privacy (nutrition labels) Apple
- [ ] Submit for Review (Apple)
- [ ] Start rollout (Google Play)

### DESIGN
- [ ] Screenshots Tier 2 : IT, NL, TR, RU, PL, JA, KO, ZH, ID, TH, VI (11 langues)
- [ ] Video preview 15-30s (optionnel)

### MARKETING
- [ ] Store metadata Tier 1 : titre, subtitle, keywords, descriptions pour AR, ES, DE, PT
- [ ] 4 Custom Store Listings (Scanner, Weight Loss, Macro, Halal) en EN + FR
- [ ] Recruter 50 beta testers pour reviews
- [ ] Preparer draft ProductHunt

---

## Semaine 3 -- Post-launch + Distribution + Visuels Tier 3

### DESIGN
- [ ] Screenshots Tier 3 : SV, NO, DA, FI, RO, HU, CS, SK, SL, HR, BG, EL, ET (13 langues)
- [ ] CSL screenshots par langue (Tier 1 d'abord)

### MARKETING
- [ ] Store metadata Tier 2 : IT, NL, TR, RU, PL, JA, KO, ZH, ID, TH, VI
- [ ] Lancer ProductHunt
- [ ] Premier article Medium
- [ ] 5 reponses Quora
- [ ] Premier post LinkedIn
- [ ] Posts Reddit (r/loseit, r/nutrition, r/caloriecount)
- [ ] Poster sur Indie Hackers
- [ ] Apple Search Ads ($200, longtail keywords)

### WEBSITE
- [ ] Configurer Google Analytics
- [ ] Schema.org Organization
- [ ] Configurer robots.txt pour AI crawlers

---

## Semaine 4 -- Iteration ASO + Contenu

### MARKETING
- [ ] Store metadata Tier 3 : SV, NO, DA, FI, RO, HU, CS, SK, SL, HR, BG, EL, ET
- [ ] CSL par langue Tier 2
- [ ] Analyser rankings keywords, ajuster ceux qui marchent pas
- [ ] Repondre a CHAQUE review store
- [ ] A/B test screenshots (Google Play Console)
- [ ] 2eme article Medium
- [ ] 5 nouvelles reponses Quora
- [ ] 2 posts LinkedIn

### WEBSITE
- [ ] Creer llms.txt
- [ ] Soumettre sitemap a Google Search Console + Bing
- [ ] Creer profil Crunchbase

### DEV
- [ ] Connecter scan camera reel a Genkit vision
- [ ] Connecter chat assistant a Genkit

---

## Semaine 5+ -- Scale contenu + App backend

### MARKETING
- [ ] CSL par langue Tier 3
- [ ] Iteration ASO mensuelle (3-5 keywords)
- [ ] 1 article Medium/semaine
- [ ] 5 reponses Quora/semaine
- [ ] 3 posts LinkedIn/semaine
- [ ] Preparer Meta Ads si budget

### WEBSITE
- [ ] Pages comparaison : Foodmi vs MyFitnessPal, vs CalAI
- [ ] Pages programmatiques "Calories in [food]" (top 100)

### DEV
- [ ] Dashboard : charger donnees reelles depuis Supabase
- [ ] Meal logging : creer le module
- [ ] Exercice : sauvegarder en Supabase
- [ ] Profil : charger donnees user reelles
- [ ] Settings : brancher les callbacks
- [ ] Recherche aliment : requeter Supabase au lieu de mock
