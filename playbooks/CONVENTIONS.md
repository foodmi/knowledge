# Conventions de Code

## Flutter / Dart

### Nommage
- Fichiers : `snake_case.dart`
- Classes : `PascalCase`
- Variables/fonctions : `camelCase`
- Constantes : `camelCase` (pas UPPER_SNAKE)
- Providers : suffix `Provider` (ex: `authProvider`)

### Patterns
- Un fichier par classe/widget
- Exports via barrel files (`widgets.dart`, `models.dart`)
- Pas de logique metier dans les widgets
- Providers pour tout etat partage
- Repository pattern pour acces donnees

### Regles
- Pas de commentaires sauf si le POURQUOI est non-evident
- Pas de docstrings sauf demande explicite
- Pas de code mort ou shims de compatibilite
- Pas de validation pour scenarios impossibles

## Next.js / TypeScript

### Nommage
- Composants : `PascalCase.tsx`
- Utilitaires : `camelCase.ts`
- Dossiers : `kebab-case`

## Git

### Branches
```
main              -> Production, toujours deployable
[prenom]/[tache]  -> Branche par tache, par personne

Exemples :
adam/fix-ios-bundle-id
adam/deploy-vercel
karim/aso-screenshots
```

### Commits
- Messages courts, descriptifs, en anglais
- Format : `type: description`
- Types : `fix`, `feat`, `chore`, `docs`, `refactor`

### PRs
- Une branche = une tache = une PR
- Review en <2h pendant l'overlap
- Supprimer la branche apres merge

## Verification code IA

Avant de deployer du code genere par un agent :
1. **COMPILE** : `flutter analyze` / `bun run build`
2. **DIFF** : `git diff` -- lire chaque ligne
3. **TEST** : `flutter test` ou test manuel
4. **SENSE CHECK** : les deps existent ? les URLs sont reelles ?
