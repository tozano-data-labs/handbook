# Décisions d'architecture (ADR)

Un ADR documente une décision structurante : contexte, décision, conséquences.

## Format

```text
docs/adr/NNNN-titre-court.md
```

```markdown
# ADR NNNN — Titre

- **Statut** : proposé | accepté | remplacé
- **Date** : AAAA-MM-JJ

## Contexte

## Décision

## Conséquences
```

## Règles

- Un ADR est immuable une fois accepté ; on le remplace par un nouvel ADR.
- Les décisions structurantes : entrepôt, orchestrateur, format de stockage,
  outil de dataviz, stratégie de qualité.
- Lier l'ADR depuis la PR et le README concerné.
