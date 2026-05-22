# Sprint Launch -- Play Store + App Store

Objectif : sortir FoodMi sur les deux stores en 5 jours.

## Jour 1 (Lun) -- Fix Config + Comptes

| # | Tache | Type | Duree | Etat |
|---|-------|------|-------|------|
| 01 | Unifier Bundle ID iOS dans Xcode | DEV | 30 min | [ ] |
| 02 | Resoudre iOS flavors (methode KISS: --dart-define) | DEV | 15 min | [ ] |
| 03 | Creer/verifier comptes Play Console + App Store Connect | ADMIN | 20 min | [ ] |
| 04 | AdMob : desactiver pour le launch | DEV | 30 min | [ ] |
| 05 | Verifier Privacy Policy + Terms (deja codes, juste deployer le site) | -- | -- | [ ] |
| 06 | GitHub Secrets pour CI/CD | DEV | 30 min | [ ] |

**Parallele J1-J2 : Deployer website foodmi.app** (voir [[website/DEPLOYMENT]])

## Jour 2 (Mar) -- ASO + Metadata + Screenshots

| # | Tache | Type | Duree | Etat |
|---|-------|------|-------|------|
| 07 | Titre + Subtitle optimises | MARKETING | 30 min | [ ] |
| 08 | Description longue Google Play (4000 chars, 80+ keywords) | MARKETING | 1h | [ ] |
| 09 | 6 screenshots (3 tailles iOS + 1 Play) | MARKETING | 3h | [ ] |
| 10 | 4 Custom Store Listings Google Play | MARKETING | 2h | [ ] |
| 11 | Icone app finale (1024x1024) | DESIGN | 30 min | [ ] |

## Jour 3 (Mer) -- Build + Sign + Upload

| # | Tache | Type | Duree | Etat |
|---|-------|------|-------|------|
| 12 | Incrementer version (1.0.0+1) | DEV | 5 min | [ ] |
| 13 | Build Android AAB | DEV | 20 min | [ ] |
| 14 | Build iOS IPA | DEV | 30 min | [ ] |
| 15 | Upload sur les deux stores | DEV | 40 min | [ ] |
| 16 | RevenueCat : configurer produits dans les stores | ADMIN | 1h | [ ] |

## Jour 4 (Jeu) -- Review Prep + Legal

| # | Tache | Type | Duree | Etat |
|---|-------|------|-------|------|
| 17 | Content Rating (IARC) Google Play | ADMIN | 15 min | [ ] |
| 18 | Data Safety Google Play | ADMIN | 30 min | [ ] |
| 19 | App Privacy Apple | ADMIN | 30 min | [ ] |
| 20 | HealthKit review notes | DEV | 15 min | [ ] |
| 21 | Compte demo pour Apple reviewer | DEV | 15 min | [ ] |
| 22 | Release notes FR + EN | MARKETING | 15 min | [ ] |
| 23 | Recruter 30-50 beta testers | MARKETING | 30 min | [ ] |

## Jour 5 (Ven) -- Submit + Distribution

| # | Tache | Type | Duree | Etat |
|---|-------|------|-------|------|
| 24 | Submit for Review (les 2 stores) | ADMIN | 15 min | [ ] |
| 25 | Preparer draft ProductHunt | MARKETING | 1h | [ ] |
| 26 | Premier article Medium | MARKETING | 1h | [ ] |
| 27 | Apple Search Ads ($200 longtail) | MARKETING | 1h | [ ] |
| 28 | Schema.org + posts Reddit/IndieHackers | MARKETING | 30 min | [ ] |

## Post-Launch J+0 a J+7

```
J+0  App approuvee -> Apple Search Ads ON
     -> Lancer ProductHunt
     -> Demander reviews aux 50 beta testers
     -> Reddit, HackerNews, IndieHackers

J+1  -> Article Medium
     -> 5 reponses Quora
     -> Premier post LinkedIn

J+2  -> Analyser premiers rankings
     -> Ajuster keywords si besoin
     -> Activer les 4 CSL Google Play

J+3  -> Repondre a CHAQUE review
     -> Preparer A/B test screenshots

J+5  -> Premiere iteration ASO
     -> Preparer Meta Ads si budget

J+7  -> Fin du boost Apple (7 jours)
     -> Bilan : downloads, rankings, reviews, conversion
     -> Planifier sprint semaine 2
```

**Rappel** : Apple donne un boost algorithmique de 7 jours aux nouvelles apps. Ne pas gaspiller cette fenetre.
