# Conventions

## Structure d'un dépôt de données

```text
.
├── pipelines/        # ingestion Python (src/ + tests/)
├── transformation/   # dbt (staging, marts)
├── dataviz/          # dashboards
├── infra/            # Docker, déploiement
├── docs/             # architecture, ADR, qualité
└── .github/          # CI, Dependabot
```

## Python

- Python 3.12, typage explicite des fonctions publiques.
- `ruff` pour le lint et le format, longueur de ligne 100.
- `pytest`, couverture minimale de 80 % (90 % sur la logique métier).
- Pas d'import relatif fragile ; code dans `src/<package>/`.

## SQL / dbt

- Couches `raw → staging → marts`, jamais de saut de couche.
- `snake_case`, une colonne `ingested_at` en staging.
- Tests `not_null` et `unique` sur les clés.
- Un modèle = une intention documentée dans `schema.yml`.

## Nommage

| Élément | Convention | Exemple |
| --- | --- | --- |
| Branche | `type/scope-court` | `feat/ingestion-transport` |
| Modèle staging | `stg_<source>` | `stg_transport` |
| Table mart | `fct_` / `dim_` | `fct_trajets`, `dim_commune` |
| Fichier de test | `test_<module>.py` | `test_ingestion.py` |

## Documentation

- Chaque dépôt a un `README.md` avec rôle, structure et commandes.
- Toute décision structurante devient un ADR dans `docs/adr/`.
- Les schémas d'architecture sont en Mermaid quand c'est pertinent.
