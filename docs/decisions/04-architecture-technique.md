# Architecture technique

Tout tourne en local sur le portable Windows de Quentin, sur son siège Claude Team, sans hébergement ni API facturée.

| Brique | Choix |
|---|---|
| Moteur | Claude Code en natif Windows (version 2.1.114, à mettre à jour) |
| Connecteurs | Connecteurs claude.ai synchronisés : Microsoft 365, Notion, Wispr Flow. Les inutiles sont désactivés pour le contexte |
| Déclenchement | Tâche planifiée Windows à l'ouverture de session, plus relance manuelle |
| Interface | Application web Node.js (v24) servie en local, React, Tailwind et shadcn/ui habillés avec le design system QDM |
| Actions | Déléguées à Claude Code en mode non interactif. En automatique : lecture et préparation seulement ; toute écriture part de l'interface après clic |
| Chat | Chaque message relance Claude Code en reprenant la session du jour. Latence de quelques secondes par message |
| Données | Tâches dans Notion. Fiches réunions, journal du soir, profil de style, mémoire de traitement et historique du chat en .md et JSON dans un dossier OneDrive |
| Code | Dépôt GitHub de l'organisation Onlynnov |
| Heure | Chaque lancement transmet l'heure exacte et le fuseau de Paris |

Tests réalisés le 15 octobre 2026 :

1. Mode interactif : Outlook (mails et agenda), Notion et Wispr répondent en un seul passage d'environ 30 secondes. Anomalie relevée : un événement déjà terminé listé comme « prochain », filtre sur la date au lieu de l'heure.
2. Mode automatique (`claude -p`) : Outlook lu sans fenêtre et sans blocage de permission, heure de Paris correcte.

Vercel n'est pas retenu : l'offre gratuite exclut tout usage commercial, y compris un outil interne développé par un salarié.

Déclenchement : remplacé par la 09, lancement manuel depuis l'application, plus de tâche planifiée Windows.
