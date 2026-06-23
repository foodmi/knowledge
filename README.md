# Foodmi Knowledge Base

Base de connaissance partagee pour Foodmi. Ouvrir ce dossier dans Obsidian pour une navigation optimale.

## Etat actuel -- 23 juin 2026

- `foodmi/app` : commit `f28ede8e` pousse sur `main`.
- iOS : sortie mainnet/App Store en priorite. La validation locale recente a ete faite sur iPhone 16 Pro avec `Foodmi Dev`; la build publique doit utiliser `prod`, `com.Foodmi.Foodmi`, RevenueCat Apple et les secrets production.
- Android / Play Store : pas pret pour rollout. Il manque la validation AAB signee, la configuration Play Console, les tests Android multi-supports et la checklist Data Safety / Health Connect / permissions.
- Ce repo est la source de verite pour le plan release et les points bloquants.

## Structure

```
knowledge/
├── CONTEXT.md                  # Vision, produit, positionnement
├── app/
│   ├── ARCHITECTURE.md         # Stack technique Flutter + Supabase
│   ├── FEATURES.md             # Features existantes
│   ├── DEPLOYMENT.md           # Build, sign, upload stores
│   └── PLAY_STORE_READINESS.md # Checklist Android / Play Store
├── website/
│   ├── ARCHITECTURE.md         # Stack Next.js
│   └── DEPLOYMENT.md           # Deploiement Vercel
├── roadmap/
│   ├── BOARD.md                # Kanban : TODO / EN COURS / FAIT
│   ├── LAUNCH-SPRINT.md        # Sprint iOS mainnet + Android readiness
│   └── BACKLOG.md              # Idees futures, features a explorer
├── marketing/
│   ├── ASO.md                  # App Store Optimization
│   ├── SEO.md                  # SEO website + programmatic
│   ├── LLM-SEO.md             # Optimisation pour ChatGPT/Claude/Gemini
│   ├── META-ADS.md            # Playbook Meta Ads
│   └── CONTENT-DISTRIBUTION.md # Medium, Quora, LinkedIn
├── playbooks/
│   └── CONVENTIONS.md          # Regles de code, naming, git
└── daily/
    ├── 2026-06-23.md           # Etat release iOS / Android
    └── TEMPLATE.md             # Template standup quotidien
```

## Comment utiliser

1. **Cloner** : `git clone https://github.com/foodmi/knowledge.git`
2. **Ouvrir dans Obsidian** : File > Open Vault > selectionner ce dossier
3. **Plugin Obsidian Git** : installer pour auto-sync (pull/push toutes les 5 min)
4. **Avant de vibecoder** : lire `CONTEXT.md` + la section pertinente

## Repos lies

- [foodmi/app](https://github.com/foodmi/app) -- App Flutter (iOS + Android)
- [foodmi/website](https://github.com/foodmi/website) -- Site marketing Next.js (actif)
- [foodmi/website2](https://github.com/foodmi/website2) -- Ancien site (archive)
