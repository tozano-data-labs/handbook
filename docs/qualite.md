# Qualité

## Principe

Aucun changement n'est livré sans test exécuté.

## Seuils

| Périmètre | Seuil |
| --- | --- |
| Couverture globale | 80 % |
| Logique métier | 90 % |
| Tests de qualité de données | obligatoires sur les marts |

## Tests attendus

- **Unitaires** : fonctions Python d'ingestion et de transformation.
- **dbt** : `not_null`, `unique`, relations, plages de valeurs.
- **Qualité de données** : complétude, unicité, fraîcheur, cohérence, volume.
- **Docker** : build reproductible, scan Trivy sans vulnérabilité critique.

## Definition of Done

- [ ] Tests ajoutés ou mis à jour, CI verte
- [ ] Documentation mise à jour (README, schéma, ADR si nécessaire)
- [ ] Aucun secret ni donnée personnelle réelle dans le diff
- [ ] Titre de PR conforme au format de commit
- [ ] Impact sur les marts et dashboards évalué

## Commandes locales

```bash
# Python
ruff check . && ruff format --check . && pytest --cov

# dbt
dbt deps && dbt parse --profiles-dir . && dbt build --profiles-dir .

# Docker
docker build -t pipeline:test .
```
