# Avancement

État du projet d'une session à l'autre. À lire au début de chaque session, à mettre à jour à la fin de chaque tâche. Les étapes sont celles de `docs/methode.md`.

Dernière mise à jour : 15 octobre 2026.

## Étape en cours

**Étape 3 : spécification.** Terminé quand une spec est dans le dépôt, découpée en lots livrables, et relue par Quentin.

Prochaine action : ouvrir une nouvelle session et lancer `/grill-with-docs` sur le périmètre de la V1, mode plan désactivé. Prolonger la même session par `/to-spec`, puis `/to-tickets`.

## Fait

- **Étape 1 : dépôt, CLAUDE.md, décisions.** Dépôt QuentinOnly/maximus (compte pro), `CLAUDE.md`, décisions de cadrage dans `docs/decisions` (01 à 07), règle « jamais de tiret cadratin » dans les conventions.
- **Étape 2 : audit et installation des skills.**
  - Dix skills de mattpocock/skills (version 1.2.3) installés dans `.claude/skills/` : grill-with-docs, to-spec, to-tickets, prototype, implement, tdd, diagnosing-bugs, retro, setup-matt-pocock-skills, git-guardrails-claude-code.
  - Relecture du code par `/mattpocock-skills:code-review` (plugin), pour éviter la confusion avec la commande intégrée `/code-review`.
  - Écartés : handoff et logo-design (écrivent hors du projet), qa (n'existe plus).
  - Suivi des issues configuré en Markdown local (`.scratch/`), décisions dans `docs/decisions` (`docs/agents/`).
- **Méthode** reprise dans `docs/methode.md`, avec le skill à invoquer à chaque étape et à chaque temps du cycle.
- Claude Code à jour : version 2.1.300 (le cadrage demandait de mettre à jour la 2.1.114).

## Reste à faire

3. Spécification (en cours).
4. Copie Notion de Roadmap 2026.2 et nouveau modèle de données, plus la base Récurrences.
5. Moteur du matin, en lecture seule.
6. Écritures validées.
7. Logo.
8. Tableau de bord local.
9. Chat.
10. Débrief du soir et tâche planifiée.
11. Semaine d'essai, puis migration de la base partagée.

## Points en suspens

- **Changement de session sans handoff.** Le skill est écarté, le passage repose sur ce fichier. À trancher : s'en contenter, ou créer une version de handoff qui écrit dans le dépôt.
- **Logo (étape 7) sans skill.** logo-design est écarté du projet mais reste installé pour le compte de Quentin. À trancher avant l'étape 7 : le désinstaller, ou l'accepter tel quel pour cette seule étape.
- **Garde-fou git non activé.** `/git-guardrails-claude-code` bloquerait aussi `git push` et demande `jq`, absent du poste. À décider avant la première session de code.
- **`.gitignore` à créer** dès la première session de code, pour qu'aucune donnée (mail, transcript, fiche réunion) n'arrive sur GitHub.
- **Deux plans de construction.** `docs/decisions/07-plan-de-construction.md` (10 lignes) et les 11 étapes de `docs/methode.md` ne sont pas découpés pareil. La méthode fait foi pour l'ordre ; le fichier 07 est à aligner (ou à marquer comme remplacé).
- **Version des skills.** Les skills du dépôt sont figés en 1.2.3. Une mise à jour du plugin ne les change pas : refaire un audit avant de les remplacer.
