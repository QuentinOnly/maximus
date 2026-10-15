# 10: Traçabilité

**Status:** ready-for-agent

**À construire :** Chaque analyse enregistre des traces datées des actions réglées dans Notion, Outlook, OneDrive et SharePoint, rattachées à un projet ou un interlocuteur.

**Bloqué par :** 02 (Premier tracé : lancer l'analyse et voir l'agenda du jour)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Les traces OneDrive et SharePoint viennent du dossier synchronisé `OneDrive - ONLYNNOV`, en nom, chemin et date de modification seulement, sans lecture du contenu ni attribution d'auteur
- [ ] Le rattachement au client ou au projet se fait par le dossier
- [ ] Une liste d'exclusion dans `reglages.json` écarte les fichiers sensibles (par défaut `Logins*`)
- [ ] Les traces Notion et Outlook (tâches modifiées, mails envoyés) sont enregistrées dans `memoire/`
- [ ] Les traces se retrouvent par projet ou par interlocuteur via l'API
- [ ] Tests de l'API : fichier exclu absent, trace rattachée au bon projet
