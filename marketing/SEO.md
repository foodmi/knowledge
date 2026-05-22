# SEO -- Site Web & Programmatic

## Architecture URL cible

```
foodmi.app/                          (homepage)
foodmi.app/features/                 (overview)
foodmi.app/features/ai-food-scanner
foodmi.app/features/macro-tracking
foodmi.app/pricing/
foodmi.app/blog/
foodmi.app/calories-in/              (programmatic SEO parent)
foodmi.app/calories-in/banana
foodmi.app/calories-in/rice
foodmi.app/compare/                  (vs competitor)
foodmi.app/compare/myfitnesspal
foodmi.app/compare/calai
foodmi.app/compare/lose-it
```

## Keywords cibles

### Immediate (low competition)
- ai calorie tracker (1K-5K/mois)
- calorie tracker with photo (1K-3K)
- food scanner app (2K-5K)
- best calorie tracker 2026 (5K-10K)
- ai food recognition app (500-1K)
- automatic calorie tracking (1K-3K)

### Moyen terme
- calorie counter app free (5K-10K)
- food tracker app (10K-20K)
- macro tracker (15K-25K)

### Long terme
- calorie tracker (60K-100K)
- calorie counter (80K-120K)

## Programmatic SEO : "Calories in [Food]"

Opportunite #1 : 10,000+ pages generees automatiquement.

Source data : USDA FoodData Central API (gratuit, 300K+ aliments).

### Template de page
```
URL: foodmi.app/calories-in/[food-slug]
H1: Calories in [Food] - Complete Nutrition Breakdown

- Hero : image + gros chiffre calories + serving size selector
- Section 1 : Nutrition Facts Table (multi serving sizes)
- Section 2 : Deep dive 300-500 mots
- Section 3 : Comparaison avec aliments similaires
- Section 4 : Recettes populaires avec calories
- CTA : "Track [food] with Foodmi's AI scanner"
- FAQ (avec FAQ schema)
```

### Plan de scaling
| Phase | Pages | Timeline |
|-------|-------|----------|
| Phase 1 | Top 100 aliments | Mois 1 |
| Phase 2 | Top 500 | Mois 2-3 |
| Phase 3 | Top 2,000 | Mois 4-6 |
| Phase 4 | 5,000+ | Mois 7-12 |

## Technique SEO

- [x] SSR/SSG via Next.js (content en HTML brut)
- [x] Sitemap XML dynamique
- [x] robots.txt
- [x] Open Graph + Twitter Cards
- [x] Schema.org SoftwareApplication + FAQPage
- [ ] Schema.org Organization
- [ ] llms.txt
- [ ] Soumettre a Google Search Console
- [ ] Soumettre a Bing Webmaster Tools
- [ ] Configurer robots.txt pour AI crawlers
