# 19: Écran Semaine et « Planifier la semaine »

**Status:** ready-for-agent

**À construire :** Un kanban de la semaine (À planifier puis une colonne par jour avec sa jauge) et un bouton « Planifier la semaine » qui produit un plan sous forme de propositions groupées par jour.

**Bloqué par :** 18 (Coque QDM, écran Matin et raccourci du bureau), 14 (Créneaux dans l'agenda)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Colonnes À planifier puis une par jour ouvré, chacune avec sa jauge de charge et une alerte de surcharge
- [ ] « Planifier la semaine » produit des propositions groupées par jour (Planifié le et créneaux)
- [ ] Une carte se déplace d'un jour à l'autre avant validation
- [ ] Validation par jour, par semaine ou par tâche
- [ ] Le recalcul quotidien ne propose que les écarts au plan validé
- [ ] Tests du planificateur et de l'API : plan de semaine, écarts après un rendez-vous ajouté
