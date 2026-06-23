# Play Store Readiness -- Android

Date : 23 juin 2026.
Statut : **pas pret pour rollout Play Store**.

Objectif : rendre Foodmi Android publiable sans regression par rapport a iOS, avec validation sur telephones, tablettes, pliables, orientations et permissions sensibles.

## Etat technique actuel

| Sujet | Etat |
|-------|------|
| Package production | `com.Foodmi.Foodmi` |
| Flavor production | `production` |
| Entry point | `lib/main_production.dart` |
| Version | `1.0.0+1` |
| minSdk | 26 (Android 8.0+) |
| Signing release | `android/keystore.properties` requis |
| RevenueCat Google | cle `REVENUECAT_GOOGLE_API_KEY` requise |
| Health Connect | permissions Android declarees, review Play requise |
| Camera/images | permissions declarees, test Android 13+ requis |

## Go / No-Go

Android reste **No-Go** tant que ces points ne sont pas tous verts :

- [ ] AAB production signe genere et installe/teste via internal testing.
- [ ] Google Play Console creee/configuree pour `com.Foodmi.Foodmi`.
- [ ] RevenueCat Google relie au produit Play Console.
- [ ] Google Sign-In valide avec SHA-1/SHA-256 upload key et App Signing key.
- [ ] Data Safety remplie et relue.
- [ ] Health Connect declarations remplies et justifiees.
- [ ] Tests Android passes sur telephones, tablettes, pliables, orientations.
- [ ] Aucun crash bloquant dans onboarding, scan, paywall, login, restore, delete account.

## Build et signing

### A faire

- [ ] Creer ou retrouver upload keystore Foodmi.
- [ ] Ajouter localement `android/keystore.properties`.
- [ ] Verifier que le keystore n'est pas commite.
- [ ] Generer AAB :

```bash
set -a
source .env
set +a

flutter build appbundle --release \
  --flavor production \
  -t lib/main_production.dart \
  --obfuscate \
  --split-debug-info=build/symbols-aab \
  --dart-define=ENVIRONMENT=production \
  --dart-define=SUPABASE_URL=https://kiojfmsvckighowrceei.supabase.co \
  --dart-define=SUPABASE_ANON_KEY=$SUPABASE_PROD_ANON_KEY \
  --dart-define=GOOGLE_WEB_CLIENT_ID=$GOOGLE_WEB_CLIENT_ID \
  --dart-define=REVENUECAT_GOOGLE_API_KEY=$REVENUECAT_GOOGLE_API_KEY
```

- [ ] Archiver `build/symbols-aab` avec le numero de version.
- [ ] Upload dans Internal testing avant toute prod.

## Play Console

### App setup

- [ ] Creer app Foodmi dans Play Console.
- [ ] Package name : `com.Foodmi.Foodmi`.
- [ ] Configurer App Signing by Google Play.
- [ ] Uploader AAB en Internal testing.
- [ ] Ajouter testeurs internes.
- [ ] Configurer pays de lancement.
- [ ] Renseigner contact developer/support.

### Store listing

- [ ] Titre, short description, long description.
- [ ] Feature graphic 1024x500.
- [ ] Icone haute resolution 512x512.
- [ ] Screenshots telephone.
- [ ] Screenshots tablette 7" et 10" si Play Console les demande.
- [ ] Locales prioritaires : en, fr, ar, es, de.
- [ ] Ne pas utiliser de screenshots de features non testees sur Android.

### Declarations

- [ ] Content Rating IARC.
- [ ] Data Safety.
- [ ] Ads : declarer **No ads**.
- [ ] App access : fournir compte demo si paywall/login bloque le reviewer.
- [ ] Target audience : adultes, pas enfants.
- [ ] Health apps / medical disclaimer si demande.
- [ ] Health Connect permissions / sensitive permissions.

## Data Safety -- donnees a declarer

Verifier dans Play Console selon l'implementation finale :

- Personal info : email, nom/profil si collecte.
- Health and fitness : poids, objectifs, nutrition, repas, activite, donnees Health Connect.
- Photos/videos : photos repas, photos progression si upload/storage.
- Audio : micro pour speech-to-text.
- App activity : analytics/telemetry.
- App info and performance : crash logs/Sentry.
- Device identifiers : selon SDKs Supabase/RevenueCat/Sentry.
- Purchases : abonnements via Google Play/RevenueCat.

