# Sprint Launch -- iOS Mainnet puis Android Play Store

Mise a jour : 23 juin 2026.

## Principe

1. Sortir iOS mainnet proprement.
2. Ne pas publier Android tant que la checklist Play Store n'est pas verte.
3. Traiter Android comme une vraie release separee, pas comme un simple port.

## Semaine 1 -- iOS mainnet

### Dev

- [ ] Synchroniser `main` et verifier commit app `f28ede8e`.
- [ ] Remplir `.env` prod local : Supabase prod, Google, RevenueCat Apple.
- [ ] Verifier Supabase prod et edge functions.
- [ ] Activer `REQUIRE_AI_ENTITLEMENT=true` si l'IA doit etre premium-only.
- [ ] Lancer `dart analyze`.
- [ ] Lancer `flutter test`.
- [ ] Lancer `CHECK_REMOTE=1 RUN_FULL_TESTS=1 RUN_BUILDS=0 scripts/prod_readiness_check.sh`.
- [ ] Build IPA production.
- [ ] Tester build prod sur iPhone 16 Pro ou TestFlight.
- [ ] Tester au moins un iPhone plus petit.

### App Store Connect

- [ ] Verifier bundle `com.Foodmi.Foodmi`.
- [ ] Configurer produits/subscriptions.
- [ ] Relier RevenueCat Apple.
- [ ] Ajouter privacy nutrition labels.
- [ ] Ajouter age rating.
- [ ] Ajouter screenshots iOS.
- [ ] Ajouter metadata FR/EN minimum.
- [ ] Ajouter privacy policy / terms.
- [ ] Creer compte demo reviewer.
- [ ] Notes for Review : HealthKit, camera, IA nutritionnelle, achat sandbox.

### QA iOS

- [ ] Onboarding complet.
- [ ] Paywall, trial, purchase sandbox, restore.
- [ ] Login email, Google, Apple.
- [ ] Scan camera et galerie.
- [ ] Menu/table analysis.
- [ ] Dashboard apres sauvegarde repas.
- [ ] Assistant IA.
- [ ] HealthKit refuse / autorise / revoke.
- [ ] Delete account.

### Sortie

- [ ] Upload IPA / TestFlight.
- [ ] Corriger les blockers si Apple/TestFlight remonte un probleme.
- [ ] Submit for Review Apple.

## Semaine 2 -- Android readiness, pas rollout public

### Build / Play Console

- [ ] Creer/verifier upload keystore.
- [ ] Creer `android/keystore.properties` local.
- [ ] Generer AAB production signe.
- [ ] Creer app Play Console `com.Foodmi.Foodmi`.
- [ ] Activer Play App Signing.
- [ ] Uploader AAB en Internal testing.
- [ ] Ajouter testeurs internes.
- [ ] Configurer RevenueCat Google + produit Play.
- [ ] Ajouter SHA-1/SHA-256 upload key + app signing key dans Google Cloud/Supabase.

### Declarations Play

- [ ] Content Rating IARC.
- [ ] Data Safety.
- [ ] Ads = No ads.
- [ ] App access / compte demo.
- [ ] Health Connect permissions.
- [ ] Target audience adults only.
- [ ] Privacy Policy / Terms.

### QA Android telephones

- [ ] Device recent Android 14/15/16.
- [ ] Device moyen/bas de gamme.
- [ ] Android 8/9/10 via device ou Firebase Test Lab.
- [ ] Camera, galerie, micro, activity recognition.
- [ ] Google Sign-In.
- [ ] Purchase/restore sandbox Google Play.
- [ ] Scan repas/menu/table.
- [ ] Offline / reseau lent.

### QA Android tablettes / pliables

- [ ] Tablette 7"-8" portrait.
- [ ] Tablette 10"-11" portrait.
- [ ] Tablette landscape.
- [ ] Pliable plie.
- [ ] Pliable deplie.
- [ ] Font scale 130% et 200%.
- [ ] RTL arabe.
- [ ] Onboarding, paywall, dashboard, scan result, profile/settings.

## Semaine 3 -- Android closed testing

- [ ] Corriger les issues Android internes.
- [ ] Relancer AAB.
- [ ] Closed testing plus large.
- [ ] Surveiller crashes et ANR.
- [ ] Verifier Data Safety apres SDK scan Play.
- [ ] Preparer release notes Android.
- [ ] Decision Go/No-Go rollout progressif.

## Semaine 4 -- Post-launch / ASO

- [ ] Surveiller iOS metrics, crashes, reviews.
- [ ] Iterer metadata iOS.
- [ ] Finaliser Android production si closed testing est stable.
- [ ] Lancer contenu SEO/ASO prioritaire.
- [ ] Preparer updates toutes les 2 semaines.

## Definition of Done

### iOS

- App Store review soumise ou acceptee.
- Aucun crash bloquant dans parcours onboarding/paywall/scan.
- Purchase/restore fonctionne.
- Privacy et reviewer notes complets.

### Android

- `app/PLAY_STORE_READINESS.md` coche.
- Internal/closed testing stable.
- Matrice telephones/tablettes/pliables validee.
- Play Console ne remonte pas de blocker policy.
