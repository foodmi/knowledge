# Meta Ads -- Playbook FoodMi

## Strategie low-budget

Ne PAS concurrencer CalAI sur iOS US ($4-6 CPI). Dominer les marches ou le CPI est $0.30-1.50.

## CPI par region

| Region | iOS | Android |
|--------|-----|---------|
| USA | $4.50-6.00 | $2.50-4.00 |
| France | $3.00-4.50 | $1.50-3.00 |
| MENA (arabe) | $0.50-1.50 | $0.20-0.60 |
| LATAM | $0.80-1.80 | $0.30-0.80 |
| SEA | $0.30-0.80 | $0.15-0.40 |

**$500/mois sur MENA+LATAM+SEA = 500-2,500 installs vs 80-140 sur iOS US.**

## Structure campagne

```
CAMPAGNE (CBO)
├── Ad Set 1 : BROAD (pas d'interet, age 18-55)
├── Ad Set 2 : INTERET Fitness
├── Ad Set 3 : INTERET Nutrition/Sante
├── Ad Set 4 : LOOKALIKE 1% (si 100+ events)
└── Ad Set 5 : RETARGETING
```

3-5 creatives par ad set. Budget : $20-50/jour total.

## Testing

- 5-7 jours par batch, 15-20 creatives
- Kill : $30+ depenses et 0 install, ou CPI > 2x cible apres $50
- Keep : CPI < cible et 5+ installs
- Creer 10 variations de la meilleure (hooks differents)
- JAMAIS augmenter budget >30%/jour

## Creatives UGC (top performer)

1. **Scan demo** : "J'ai decouvert une app qui scanne mes repas en 3 sec"
2. **Before/after** : "J'ai perdu 8kg en 6 semaines"
3. **Comparaison** : "J'en avais marre de MyFitnessPal"
4. **Routine matinale** : "Ma routine sante du matin en 30 secondes"
5. **Resultat choc** : "Mon medecin m'a dit que j'avais change mes analyses"

Higgsfield AI : 50-100 videos pour $100/mois vs $150-500/video avec UGC creators.

## Budget par phase

| Phase | Budget/mois | Geo | Objectif |
|-------|-------------|-----|----------|
| Validation (M1-2) | $500-1,000 | MENA+LATAM+SEA | Trouver 2-3 creatives gagnantes |
| Iteration (M3-4) | $1,000-2,000 | + France+Espagne | Optimiser trial -> paid |
| Scale (M5-6) | $2,000-5,000 | + US/UK/DACH | ROAS positif |
| Domination (M7+) | $5,000+ | Toutes geos | CAC/LTV < 1:3 |

## Metrics cibles

| Metric | Cible | Kill |
|--------|-------|------|
| CTR | >1.0% Reels, >0.8% Feed | <0.5% |
| CPI iOS US | <$5.00 | >$7.00 |
| CPI Android MENA | <$0.50 | >$1.00 |
| CPT (trial) | <$10 iOS, <$3 Android | >$20 |
| Trial-to-paid | >30% | <20% |
| D30 ROAS | >40% | <25% |

## iOS post-ATT

- Conversion API (CAPI) obligatoire (server-side via Supabase Edge Function)
- Broad targeting performe souvent MIEUX que interest targeting
- SKAdNetwork : patienter 72h minimum avant d'analyser
- Opt-in rate apps sante : 25-35%
