# Website FoodMi -- Architecture

Repo : [foodmi/website](https://github.com/foodmi/website)

Le site actif est `website` (pas `website2` qui est archive).

## Stack

| Couche | Techno |
|--------|--------|
| Framework | Next.js 16.1.6 (App Router) |
| Langage | TypeScript 5.9.3 |
| i18n | next-intl -- 5 langues (en, fr, es, de, ar) |
| Styling | CSS (globals.css + webflow.css migre) |
| Analytics | @next/third-parties (Google Analytics, pas encore configure) |
| Package manager | Bun |

## Pages

- `/` -- Landing page (10+ sections)
- `/blog` -- Articles SEO (1 article, 5 langues)
- `/privacy` -- Politique de confidentialite (7 sections, 5 langues)
- `/terms` -- Conditions d'utilisation (10 sections, 5 langues)

Toutes les pages sont sous `[locale]/` pour l'i18n.

## Composants landing page

1. Navbar (badges store)
2. Hero (CTA principal)
3. Features
4. HowItWorks
5. WhyFoodmi
6. Comparison (code mais PAS importe dans page.tsx)
7. DietSupport
8. FAQ
9. Testimonials
10. SocialProof (stats -- placeholders a verifier)
11. DownloadCTA
12. Footer (liens store + socials)
13. ScrollReveal

## Fichiers de config IA

- `AGENTS.md` -- Instructions pour agents IA
- `CLAUDE.md` -- Instructions pour Claude Code
- `design/CHARTE-GRAPHIQUE.md` -- Charte graphique complete

## SEO

- Sitemap dynamique (`sitemap.ts`) -- ATTENTION : `/login` reference mais n'existe pas, a retirer
- robots.txt
- Open Graph tags
- Schema.org (SoftwareApplication + FAQPage)
- Schema Organization a ajouter
