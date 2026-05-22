# FoodMi -- Contexte Produit

## Qu'est-ce que FoodMi ?

FoodMi est une application mobile de suivi nutritionnel avec reconnaissance alimentaire par IA. L'utilisateur prend une photo de son repas, l'IA identifie les aliments et calcule les calories/macros instantanement.

## Positionnement

**"Le calorie tracker qui scanne tes repas en 3 secondes."**

- Concurrent direct de CalAI (5M users), MyFitnessPal (200M users), Yazio, Lifesum
- Differenciateur : IA + 30 langues + support Halal/Vegan + RTL arabe
- Cible : adultes 18-45 soucieux de leur sante, tech-savvy

## Equipe

- **Adam Chafqani** -- Fondateur, dev lead (Flutter, Supabase, IA)
- **Karim** -- Co-fondateur, marketing/ASO
- Equipe de 2, bootstrap, zero budget marketing
- Les deux ont le TDAH -- workflow adapte (voir [[team/WORKFLOW]])

## Stack Technique

| Couche | Techno |
|--------|--------|
| Mobile | Flutter 3.x + Dart + Riverpod |
| Backend | Supabase (PostgreSQL, Auth, Storage, Edge Functions) |
| IA | OpenRouter (Claude Sonnet 4, GPT-5.3) + Genkit |
| Monetisation | RevenueCat + Google AdMob |
| Website | Next.js 16 + next-intl (5 langues) |
| CI/CD | GitHub Actions |
| Hosting site | Vercel (a deployer) |

## Langues supportees

- **App** : 30 langues (ARB files)
- **Website** : 5 langues (en, fr, es, de, ar) avec support RTL
- **Store listings** : a localiser (priorite: FR, EN, AR, ES, DE)

## Repos GitHub

| Repo | Contenu | Etat |
|------|---------|------|
| `foodmi/app` | App Flutter iOS+Android | Actif, production-ready |
| `foodmi/website` | Site marketing Next.js (13 sections, blog, privacy, terms) | Actif, a deployer |
| `foodmi/website2` | Ancien site (2 langues, minimal) | Archive |
| `foodmi/knowledge` | Ce repo -- base de connaissance partagee | Actif |

## Business Model

- **Freemium** : version gratuite avec pubs (Google AdMob)
- **Premium** : trial 7 jours, abonnement mensuel/annuel (RevenueCat)
- Feature gating : scans illimites, assistant IA, rapports sante en premium

## Vision

Devenir le #1 des calorie trackers IA dans les marches non-anglophones (arabe, francais, espagnol, allemand) ou la concurrence est quasi inexistante avec une app de qualite.
