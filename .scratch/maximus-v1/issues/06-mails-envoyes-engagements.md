# 06: Mails envoyés : engagements et sujets réglés

**Status:** ready-for-agent

**À construire :** Un engagement pris dans un mail envoyé (« c'est noté », « je reviens vers vous ») devient une proposition de tâche. Une réponse envoyée qui règle un sujet devient une proposition de tâche Terminé à valider.

**Bloqué par :** 05 (Mails reçus en couloirs)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Les Éléments envoyés depuis la dernière analyse sont lus
- [ ] Un engagement produit une proposition de tâche avec la source vers le mail envoyé
- [ ] Une réponse qui règle le sujet produit une proposition « Terminé à valider » liée à la tâche ou au mail d'origine
- [ ] Aucune clôture n'a lieu sans approbation
- [ ] Tests de l'API avec sorties simulées : engagement, sujet réglé, mail envoyé déjà traité
