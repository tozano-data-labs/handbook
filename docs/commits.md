# Commits et titres de PR

Format obligatoire :

```text
<gitmoji> <type>(<scope>): <description en anglais>
```

- Impératif, sans point final, **72 caractères maximum**.
- Un changement logique par commit.
- Le titre de PR devient le message de commit au squash merge.

## Types autorisés

| Gitmoji | Type | Usage |
| --- | --- | --- |
| ✨ | `feat` | Nouvelle fonctionnalité |
| 🐛 | `fix` | Correction de bug |
| 📚 | `docs` | Documentation |
| ♻️ | `refactor` | Refonte sans changement de comportement |
| ✅ | `test` | Tests |
| 🔧 | `chore` | Maintenance, configuration |
| 🔒 | `security` | Sécurité |
| 🚑 | `ci` | Intégration continue |
| 📦 | `build` | Build, Docker, dépendances de build |
| ⏪ | `revert` | Annulation |

## Scopes usuels

`ingestion`, `orchestration`, `dbt`, `quality`, `dataviz`, `infra`, `docker`,
`deps`, `docs`, `ci`.

## Exemples

```text
✨ feat(ingestion): add open data transport source
🐛 fix(dbt): deduplicate staging rows
📚 docs(adr): document warehouse choice
🚑 ci(docker): pin trivy action version
```

## Vérification

`pr-title.yml` (via `shared-workflows`) exécute `scripts/check-pr-title.mjs`.
Chaque dépôt conserve une copie alignée de ce script.
