# Website FoodMi -- Deploiement

## Etat actuel (22 mai 2026)

- [ ] **PAS DEPLOYE** -- le site n'est pas encore live
- [ ] 13 liens `href="#"` a remplacer (store badges + socials)
- [ ] Google Analytics pas configure
- [ ] Composant Comparison pas importe dans page.tsx
- [ ] Stats SocialProof = placeholders

## Deployer sur Vercel

### Option 1 : Vercel CLI
```bash
cd website
npx vercel --prod
```

### Option 2 : Dashboard Vercel
1. Import git repo sur vercel.com/new
2. Framework preset : Next.js
3. Root directory : `.` (ou `website` si monorepo)
4. Build command : `bun run build`
5. Add domain : `foodmi.app`

### DNS
```
CNAME foodmi.app -> cname.vercel-dns.com
```

## Fixes avant deploiement

### 1. Remplacer les href="#"

| Fichier | Lignes | Quoi |
|---------|--------|------|
| Hero.tsx | 26, 29 | App Store + Google Play badges |
| Navbar.tsx | 102, 105, 135, 136 | Badges mobile + desktop |
| DownloadCTA.tsx | 32, 35 | CTA section badges |
| Footer.tsx | 20, 23 | Store links |
| Footer.tsx | 50, 55, 62 | Facebook, Instagram, TikTok |

URLs attendues :
- App Store : `https://apps.apple.com/app/foodmi-ai-calorie-tracker/id[APP_ID]`
- Play Store : `https://play.google.com/store/apps/details?id=com.FoodMi.FoodMi`

### 2. Fix sitemap
Retirer `/login` de `src/app/sitemap.ts` ligne 16.

### 3. Ajouter Comparison
Importer `Comparison` dans `[locale]/page.tsx`, placer entre WhyFoodmi et DietSupport.

### 4. Configurer Google Analytics
```tsx
// src/app/[locale]/layout.tsx
import { GoogleAnalytics } from '@next/third-parties/google'
// Dans le JSX :
<GoogleAnalytics gaId="G-XXXXXXXXXX" />
```

### 5. Ajouter Schema.org Organization
```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Foodmi",
  "url": "https://foodmi.app",
  "logo": "https://foodmi.app/app-icon.png"
}
```

### 6. Verifier SocialProof
Les stats affichees ("500K+ users", "4.8 rating") sont des placeholders. Mettre des chiffres reels ou retirer la section.
