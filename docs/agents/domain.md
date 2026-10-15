# Documentation du domaine

Comment les skills d'ingénierie lisent la documentation du domaine de ce dépôt quand ils explorent le code.

Disposition : **un seul contexte**. Les décisions vivent dans **`docs/decisions/`**, pas dans `docs/adr/`.

## Avant d'explorer, lire

- **`CONTEXT.md`** à la racine (le glossaire du projet).
- **`docs/decisions/`** : lire l'index `README.md`, puis les décisions qui touchent la zone de travail.

Si un de ces fichiers n'existe pas, **continuer sans le signaler**. Le skill `/domain-modeling` (appelé par `/grill-with-docs` et `/improve-codebase-architecture`) les crée au moment où un terme ou une décision est tranché.

## Structure

```
/
├── CONTEXT.md
├── docs/decisions/
│   ├── README.md                     ← index, à tenir à jour
│   ├── 01-objectif-et-perimetre.md
│   ├── ...
│   └── 07-plan-de-construction.md
└── src/
```

## Écrire une décision (remplace le format ADR par défaut)

Partout où un skill dit « créer un ADR dans `docs/adr/` » :

- l'écrire dans `docs/decisions/` ;
- le numéroter à la suite des fichiers existants, sur deux chiffres : `08-slug.md`, `09-slug.md`, etc. (slug en français, sans accents) ;
- garder le gabarit court du skill (titre, puis une à trois phrases : contexte, décision, raison), en français ;
- ajouter une ligne pour ce fichier dans l'index `docs/decisions/README.md`.

Une décision qui en remplace une autre ne réécrit pas l'ancienne en silence : la nouvelle la cite, et l'ancienne reçoit une ligne « Remplacée par NN ».

## Employer le vocabulaire du glossaire

Quand une production nomme un concept du domaine (titre d'issue, proposition de refactorisation, hypothèse, nom de test), utiliser le terme tel que défini dans `CONTEXT.md`. Ne pas dériver vers les synonymes que le glossaire écarte.

Si le concept n'est pas encore dans le glossaire, c'est un signal : soit on invente un langage que le projet n'emploie pas (à reconsidérer), soit il y a un vrai manque (à noter pour `/domain-modeling`).

## Signaler les contradictions

Si une production contredit une décision existante, le dire explicitement plutôt que la contourner :

> _Contredit la décision 04 (architecture technique), mais mérite d'être rouverte parce que…_
