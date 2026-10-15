# 07: Factures

**Status:** ready-for-agent

**À construire :** Les factures reçues par mail sont repérées par leur contenu. Celles d'un expéditeur de la liste validée deviennent des propositions de mise à jour de la tâche groupée « Factures à déposer ». Les autres deviennent des « Factures à vérifier » (décision 10).

**Bloqué par :** 05 (Mails reçus en couloirs)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Détection par contenu (facture ou invoice, avec un PDF ou un lien de téléchargement)
- [ ] Au premier lancement, une liste d'expéditeurs est amorcée sur les trois derniers mois et proposée à Quentin pour validation
- [ ] Une facture d'un expéditeur validé devient une proposition de mise à jour de la tâche groupée (compteur, lien, échéance au jour même), ou de création si aucune tâche n'est ouverte
- [ ] Une facture d'un expéditeur hors liste devient une proposition « Facture à vérifier », qui n'atteint jamais la tâche groupée sans décision
- [ ] Sur une facture à vérifier, Quentin peut l'ajouter à la tâche (et l'expéditeur à la liste) ou l'écarter
- [ ] Les mails de facture sortent des couloirs
- [ ] La liste validée vit dans `reglages.json` du dossier de données
- [ ] Tests de l'API : expéditeur validé, expéditeur inconnu, tâche groupée terminée puis nouvelle facture
