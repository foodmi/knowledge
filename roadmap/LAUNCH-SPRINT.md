# Sprints Hebdomadaires

Chaque semaine on pioche des taches par type. On coche ce qui est fait, le reste passe a la semaine suivante.

---

## Semaine 1 -- Config + Deploy + Visuels 30 langues

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

### DESIGN (visuels store -- GPT Image 2)
Tout generer avec GPT Image 2 pour les 30 langues d'un coup.

**Icone**
- [ ] Valider icone 1024x1024 PNG
- [ ] Generer toutes tailles (`flutter_launcher_icons`)

**Screenshots 30 langues (GPT Image 2)**
6 ecrans a generer :
1. "Scanne ton repas en 3 secondes" -- scan AI en action
2. "Resultats nutritionnels instantanes" -- macros breakdown
3. "Suis tes calories automatiquement" -- journal/dashboard
4. "Atteins tes objectifs" -- graphiques progression
5. "Coach IA personnalise" -- chat assistant
6. "30+ langues, Halal, Vegan" -- differenciateur

Pour chaque langue, generer les textes marketing traduits puis generer les screenshots avec GPT Image 2 :

| Code | Langue | Screenshots | Metadata |
|------|--------|-------------|----------|
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

Tailles a exporter :
- iOS : 6.7" (1290x2796), 6.5" (1242x2688), 5.5" (1242x2208)
- Google Play : portrait 9:16

Total : 6 screenshots x 30 langues x 4 tailles = **720 images**

**Feature Graphic Google Play**
- [ ] Banniere 1024x500 (logo + tagline + apercu app) -- 1 par langue ou 1 universelle EN

**Video Preview (optionnel, +25% conversion)**
- [ ] 15-30 secondes portrait 9:16
- [ ] Scan en action = wow moment
- [ ] Sous-titres integres, son off par defaut
- [ ] Decliner sous-titres 30 langues

### MARKETING (store metadata 30 langues)
Generer pour les 30 langues d'un coup :
- [ ] Titre (30 chars) adapte par langue (keywords locaux, pas juste traduction)
- [ ] Subtitle iOS (30 chars) adapte par langue
- [ ] Keywords iOS (100 chars par locale) -- mots-cles locaux
- [ ] Description courte Google Play (80 chars) par langue
- [ ] Description longue Google Play (4000 chars, keywords locaux) par langue
- [ ] Release notes par langue
- [ ] 4 CSL (Scanner, Weight Loss, Macro, Halal) avec screenshots + description par langue

### WEBSITE
- [ ] Deployer sur Vercel + domaine foodmi.app
- [ ] Remplacer 13x href="#" (store badges + socials)
- [ ] Fix sitemap (retirer /login)
- [ ] Ajouter composant Comparison dans page.tsx

---

## Semaine 2 -- Upload + Review + Submit

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
- [ ] Uploader screenshots + metadata 30 langues sur les deux stores

### MARKETING
- [ ] Recruter 50 beta testers pour reviews
- [ ] Preparer draft ProductHunt

---

## Semaine 3 -- Post-launch + Distribution

### MARKETING
- [ ] Lancer ProductHunt
- [ ] Premier article Medium
- [ ] 5 reponses Quora
- [ ] Premier post LinkedIn
- [ ] Posts Reddit (r/loseit, r/nutrition, r/caloriecount)
- [ ] Poster sur Indie Hackers
- [ ] Apple Search Ads ($200, longtail keywords)
- [ ] Repondre a CHAQUE review store

### WEBSITE
- [ ] Configurer Google Analytics
- [ ] Schema.org Organization
- [ ] Configurer robots.txt pour AI crawlers

---

## Semaine 4 -- Iteration ASO + Contenu

### MARKETING
- [ ] Analyser rankings keywords par langue, ajuster ceux qui marchent pas
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
- [ ] Iteration ASO mensuelle (3-5 keywords par langue)
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
