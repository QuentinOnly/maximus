# Suivi des issues : Markdown local

Les specs et les issues de ce dépôt sont des fichiers Markdown dans `.scratch/`, versionnés avec le code. Rien n'est publié sur GitHub Issues.

## Conventions

- Un sujet par dossier : `.scratch/<sujet>/`
- La spec est `.scratch/<sujet>/spec.md`
- Les issues d'implémentation font un fichier par ticket : `.scratch/<sujet>/issues/<NN>-<slug>.md`, numérotés à partir de `01`, jamais un fichier unique regroupant tous les tickets
- L'état de triage est une ligne `Status:` en haut de chaque fichier d'issue (voir `triage-labels.md` pour les valeurs)
- Les commentaires et l'historique s'ajoutent en bas du fichier sous un titre `## Comments`

## Quand un skill dit « publier dans le suivi des issues »

Créer un nouveau fichier sous `.scratch/<sujet>/` (en créant le dossier si besoin).

## Quand un skill dit « récupérer le ticket concerné »

Lire le fichier au chemin indiqué. Quentin donne normalement le chemin ou le numéro de l'issue.

## Opérations de wayfinding

Utilisées par `/wayfinder`. La **carte** est un fichier, avec un fichier **enfant** par ticket.

- **Carte** : `.scratch/<chantier>/map.md` (corps Notes / Decisions-so-far / Fog).
- **Ticket enfant** : `.scratch/<chantier>/issues/NN-<slug>.md`, numéroté à partir de `01`, la question dans le corps. Une ligne `Type:` donne le type (`research`/`prototype`/`grilling`/`task`) ; une ligne `Status:` donne `claimed`/`resolved`.
- **Blocage** : une ligne `Blocked by: NN, NN` en haut. Un ticket est débloqué quand tous les fichiers listés sont `resolved`.
- **Front** : parcourir `.scratch/<chantier>/issues/` pour trouver les fichiers ouverts, non bloqués et non pris ; le plus petit numéro passe en premier.
- **Prise** : passer `Status: claimed` et enregistrer avant tout travail.
- **Résolution** : ajouter la réponse sous un titre `## Answer`, passer `Status: resolved`, puis ajouter un renvoi (résumé + lien) dans la section Decisions-so-far de `map.md`.
