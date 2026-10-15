# 15: Brouillons Outlook

**Status:** ready-for-agent

**À construire :** Un mail du couloir Action peut recevoir une proposition de réponse dans le style de Quentin. Après approbation, le brouillon est créé dans Outlook, dans le bon fil. Quentin l'envoie lui-même.

**Bloqué par :** 12 (Premier tracé d'écriture : approuver crée la tâche), 11 (Profil de style)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] La proposition de brouillon montre le texte, modifiable avant approbation
- [ ] Le brouillon est créé en réponse au bon fil, jamais envoyé
- [ ] Aucun outil d'envoi n'est transmis à aucun appel
- [ ] À l'analyse suivante, l'écart entre le brouillon et le mail réellement envoyé est noté dans `profil-style.md`
- [ ] Tests de l'API : brouillon créé, aucune demande d'envoi possible
- [ ] Vérification réelle : un brouillon visible dans Outlook dans le bon fil
