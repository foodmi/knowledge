# App Foodmi -- Build & Deploiement

Reference app : `foodmi/app` commit `f28ede8e` sur `main`.
Date : 23 juin 2026.

## Decision release

| Plateforme | Statut | Action |
|------------|--------|--------|
| iOS | Priorite mainnet | Finaliser build production, App Store Connect, privacy, notes reviewer |
| Android | Pas pret Play Store | Qualifier AAB, Play Console, Health Connect, Data Safety, tests multi-supports |

Ne pas publier Android tant que `app/PLAY_STORE_READINESS.md` n'est pas coche.

## Environnements

| Env | Entry point | Android flavor | Bundle/applicationId | Supabase |
|-----|-------------|----------------|----------------------|----------|
| Dev | `lib/main_dev.dart` | `dev` | `com.Foodmi.Foodmi.dev` | `rpsjptvowzijinwxhvsl` |
| Prod | `lib/main_production.dart` | `production` | `com.Foodmi.Foodmi` | `kiojfmsvckighowrceei` |

Le script local officiel est :

```bash
scripts/foodmi_app.sh <dev|prod> <ios|android> <build|run|install> [--device DEVICE_ID] [--mode debug|release|profile]
```

## Secrets locaux requis

Dans `.env` local, jamais committe :

```bash
SUPABASE_DEV_ANON_KEY=...
SUPABASE_PROD_ANON_KEY=...
GOOGLE_WEB_CLIENT_ID=...
GOOGLE_IOS_DEV_CLIENT_ID=...
GOOGLE_IOS_PROD_CLIENT_ID=...
REVENUECAT_APPLE_API_KEY=...
REVENUECAT_GOOGLE_API_KEY=...
```

Secrets operateur uniquement pour scripts/admin :

```bash
SUPABASE_ACCESS_TOKEN=...
SUPABASE_DB_URL=...
SUPABASE_DB_PASSWORD=...
SUPABASE_SERVICE_ROLE_KEY=...
```

Ne jamais passer service-role/access token/DB password en `--dart-define`.

## iOS -- chemin mainnet

### Smoke test local dev

Commande deja utilisee avec succes pour installer `Foodmi Dev` sur iPhone 16 Pro :

```bash
scripts/foodmi_app.sh dev ios run --mode release --device 00008140-00126D903693001C
```

Si iOS refuse le lancement : approuver le profil dans `Reglages > General > VPN et gestion de l'appareil`.

### Build production

```bash
set -a
source .env
set +a

flutter build ipa --release \
  -t lib/main_production.dart \
  --obfuscate \
  --split-debug-info=build/symbols-ios \
  --dart-define=ENVIRONMENT=production \
  --dart-define=SUPABASE_URL=https://kiojfmsvckighowrceei.supabase.co \
  --dart-define=SUPABASE_ANON_KEY=$SUPABASE_PROD_ANON_KEY \
  --dart-define=GOOGLE_WEB_CLIENT_ID=$GOOGLE_WEB_CLIENT_ID \
  --dart-define=REVENUECAT_APPLE_API_KEY=$REVENUECAT_APPLE_API_KEY \
  --export-options-plist=ios/ExportOptions.plist
```

### Checklist iOS avant soumission

- [ ] Bundle production `com.Foodmi.Foodmi` dans Xcode/App Store Connect.
- [ ] Provisioning/certificats Apple production valides.
- [ ] Produit(s) RevenueCat relies a App Store Connect.
- [ ] Privacy Policy et Terms publics.
- [ ] Notes for Review : HealthKit, camera, IA nutritionnelle, compte demo.
- [ ] Tester abonnement/trial en sandbox.
- [ ] Tester scan, onboarding, paywall, restore purchase, delete account.
- [ ] Verifier `REQUIRE_AI_ENTITLEMENT=true` cote Supabase prod si l'IA est payante.

## Android -- build, mais pas encore rollout

### Build production AAB

Prerequis : `android/keystore.properties` et keystore local non committes.

```properties
storePassword=<password>
keyPassword=<password>
keyAlias=<alias>
storeFile=upload-keystore.jks
```

Commande :

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

Output attendu :

```text
build/app/outputs/bundle/productionRelease/app-production-release.aab
```

### Pourquoi Android n'est pas pret

- Pas de validation Play Console complete.
- AAB signe non qualifie sur vraie matrice Android.
- Health Connect et permissions sensibles a declarer.
- Data Safety a remplir avec precision.
- Tests tablette/pliable/orientation manquants.
- Google Sign-In doit etre valide avec SHA app signing + upload key.

Voir `app/PLAY_STORE_READINESS.md`.

## Readiness prod locale

Commande complete :

```bash
CHECK_REMOTE=1 RUN_FULL_TESTS=1 RUN_BUILDS=1 scripts/prod_readiness_check.sh
```

Commande rapide :

```bash
CHECK_REMOTE=1 RUN_FULL_TESTS=1 RUN_BUILDS=0 scripts/prod_readiness_check.sh
```

Le gate doit verifier :

- variables prod obligatoires
- absence de secrets serveur dans le code client
- `flutter pub get`
- `dart analyze`
- `flutter test`
- migrations et edge functions Supabase
- dry-run `supabase db push`
- builds release si `RUN_BUILDS=1`

## GitHub Actions / secrets

Production GitHub environment :

```text
SUPABASE_URL
SUPABASE_ANON_KEY
SUPABASE_ACCESS_TOKEN
SUPABASE_DB_URL
GOOGLE_WEB_CLIENT_ID
REVENUECAT_GOOGLE_API_KEY
REVENUECAT_APPLE_API_KEY
KEYSTORE_BASE64
KEYSTORE_PASSWORD
KEY_PASSWORD
KEY_ALIAS
P12_CERTIFICATE_BASE64
P12_PASSWORD
PROVISION_PROFILE_BASE64
KEYCHAIN_PASSWORD
```

## Store review

### Apple

- Review souvent 24-48h, mais HealthKit peut rallonger.
- Fournir compte demo avec donnees pre-remplies.
- Expliquer pourquoi l'app lit les donnees sante.

### Google

- Premier review peut prendre plusieurs jours.
- Ne pas lancer rollout production direct : commencer par internal testing / closed testing.
- Verifier toutes les declarations Data Safety avant upload public.
