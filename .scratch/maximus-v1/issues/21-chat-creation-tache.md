# 21: Bulle de chat et création de tâche

**Status:** ready-for-agent

**À construire :** Une bulle en bas à droite ouvre un panneau de chat. Une demande en langage naturel produit une carte de proposition ; seul le clic sur la carte écrit. Étape 10.

**Bloqué par :** 18 (Coque QDM, écran Matin et raccourci du bureau), 12 (Premier tracé d'écriture : approuver crée la tâche)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Chaque message relance Claude Code en reprenant la session du jour ; les conversations précédentes sont archivées dans `chat/`
- [ ] Une demande de tâche produit une carte de proposition avec les propriétés pré-remplies, Approuver et Rejeter
- [ ] Taper « oui » n'écrit jamais rien
- [ ] Les appels du chat suivent la même liste blanche que l'analyse ; l'écriture passe par l'écrivain
- [ ] La latence par message est mesurée et notée dans `docs/avancement.md`
- [ ] Tests de l'API : demande de tâche, « oui » tapé sans effet
