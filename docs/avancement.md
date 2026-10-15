# Avancement

État du projet d'une session à l'autre. À lire au début de chaque session, à mettre à jour à la fin de chaque tâche. Les étapes sont celles de `docs/methode.md`.

Dernière mise à jour : 15 octobre 2026.

## Étape en cours

**Étape 3 : spécification.** Terminé quand une spec est dans le dépôt, découpée en lots livrables, et relue par Quentin.

Grill fait (décision 09, `CONTEXT.md`), spec écrite dans `.scratch/maximus-v1/spec.md`.

Prochaine action : Quentin relit la spec, puis `/to-tickets` dans la même session pour la découper en tickets.

## Fait

- **Étape 1 : dépôt, CLAUDE.md, décisions.** Dépôt QuentinOnly/maximus (compte pro), `CLAUDE.md`, décisions de cadrage dans `docs/decisions` (01 à 07), règle « jamais de tiret cadratin » dans les conventions.
- **Étape 2 : audit et installation des skills.**
  - Dix skills de mattpocock/skills (version 1.2.3) installés dans `.claude/skills/` : grill-with-docs, to-spec, to-tickets, prototype, implement, tdd, diagnosing-bugs, retro, setup-matt-pocock-skills, git-guardrails-claude-code.
  - Relecture du code par `/mattpocock-skills:code-review` (plugin), pour éviter la confusion avec la commande intégrée `/code-review`.
  - Écartés : handoff et logo-design (écrivent hors du projet), qa (n'existe plus).
  - Suivi des issues configuré en Markdown local (`.scratch/`), décisions dans `docs/decisions` (`docs/agents/`).
- **Méthode** reprise dans `docs/methode.md`, avec le skill à invoquer à chaque étape et à chaque temps du cycle.
- Claude Code à jour : version 2.1.300 (le cadrage demandait de mettre à jour la 2.1.114).
- **Grill du périmètre V1** : décision 09 (V1 complète sauf Khadidiatou, lancement manuel, aucun envoi de mail, migration avancée en étape 7, dossier de données `OneDrive - ONLYNNOV\maximus\` créé), glossaire `CONTEXT.md`, `CLAUDE.md` et `docs/methode.md` alignés.
- **Spec V1** écrite : `.scratch/maximus-v1/spec.md` (109 user stories, deux points de test : planificateur et API locale).
- **Points en suspens tranchés** (décision 08) : pas de handoff, logo-design désinstallé, règles Git écrites dans `CLAUDE.md` à la place du garde-fou, `.gitignore` créé (dépendances, secrets, données de Maximus).

## Reste à faire

Ordre révisé par la décision 09.

3. Spécification (en cours : relecture, puis tickets).
4. Copie Notion de Roadmap 2026.2, nouveau modèle de données, base Récurrences.
5. Moteur du matin, en lecture seule.
6. Écritures validées sur la copie, page brute de validation.
7. Migration de la base partagée.
8. Logo.
9. Tableau de bord local et raccourci du bureau.
10. Chat.
11. Débrief du soir.
12. Semaine d'essai sur la base partagée.

## Points en suspens

- **logo-design à réauditer à l'étape 8** avant toute réinstallation (désinstallé le 15 octobre).
- **Noms des dossiers de données** fixés par la décision 09 et repris dans le `.gitignore` (ancrés à la racine). Les revérifier si le moteur en ajoute.
- **Inconnues à mesurer dès l'étape 5** (décision 06) : quota d'usage, latence du chat, écriture en mode non interactif. Si l'écriture non interactive échoue, l'étape 6 bloque tout le reste.
- **Version des skills.** Les skills du dépôt sont figés en 1.2.3. Une mise à jour du plugin ne les change pas : refaire un audit avant de les remplacer.
