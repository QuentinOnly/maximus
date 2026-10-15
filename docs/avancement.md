# Avancement

État du projet d'une session à l'autre. À lire au début de chaque session, à mettre à jour à la fin de chaque tâche. Les étapes sont celles de `docs/methode.md`.

Dernière mise à jour : 15 octobre 2026.

## Étape en cours

**Étape 5 : moteur du matin, en lecture seule.** Premier ticket : `.scratch/maximus-v1/issues/02-premier-trace-analyse-agenda.md` (aucun blocage).

Prochaine action : ouvrir une nouvelle session, lire ce fichier, puis traiter le ticket 02. Les réglages de Notion (copie de test et base partagée) sont dans `reglages.json` du dossier de données ; toute écriture vise la copie.

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
- **Étape 3 : spécification.** Spec `.scratch/maximus-v1/spec.md` (deux points de test : planificateur et API locale), relue par Quentin, complétée par la décision 10 (garde-fous de l'analyse), découpée en 24 tickets dans `.scratch/maximus-v1/issues/` avec leurs blocages.
- **Étape 4 : copie Notion et nouveau modèle** (ticket 01, décision 11). Copie « Roadmap 2026.2 [TEST Maximus] » dans les pages privées de Quentin : Échéance renommée en Planifié le, nouvelles propriétés Échéance, Ferme, Impact, Estimation (h), Temps réel (h), Source ; Impact et Estimation remplis pour les 52 tâches de Quentin ; base Récurrences créée vide. Base partagée vérifiée intacte avant et après (empreinte identique).
- **Points en suspens tranchés** (décision 08) : pas de handoff, logo-design désinstallé, règles Git écrites dans `CLAUDE.md` à la place du garde-fou, `.gitignore` créé (dépendances, secrets, données de Maximus).

## Reste à faire

Ordre révisé par la décision 09. Tickets 01 à 24 dans `.scratch/maximus-v1/issues/`.

5. Moteur du matin, en lecture seule (en cours, ticket 02).
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
- **Limites du connecteur Notion sans l'offre Business** (décision 11) : pas de requête SQL sur plusieurs bases, requêtes SQL plafonnées, code des formules illisible. À mesurer à l'étape 5 ; l'adaptation des formules (ticket 16) passe par l'interface Notion.
- **Boutons « Création rapide » de la copie** : le connecteur ne les lit pas. Ne pas s'en servir tant que Quentin n'a pas vérifié dans Notion qu'ils créent bien dans la copie.
- **Statut des tickets terminés** : aucune valeur prévue dans `docs/agents/triage-labels.md` ; le ticket 01 porte `done`. À valider ou à remplacer.
- **Version des skills.** Les skills du dépôt sont figés en 1.2.3. Une mise à jour du plugin ne les change pas : refaire un audit avant de les remplacer.
