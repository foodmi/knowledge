# App FoodMi -- Build & Deploiement

## Blockers connus (au 22 mai 2026)

1. **iOS Bundle ID mismatch** : Xcode a `com.adamchafqani.scanflow`, doit etre `com.FoodMi.FoodMi`
2. **iOS flavors manquants** : pas de schemes Xcode pour dev/prod -> builder sans `--flavor`, utiliser `--dart-define`
3. **AdMob a retirer** : les IDs de test sont encore dans les manifests -> supprimer toute integration AdMob (pas de pubs)
4. **Website pas deploye** : privacy/terms inaccessibles -> deployer sur Vercel d'abord

## Build Android

```bash
flutter build appbundle --release \
  --flavor production \
  --dart-define=SUPABASE_URL=https://xxx.supabase.co \
  --dart-define=SUPABASE_ANON_KEY=xxx \
  --dart-define=GOOGLE_WEB_CLIENT_ID=xxx \
  --dart-define=REVENUECAT_GOOGLE_API_KEY=xxx

# Output : build/app/outputs/bundle/productionRelease/app-production-release.aab
```

## Build iOS

```bash
flutter build ipa --release \
  --dart-define=SUPABASE_URL=https://xxx.supabase.co \
  --dart-define=SUPABASE_ANON_KEY=xxx \
  --dart-define=GOOGLE_WEB_CLIENT_ID=xxx \
  --dart-define=REVENUECAT_APPLE_API_KEY=xxx \
  --export-options-plist=ios/ExportOptions.plist

# Output : build/ios/ipa/FoodMi.ipa
```

## Upload

### Google Play Console
1. App releases -> Production -> Create new release
2. Upload AAB
3. Remplir release notes
4. Sauvegarder en draft (ne PAS publier avant review)

### App Store Connect
```bash
xcrun altool --upload-app -f build/ios/ipa/FoodMi.ipa \
  -t ios -u "apple-id@email.com" -p "app-specific-password"
```
Ou via Xcode : Window -> Organizer -> Distribute App

## GitHub Secrets (CI/CD)

### Android
- `KEYSTORE_BASE64` -- base64 encode FoodMi-release.jks
- `KEYSTORE_PASSWORD`
- `KEY_PASSWORD`
- `KEY_ALIAS`

### iOS
- `P12_CERTIFICATE_BASE64`
- `P12_PASSWORD`
- `PROVISION_PROFILE_BASE64`

### Partages
- `SUPABASE_URL`, `SUPABASE_ANON_KEY`
- `GOOGLE_WEB_CLIENT_ID`
- `REVENUECAT_GOOGLE_API_KEY`, `REVENUECAT_APPLE_API_KEY`

## Apple Review -- Notes importantes

- **HealthKit** : Apple est strict. Preparer un texte dans "Notes for Review" expliquant pourquoi HealthKit est utilise
- **Compte demo** : creer un compte test dans Supabase avec donnees pre-remplies
- **Privacy Policy** : doit etre accessible a une URL publique (foodmi.app/privacy)

## Delais de review

- Apple : 24-48h (parfois 1 semaine si HealthKit)
- Google : 1-7 jours (premier build souvent plus long)
