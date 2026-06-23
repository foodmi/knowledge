# App Foodmi -- Features (etat reel)

Reference repo : `foodmi/app` commit `f28ede8e` (23 juin 2026).

## Statut global

- iOS : candidat mainnet en preparation. Le build dev release a ete installe sur iPhone 16 Pro ; la soumission publique doit maintenant passer par la config production.
- Android : pas pret Play Store. Les features existent en grande partie, mais la qualif Android multi-supports n'est pas faite.
- Produit : premium-first via RevenueCat, pas de pubs.

## Fonctionnel / code present

### Auth et compte

- Supabase Auth : email, login, reset password.
- Google Sign-In.
- Apple OAuth cote app.
- Profil utilisateur, preferences, allergies, conditions sante, categories repas.
- Suppression compte via backend dedie.
- Secure storage helper et nettoyage session.

### Onboarding

- Flow conversationnel long avec collecte objectif, morphologie, habitudes, motivation, obstacles, preferences, allergies, conditions sante.
- Persistance de progression onboarding.
- Paywall integre.
- Permissions camera et Health Connect / Apple Health dans le flow.
- Tests de persistance et paywall presents.

### Scan et analyse alimentaire

- Ecran scan avec camera / image picker.
- Analyse de repas via service IA vision.
- Analyse menu/table avec ecrans dedies.
- Resultats editables, recalcul portions/macros, sauvegarde repas.
- Validation photo et schemas de sortie IA.
- Risque a tester : latence reseau, erreurs IA, permissions camera/images sur Android 13+, reprise apres refus permission.

### Journal, repas et nutrition

- Repositories repas et poids.
- `meal_service`, `food_database_service`, `open_food_facts_service`, cache aliment.
- Dashboard nutrition, calories, macros, repas recents, hydratation locale.
- Recherche aliment et detail premium.
- Tests sur providers repas et page nutrition.

### Assistant IA

- Hub assistant, chat, suggestions, contenus generes.
- Services assistant et execution d'outils IA.
- Prompt builder durci et tests dedies.
- Contenus : recettes, tips, weekly analysis, weekly menu.
- Risque a tester : quotas OpenRouter/Supabase, entitlement premium, streaming/timeout, messages offline.

### Sante

- Health hub.
- Apple Health / Health Connect via package `health`.
- Donnees : pas, calories, distance, sommeil, rythme cardiaque, HRV, SpO2, glucose, tension, cholesterol selon disponibilite plateforme.
- Vital scan / PPG service.
- Rapports sante IA et exports.
- Risque review : permissions Health Connect / HealthKit doivent etre justifiees et limitees aux usages affiches dans l'app.

### Exercice

- Ecrans course, force, manuel.
- Logs exercice, detail sheet, analysis IA.
- Repository exercice et migration media exercice.
- Permissions activity recognition cote Android.

### Progres

- Poids, courbes, photos progression, comparaison avant/apres.
- Provider stats progression.
- Tests sur widgets progression/profile.

### Profil et settings

- Profil, settings, langue, allergies, diet/allergies, conditions sante, categories repas.
- Aide/support, privacy, terms, storage, change password.
- Connexion Apple Health / Google Health depuis profil.

### i18n

- 30 locales ARB.
- Support RTL arabe.
- Localizations generees commitees.
- Risque a tester : textes longs sur petites resolutions Android et tablettes.

### Observabilite et qualite

- Sentry optionnel via `SENTRY_DSN`.
- Telemetry best-effort Supabase.
- `dart analyze`, `flutter test`, couverture CI avec seuil.
- Responsive smoke tests ajoutes.

## Points a valider avant App Store iOS

- Build production `com.Foodmi.Foodmi` avec `lib/main_production.dart`.
- RevenueCat Apple API key et produits App Store Connect.
- Privacy Policy / Terms accessibles publiquement.
- Notes for Review : HealthKit, IA nutritionnelle, compte demo.
- `REQUIRE_AI_ENTITLEMENT=true` cote Supabase prod si l'IA doit etre reservee aux abonnes.
- Test reel sur iPhone 16 Pro et au moins un iPhone plus petit.

## Points a valider avant Play Store Android

- AAB production signe avec keystore Foodmi.
- RevenueCat Google API key + produit Play Console.
- Google Sign-In : SHA-1/SHA-256 upload key et app signing key.
- Health Connect : declarations Play Console + permissions justifiees.
- Data Safety : camera, photos, health data, nutrition, identifiers, purchases, crash logs.
- Tests telephones, tablettes, pliables, orientations, API 26 a recent.
- Voir `app/PLAY_STORE_READINESS.md`.

## Risques connus

- Play Store n'est pas pret : ne pas publier Android avant matrice QA complete.
- Les permissions Android sont sensibles : camera, images, micro, activity recognition, Health Connect.
- Les claims marketing "scan en 3 secondes" doivent rester vrais sur devices Android moyens.
- Les screenshots store doivent correspondre aux features reellement testees.
- Les builds prod dependent de secrets `.env` et GitHub environments ; ne jamais les committer.
