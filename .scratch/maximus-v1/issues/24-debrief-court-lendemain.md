# 24: Débrief court du lendemain matin

**Status:** ready-for-agent

**À construire :** Si le débrief de la veille n'a pas été fait, l'écran Matin propose en tête un débrief court (statut et temps réel), que Quentin peut passer.

**Bloqué par :** 23 (Débrief du soir)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Le débrief court apparaît seulement si celui de la veille manque
- [ ] Il ne demande que le statut et le temps réel des tâches de la veille
- [ ] Le passer ne change rien aux tâches et ne clôt rien
- [ ] Le Top 3 du jour est calculé après le débrief court s'il est fait
- [ ] Tests de l'API : débrief manquant, débrief passé
