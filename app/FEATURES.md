# App FoodMi -- Features (etat reel du code)

## Implemente et fonctionnel

### Auth
- Email sign-in/sign-up via Supabase
- Google Sign-In (ID token)
- Apple OAuth
- Password reset
- Session refresh
- Profil utilisateur CRUD (table `profiles`)

### Onboarding
- Flow conversationnel en 40+ etapes (1800+ lignes)
- Collecte : genre, objectif, date naissance, taille/poids, preferences alimentaires, allergies, conditions sante, morphologie, motivation, obstacles
- Persistance progress via SharedPreferences (reprise si interruption)
- Tracking analytics vers Supabase (`onboarding_analytics`)
- Paywall integre, creation compte, permission camera, confirmation privacy

### Monetisation (RevenueCat)
- Init, login/logout, purchase, restore
- Detection trial, dates expiration
- Provider `isPremiumProvider`
- Trial 3 jours, abonnement mensuel/annuel
- Pas de pubs

### Backend IA (Genkit)
- Service configure avec OpenAI plugin
- Route via Supabase Edge Function (`ai-proxy`)
- Modeles exposes : vision, chat, reasoning, content, text
- Auto-refresh sur changement token auth

## UI complete mais donnees en dur (pas connecte au backend)

### Dashboard
- Anneau calories, selecteur date, apercu macros, repas du jour, recompense, defis
- UI polie avec glassmorphism + animations
- **Donnees hardcodees** (calories=1934, goal=2046, repas mock)

### Recherche / Detail aliment
- Ecran recherche avec barre, chips categories, liste aliments
- Detail avec macros, infos nutritionnelles, conseil IA
- **10 fruits hardcodes** (`food_mock_data.dart`), pas de requete Supabase

### Ajout aliment
- Quick add macros, recherche recents, ajout manuel
- **Pas de persistence**

### Exercice
- Liste 3 types (course, muscu, manuel)
- Formulaire : intensite, duree, distance, notes
- **Affiche un SnackBar et pop, rien n'est sauvegarde**

### Profil
- User card, stats, poids, IMC, photos progres
- **Tout hardcode** (username "bizdebusiness", stats fixes)

### Settings
- Langue, notifs, apparence, infos perso, objectifs, unites, about, privacy, terms, aide, logout
- **Tous les `onTap` sont vides `() {}`**

### Progres
- Selecteur periode (semaine/mois/annee), graphique poids (fl_chart), cards resume
- Le toggle semaine/mois/annee fonctionne
- **Donnees hardcodees** (arrays statiques)

### Assistant
- Hub avec 7 capacites (meal plan, exercices, conseils, revue hebdo, analyse progres, recettes, programme)
- Navigation vers ecran chat

### Chat
- Input texte, bulles messages, scroll
- **Reponse automatique hardcodee apres 800ms** -- pas connecte a Genkit/IA
- Messages pas persistes

### Scan
- 3 ecrans : scan, analyse (progress simule 0-100%), resultat (mock)
- **Pas de camera, pas d'IA** -- le scan est simule, les resultats sont hardcodes
- `camera` et `mobile_scanner` dans pubspec mais pas utilises

## N'existe pas du tout

| Feature | Etat |
|---------|------|
| Scan camera reel | Pas implemente (simule) |
| Scan frigo | N'existe pas |
| Scan ticket de caisse | N'existe pas |
| Scan barcode | Dep dans pubspec, zero code |
| Gamification (badges, XP, streaks) | Dossier vide |
| Sante (glycemie, tension) | Dossier vide |
| Meal logging / journal repas | Dossier vide |
| Offline / sync (Hive) | Deps dans pubspec, zero code |
| Notifications push | Deps dans pubspec, zero code |
| HealthKit / Google Fit | Dep dans pubspec, zero code |
| Speech to text | Dep dans pubspec, zero code |
| Text to speech | Dep dans pubspec, zero code |
| Export PDF | Dep dans pubspec, zero code |
| Partage social | Dep dans pubspec, zero code |

## Deps pubspec inutilisees (a nettoyer)

`hive`, `hive_flutter`, `mobile_scanner`, `health`, `speech_to_text`, `flutter_tts`, `pdf`, `share_plus`, `google_mobile_ads`, `flutter_local_notifications`, `firebase_messaging`, `connectivity_plus`
