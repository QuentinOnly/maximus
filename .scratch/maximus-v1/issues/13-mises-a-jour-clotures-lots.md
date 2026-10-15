# 13: Mises à jour, clôtures et validation en lot

**Status:** ready-for-agent

**À construire :** Les propositions de mise à jour et de clôture d'une tâche existante s'écrivent après approbation. Les récurrences et les factures se valident en lot d'un clic.

**Bloqué par :** 12 (Premier tracé d'écriture : approuver crée la tâche), 07 (Factures), 09 (Récurrences)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Une proposition de mise à jour montre l'avant et l'après de chaque propriété
- [ ] Une clôture (Terminé à valider) ne s'écrit qu'après approbation
- [ ] Le bouton « Tout valider » d'un lot écrit chaque proposition du lot et affiche le résultat de chacune
- [ ] La tâche groupée des factures est mise à jour par le lot ; une fois terminée, la facture suivante crée une nouvelle tâche
- [ ] Les instances de récurrences approuvées sont créées dans la copie
- [ ] Tests de l'API : lot partiellement en échec, mise à jour d'une tâche modifiée entre-temps dans Notion
