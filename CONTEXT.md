# Foodmi -- Contexte Produit

## Qu'est-ce que Foodmi ?

Foodmi est une application mobile de suivi nutritionnel avec reconnaissance alimentaire par IA. L'utilisateur prend une photo d'un repas ou d'un menu, l'IA estime les aliments, calories, macros et aide a suivre un objectif de perte de poids, maintien ou prise de masse.

## Positionnement

**"Le calorie tracker IA qui transforme une photo de repas en suivi nutritionnel."**

- Concurrent direct de CalAI (5M users), MyFitnessPal (200M users), Yazio, Lifesum
- Differenciateurs : scan IA, assistant nutritionnel, onboarding personnalise, 30 langues, support Halal/Vegan, RTL arabe, suivi sante/progres
- Cible : adultes 18-45 soucieux de leur sante, tech-savvy

## Contraintes equipe

- Petite equipe bootstrap, zero budget marketing
- TDAH -- les taches doivent etre decoupees en micro-actions de 15-30 min max
- Methode Pomodoro (25 min focus / 5 min break)
- 6h de travail effectif max par jour
- Async-first, KISS (pas de setup qui prend >2h)

## Stack Technique

| Couche | Techno |
|--------|--------|
| Mobile | Flutter 3.x + Dart + Riverpod |
| Backend | Supabase (PostgreSQL, Auth, Storage, Edge Functions) |
| IA | OpenRouter + Genkit + Supabase Edge Functions |
| Monetisation | RevenueCat |
| Website | Next.js + next-intl |
| CI/CD | GitHub Actions |
| Hosting site | Vercel |

## Etat release -- 23 juin 2026

| Plateforme | Etat | Decision |
|------------|------|----------|
| iOS | Candidat mainnet en cours | Priorite immediate : build prod, App Store Connect, privacy, reviewer notes |
| Android | Pas pret Play Store | Pas de rollout avant tests multi-supports, AAB signe, Play Console, Health Connect/Data Safety |
| Website | Site marketing actif | Doit rester disponible pour privacy/terms/store review |

Dernier commit app pousse : `f28ede8e` sur `foodmi/app`.

Note : le build local `Foodmi Dev` release a ete installe sur iPhone 16 Pro. Le lancement etait bloque par la confiance du profil developpeur iOS, pas par le build. Pour la soumission publique, utiliser la configuration production et non `Foodmi Dev`.

## Langues supportees

- **App** : 30 langues (ARB files)
- **Website** : 5 langues (en, fr, es, de, ar) avec support RTL
- **Store listings** : a localiser (priorite: FR, EN, AR, ES, DE)

## Repos GitHub

| Repo | Contenu | Etat |
|------|---------|------|
| `foodmi/app` | App Flutter iOS+Android | Actif, iOS mainnet en preparation, Android Play Store a qualifier |
| `foodmi/website` | Site marketing Next.js (13 sections, blog, privacy, terms) | Actif, a deployer |
| `foodmi/website2` | Ancien site (2 langues, minimal) | Archive |
| `foodmi/knowledge` | Ce repo -- base de connaissance partagee | Actif |

## Business Model

- **Premium only** : trial 3 jours, puis abonnement mensuel/annuel (RevenueCat)
- Pas de version gratuite, pas de pubs

## Vision

Devenir le #1 des calorie trackers IA dans les marches non-anglophones (arabe, francais, espagnol, allemand) ou la concurrence est quasi inexistante avec une app de qualite.
