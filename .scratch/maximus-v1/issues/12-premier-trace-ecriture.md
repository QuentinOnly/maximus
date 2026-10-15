# 12: Premier tracé d'écriture : approuver crée la tâche

**Status:** ready-for-agent

**À construire :** Dans la page brute, Quentin approuve, rejette ou corrige une proposition de tâche. Une approbation crée la tâche dans la copie Notion. Ce ticket lève l'inconnue de l'écriture en mode non interactif : à traiter avant tout autre ticket de l'étape 6. Étape 6.

**Bloqué par :** 01 (Copie de Roadmap 2026.2 au nouveau modèle), 05 (Mails reçus en couloirs)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Les propositions ont un cycle de vie : en attente, approuvée, rejetée, écrite, en échec
- [ ] Approuver déclenche un appel `claude -p` distinct, qui ne reçoit que l'outil d'écriture nécessaire
- [ ] L'écrivain refuse toute demande qui ne vient pas d'une proposition approuvée ; il n'existe aucune opération d'envoi de mail
- [ ] Quentin peut corriger une propriété avant d'approuver ; l'estimation accepte les raccourcis XS, S, M, L
- [ ] Une proposition rejetée ne revient pas à l'analyse suivante
- [ ] Une écriture en échec est affichée avec sa raison et peut être relancée
- [ ] La tâche est créée dans la copie, jamais dans la base partagée
- [ ] Tests de l'API avec écrivain simulé : aucune écriture sans approbation, rejet mémorisé, échec puis relance
- [ ] Vérification réelle : une tâche créée dans la copie après le clic de Quentin
