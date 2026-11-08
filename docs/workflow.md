# Flux de travail

```text
Issue → Branche → PR → CI verte → Revue → Squash merge
```

## 1. Issue

- Une issue décrit le besoin, le périmètre et les critères d'acceptation.
- Utiliser les formulaires : Bug, Fonctionnalité, Qualité de données.

## 2. Branche

- Créer depuis `main` : `feat/…`, `fix/…`, `docs/…`, `chore/…`.
- Une branche = un sujet.

## 3. Pull request

- Même en travail solo, ouvrir une PR.
- Remplir le modèle de PR (contexte, changements, impact données, tests).
- Le titre suit le format de commit.

## 4. CI

- `ci-python`, `ci-dbt`, `docker-build` selon le dépôt.
- `dependency-review` et `pr-title` sur les PR.
- La CI doit être verte avant revue.

## 5. Revue et fusion

- Revue par un *trusted committer* (le propriétaire du dépôt).
- **Squash and merge** uniquement.
- **Aucun auto-merge**, Dependabot compris.
- Pas de force push sur `main`.

## Règles de protection

Configurer pour chaque dépôt :

- PR obligatoire avant `main` ;
- checks CI requis ;
- historique linéaire ;
- suppression de la branche après fusion.
