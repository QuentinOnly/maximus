# 23: Débrief du soir

**Status:** ready-for-agent

**À construire :** Quentin lance le débrief quand il s'y met. Il saisit statut, temps réel, heures restantes et ressentis ; les changements de tâches sont des propositions qu'il approuve. Étape 11.

**Bloqué par :** 18 (Coque QDM, écran Matin et raccourci du bureau), 13 (Mises à jour, clôtures et validation en lot)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Écran Soir conforme à la maquette : statut par tâche, graphique estimé contre réel, ressentis, reports, traces du jour
- [ ] Statut, temps réel et heures restantes deviennent des propositions de mise à jour, validées par Quentin
- [ ] Le journal du soir est enregistré dans `journal/` en Markdown
- [ ] Une réunion de plus de 30 minutes avec des externes sans transcript est signalée une fois
- [ ] Aucune notification, aucun lancement automatique
- [ ] Tests de l'API : débrief complet, réunion sans transcript signalée une seule fois
