# 08: Wispr et fiches réunions

**Status:** ready-for-agent

**À construire :** Chaque transcript Wispr arrivé depuis la dernière analyse est analysé une seule fois et produit une fiche Markdown dans le dossier de données. Seules les actions de Quentin deviennent des propositions de tâche.

**Bloqué par :** 02 (Premier tracé : lancer l'analyse et voir l'agenda du jour)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Une fiche par réunion dans `reunions/`, avec résumé, décisions et actions de Quentin
- [ ] Les actions des autres participants ne sont ni retenues ni proposées
- [ ] Chaque action de Quentin devient une proposition de tâche, avec la source vers le transcript
- [ ] Un transcript déjà analysé n'est jamais réanalysé
- [ ] Les heures des transcripts (UTC) sont converties en heure de Paris
- [ ] Tests de l'API : transcript nouveau, transcript déjà analysé
