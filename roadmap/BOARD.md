# Board -- Kanban Foodmi

Mise a jour : 23 juin 2026.
Reference app : `foodmi/app` commit `f28ede8e`.

## FAIT

- [x] Auth Supabase email / Google / Apple.
- [x] Onboarding conversationnel + persistance progression.
- [x] Paywall et RevenueCat integres.
- [x] Backend Supabase dev/prod separe.
- [x] Services IA Genkit/OpenRouter via Supabase Edge Functions.
- [x] Scan repas/menu/table cote app.
- [x] Dashboard, journal, nutrition, recherche aliment.
- [x] Exercise logging et analyses.
- [x] Health hub, HealthKit/Health Connect integration cote app.
- [x] Progress photos, poids, stats progression.
- [x] 30 locales ARB + RTL arabe.
- [x] CI tests/analyze + seuil couverture.
- [x] Script `scripts/foodmi_app.sh` pour dev/prod iOS/Android.
- [x] Commit app `f28ede8e` pousse sur `foodmi/app main`.
- [x] Build dev release installe sur iPhone 16 Pro (`Foodmi Dev`).

## EN COURS -- iOS mainnet

- [ ] Build production iOS `com.Foodmi.Foodmi` avec `lib/main_production.dart`.
- [ ] Verifier `REVENUECAT_APPLE_API_KEY` et produits App Store Connect.
- [ ] Verifier Supabase prod + `REQUIRE_AI_ENTITLEMENT=true` si necessaire.
- [ ] Tester iPhone 16 Pro en prod/sandbox.
- [ ] Tester un iPhone plus petit.
- [ ] App Store Connect : privacy nutrition labels.
- [ ] App Store Connect : screenshots, metadata, age rating.
- [ ] Notes for Review : HealthKit, camera, IA nutritionnelle, compte demo.
- [ ] Submit for Review Apple.

## BLOQUE / NO-GO -- Android Play Store

Android ne part pas en production avant validation de `app/PLAY_STORE_READINESS.md`.

- [ ] Generer AAB production signe.
- [ ] Creer/configurer Play Console pour `com.Foodmi.Foodmi`.
- [ ] Configurer Google Play App Signing.
- [ ] Ajouter SHA-1/SHA-256 upload key + app signing key dans Google Cloud/Supabase.
- [ ] Configurer RevenueCat Google et produit Play Console.
- [ ] Remplir Data Safety.
- [ ] Remplir declarations Health Connect / permissions sensibles.
- [ ] Internal testing avec testeurs.
- [ ] Tests telephones Android.
- [ ] Tests tablettes Android.
- [ ] Tests pliables.
- [ ] Tests RTL arabe et grandes polices.
- [ ] Verifier crash-free / telemetry.

## TODO -- iOS release polish

- [ ] Privacy Policy / Terms accessibles et lies dans App Store Connect.
- [ ] Compte demo reviewer avec donnees pre-remplies.
- [ ] Release notes FR/EN.
- [ ] Tester restore purchase.
- [ ] Tester delete account.
- [ ] Tester refus/revocation camera, photo, HealthKit.
- [ ] Verifier aucune mention Android/Play Store dans metadata iOS.

## TODO -- Android QA detail

- [ ] Parcours complet onboarding -> paywall -> achat sandbox.
- [ ] Scan camera sur Android 13+.
- [ ] Import galerie Android 13+ (`READ_MEDIA_IMAGES`).
- [ ] Import galerie Android 12- (`READ_EXTERNAL_STORAGE`).
- [ ] Health Connect absent / installe / permissions partielles.
- [ ] Micro refuse / autorise.
- [ ] Reseau lent, offline, timeout IA.
- [ ] Layouts tablette portrait/landscape.
- [ ] Foldable plie/deplie.
- [ ] Font scale 130% et 200%.

## TODO -- Store assets

- [ ] Valider icone 1024x1024 et 512x512.
- [ ] Screenshots iOS prioritaires.
- [ ] Screenshots Android telephone.
- [ ] Screenshots Android tablette.
- [ ] Feature graphic Google Play 1024x500.
- [ ] Metadata locales prioritaires : en, fr, ar, es, de.
- [ ] Garder les claims alignes avec les features testees.

## TODO -- Post iOS launch

- [ ] Surveiller crashes Sentry/Supabase.
- [ ] Repondre aux reviews.
- [ ] Iterer screenshots / ASO.
- [ ] Preparer Android internal testing.
- [ ] Recruter beta testers Android.
