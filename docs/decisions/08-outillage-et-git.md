# Outillage et règles Git

15 octobre 2026. Tranche quatre points en suspens de `docs/avancement.md`.

- **Pas de handoff.** Le passage d'une session à l'autre repose uniquement sur `docs/avancement.md` et la phrase d'ouverture de `docs/methode.md`. Raison : le skill écrit hors du projet, et le fichier d'avancement suffit.
- **logo-design désinstallé** du compte de Quentin. Il sera réaudité à l'étape 7 (logo) avant toute réinstallation. Raison : ses scripts écrivent hors du projet et lancent Chrome en arrière-plan.
- **Pas de garde-fou Git** (`/git-guardrails-claude-code` reste installé mais inactif). À la place, des règles écrites dans `CLAUDE.md` : jamais de `git push --force`, jamais de suppression de branche, jamais de réécriture de l'historique, `git push` uniquement à la demande de Quentin. Raison : le garde-fou bloquerait aussi les push voulus et dépend de `jq`, absent du poste.
- **`.gitignore` créé dès maintenant** : dépendances, fichiers d'environnement et secrets, et tous les dossiers de données de Maximus (fiches réunions, journal, profil de style, mémoire, historique du chat, exports de mails, transcripts). Raison : aucune donnée ne doit arriver sur GitHub, même par erreur avant la première session de code.
