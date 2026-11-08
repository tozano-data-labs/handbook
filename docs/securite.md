# Sécurité

## Secrets

- `.env` n'est jamais commité ; seul `.env.example` l'est.
- Les secrets CI vivent dans les *GitHub Secrets*.
- Aucun identifiant en dur dans le code, les notebooks ou les fichiers compose.

## Dépendances

- `dependency-review` bloque les vulnérabilités de sévérité haute sur les PR.
- Dependabot ouvre des PR de mise à jour ; fusion manuelle uniquement.
- Les images Docker sont scannées par Trivy en CI.

## Signalement

- Ne jamais publier une faille dans une issue publique.
- Utiliser **Security → Report a vulnerability** du dépôt concerné.
- Voir `SECURITY.md` du dépôt `.github` de l'organisation.

## Bonnes pratiques

- Principe du moindre privilège pour les tokens et les accès aux sources.
- Journaux sans donnée personnelle ni secret.
- Revue systématique de tout code qui touche à l'authentification ou aux accès.
