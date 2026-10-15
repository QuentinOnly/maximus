# 03: Capacité et journée planifiée

**Status:** ready-for-agent

**À construire :** Après l'analyse, la page brute montre la capacité du jour, les heures libres et une journée planifiée à 70 % à partir des tâches de la copie Notion. Le planificateur est un module pur, testé en profondeur.

**Bloqué par :** 01 (Copie de Roadmap 2026.2 au nouveau modèle), 02 (Premier tracé : lancer l'analyse et voir l'agenda du jour)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Le planificateur prend une photo du jour (tâches, rendez-vous, heure exacte, horaires) et ne fait aucun accès réseau ni lecture d'horloge implicite
- [ ] Horaires : lundi 9 h à 12 h et 13 h 30 à 17 h ; mardi à vendredi 9 h à 12 h 30 et 13 h 30 à 18 h
- [ ] Heures libres = horaires moins rendez-vous, calculées sur l'heure ; seules 70 % sont planifiées
- [ ] Une tâche sans échéance prend la fin de sa plage comme échéance souple
- [ ] La jauge de capacité suit les seuils de la décision 05 (neutre sous 50 %, ambre de 50 à 80 %, rouge au-delà)
- [ ] Tests du planificateur : lundi contre mardi, rendez-vous qui chevauche la pause, rendez-vous terminé, journée pleine, tâche sans échéance
- [ ] Les tâches sont lues dans la copie Notion, jamais dans la base partagée
