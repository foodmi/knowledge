# Protocole d'equipe -- TDAH + Async + Anti-burnout

## Principes

1. **KISS** : si un outil prend >2h a setup, on fait manuellement
2. **Async-first** : tout passe par l'ecrit, zero meeting obligatoire sauf standup
3. **Micro-taches** : chaque tache = 15-30 min max, sinon la decouper
4. **6h max/jour** : de travail reel (timer Pomodoro = source de verite)

## Pomodoro TDAH-friendly

```
25 min FOCUS  -> 1 micro-tache
 5 min BREAK  -> ce que tu veux, zero culpabilite
25 min FOCUS  -> tache suivante
 5 min BREAK
25 min FOCUS  -> tache suivante
15 min LONG BREAK -> sortir, bouger, manger

= 3 taches par cycle de ~2h
= 6-9 taches par jour
```

Si une tache prend plus de 25 min, elle est trop grosse -> la decouper.

## Standup quotidien

- **Quand** : 15h30 Paris / 9h30 Montreal (15 min)
- **Format** : texte ou vocal (PAS video)
- **Structure** :
  1. Ce que j'ai fini hier (liste de taches)
  2. Ce que je fais aujourd'hui (max 3 taches)
  3. Ce qui me bloque (0 ou 1 truc)

Si quelqu'un est pas la, il poste son standup en texte.

## Handoff (fin de journee)

```markdown
## Handoff [Prenom] -- [Date] [Heure]

### Fait aujourd'hui
- [x] Tache 1 (commit: abc123)
- [x] Tache 2 (PR #12)
- [ ] Tache 3 (en cours, 70%)

### Etat du code
- Branche : main (clean / WIP)
- Build : passe / casse (pourquoi)

### Pour demain / pour [prenom]
- Continuer tache 3 : ouvrir fichier X, faire Y
- Attention : Z est casse, ne pas toucher

### Questions en attente
- Est-ce qu'on garde AdMob pour le launch ?
```

## Regles de communication

- **Jamais** de "tu es la ?" -- envoyer le message complet d'un coup avec contexte + question
- **Pas de guilt** si une tache n'est pas finie
- **INBOX.md** pour dumper les idees tangentes (trier en fin de journee)

## Signal d'alerte burnout

Si 3 de ces signaux sont vrais en meme temps -> 24h off, non-negociable :
- Dormi <6h deux nuits de suite
- Procrastination sur des taches faciles
- Irritable a l'ecrit
- Travail le soir/nuit "pour rattraper"
- Pas bouge physiquement depuis 2 jours
- Boule dans le ventre quand tu ouvres le laptop

## Git

- **main** = production, toujours deployable
- Branches : `[prenom]/[tache]` (ex: `adam/fix-bundle-id`, `karim/aso-screenshots`)
- Une branche = une tache du sprint
- PR quand c'est fini, review en <2h pendant l'overlap
- Supprimer la branche apres merge

## Stack outils

| Besoin | Outil |
|--------|-------|
| Code | Git + GitHub |
| Agent IA | OpenCode / Claude (compte perso chacun) |
| Contexte partage | Ce repo (Obsidian + Git) |
| Communication | Telegram ou Discord (1 channel) |
| Taches | [[roadmap/BOARD]] |
| CI/CD | GitHub Actions |
| Deploy site | Vercel |
| Backend | Supabase |
| Monetisation | RevenueCat |
| Timer TDAH | Pomofocus.io |

## Body doubling avec Claude

Quand tu bosses seul, ouvre un agent Claude et dis-lui ce que tu fais. Il devient ton body double :

```
"Je commence la tache W2 (deployer sur Vercel).
 Je vais d'abord push le code sur GitHub.
 Rappelle-moi si je diverge."
```