Pour chaque type : preciser collecte, partage, chiffrement en transit, suppression compte, usage app functionality/analytics.

## Permissions Android a tester

Permissions sensibles declarees ou utilisees :

- Camera : scan repas/menu.
- Images : import galerie, Android 13+ `READ_MEDIA_IMAGES`, Android 12- `READ_EXTERNAL_STORAGE`.
- Micro : dictee assistant.
- Activity recognition : activite/pas.
- Health Connect : steps, calories, distance, heart rate, sleep, glucose, blood pressure, oxygen, respiratory rate.

Tests minimum :

- [ ] Premiere ouverture apres install propre.
- [ ] Refuser camera puis re-autoriser depuis settings.
- [ ] Refuser galerie puis importer une image.
- [ ] Refuser micro puis envoyer texte normal.
- [ ] Installer sans Health Connect.
- [ ] Installer avec Health Connect mais sans permissions.
- [ ] Autoriser partiellement Health Connect.
- [ ] Revoquer permissions pendant l'app ouverte.

## Matrice de tests Android

### Telephones

- [ ] Petit ecran : 5.4"-5.8", 1080p ou moins.
- [ ] Standard : Pixel/Samsung recent, Android 14/15/16.
- [ ] Moyen/bas de gamme : RAM limitee, CPU moyen, reseau lent.
- [ ] Android 8/9/10 si disponible ou Firebase Test Lab.

### Tablettes

- [ ] 7"-8" portrait et landscape.
- [ ] 10"-11" portrait et landscape.
- [ ] Verifier onboarding, paywall, dashboard, scan result sheet, profile/settings.
- [ ] Pas de texte coupe, pas de bottom sheet trop haute, pas de boutons hors ecran.

### Pliables

- [ ] Ecran plie format telephone.
- [ ] Ecran deplie format tablette.
- [ ] Rotation pendant onboarding / scan result / paywall.

### Orientations et responsive

- [ ] Portrait principal.
- [ ] Landscape tablette.
- [ ] Font scale 100%, 130%, 200%.
- [ ] Mode sombre systeme.
- [ ] RTL arabe.

## Parcours critiques a tester

- [ ] Install propre -> onboarding complet -> paywall -> login.
- [ ] Login email.
- [ ] Login Google.
- [ ] Restore purchase.
- [ ] Acheter abonnement sandbox/internal test.
- [ ] Scanner repas avec camera.
- [ ] Scanner depuis galerie.
- [ ] Scanner menu/table.
- [ ] Editer un resultat de scan et sauvegarder.
- [ ] Ajouter aliment depuis recherche.
- [ ] Dashboard apres repas sauvegarde.
- [ ] Eau / poids / glucose / tension / cholesterol.
- [ ] Exercise manuel/course/force.
- [ ] Assistant chat et contenus generes.
- [ ] Progress photos.
- [ ] Changer langue, tester arabe RTL.
- [ ] Delete account.
- [ ] Offline / reseau lent / timeout IA.

## Qualite et CI

- [ ] `dart analyze`
- [ ] `flutter test`
- [ ] `flutter test --coverage`
- [ ] `CHECK_REMOTE=1 RUN_FULL_TESTS=1 RUN_BUILDS=1 scripts/prod_readiness_check.sh`
- [ ] Internal testing crash-free sur au moins 24h.
- [ ] Sentry ou Supabase telemetry verifiee en prod.

## Risques specifiques Play Store

- Permissions Health Connect refusees si justification trop large.
- Data Safety incoherente avec SDKs ou permissions.
- Screenshots montrant des fonctions non robustes sur Android.
- Paywall bloquant le reviewer sans compte demo.
- Google Sign-In casse si SHA Play App Signing non ajoute dans Google Cloud/Supabase.
- Layouts tablette/pliable non testes.

## Definition of Done Android

Android peut passer en rollout progressif seulement si :

- AAB production signe est accepte par Play Console.
- Internal testing valide les parcours critiques.
- Data Safety, Health Connect et content rating sont completes.
- Au moins 1 telephone recent, 1 telephone moyen, 1 tablette et 1 scenario RTL passent.
- Aucune permission critique ne bloque l'utilisation de base.
- RevenueCat Google purchase/restore fonctionne.
