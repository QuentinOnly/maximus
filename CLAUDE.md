# Maximus

Agent de planification personnel de Quentin (Onlynnov) : ne rien perdre, ne rien oublier, ne plus planifier à la main. Les décisions de cadrage complètes sont dans [docs/decisions](docs/decisions/README.md) ; ce fichier en est le résumé opérationnel.

## Ce que fait Maximus

- Lit Outlook (mails et agenda), Notion, OneDrive, SharePoint et Wispr Flow.
- Chaque matin (8 h 30 à 9 h, lancé à l'ouverture de session Windows) : propose une journée planifiée selon la capacité réelle, un Top 3 sans ex aequo, et les tâches à créer.
- Transforme chaque entrée (mail, engagement envoyé, transcript Wispr, demande dans le chat) en tâche Notion complète, après validation.
- Chaque soir : débrief (statut, temps réel, heures restantes, ressentis).

Critère de réussite : aucune tâche créée à la main, rien d'oublié, un agenda juste.

## Règles non négociables

- **Zéro euro de dépense supplémentaire.** Pas d'hébergement, pas d'API facturée, pas de Vercel (l'offre gratuite exclut l'usage commercial).
- **L'agent propose, Quentin valide.** Aucune écriture sans clic, aucune modification d'une tâche existante sans accord, aucune clôture automatique, aucun mail envoyé sans validation.
- En mode automatique : lecture et préparation seulement. Toute écriture part de l'interface après un clic.
- Le statut lu / non lu d'un mail n'est pas un signal.
- Chaque lancement transmet l'heure exacte et le fuseau Europe/Paris ; filtrer sur l'heure, pas seulement sur la date.
- Notion « Roadmap 2026.2 » est la source de vérité des tâches. Tout changement de modèle se teste d'abord sur une copie de la base, jamais directement sur la base partagée de l'équipe.

## Architecture

- **Moteur** : Claude Code natif Windows, appelé en mode non interactif (`claude -p`).
- **Connecteurs** : connecteurs claude.ai (Microsoft 365, Notion, Wispr Flow) ; les inutiles désactivés pour le contexte.
- **Déclenchement** : tâche planifiée Windows à l'ouverture de session, plus relance manuelle.
- **Interface** : application web locale Node.js v24, React, Tailwind, shadcn/ui, habillée avec le design system QDM. Grand écran, lisible sur un portable 15 pouces, pas de mobile.
- **Chat** : chaque message relance Claude Code en reprenant la session du jour.
- **Données** : tâches dans Notion ; fiches réunions, journal du soir, profil de style, mémoire de traitement et historique du chat en `.md` et JSON dans un dossier OneDrive.

## Concepts clés

- **Urgence** (échéance, ferme ou souple) est séparée de l'**importance** (propriété Impact : Faible, Moyen, Fort, qui remplace Priorité).
- Planification à 70 % des heures libres. Capacité : lundi 9 h–12 h et 13 h 30–17 h ; mardi à vendredi 9 h–12 h 30 et 13 h 30–18 h.
- **Pression** d'une tâche longue = heures restantes / heures libres avant la fin de plage. Au-delà de 50 %, elle remonte dans le Top 3.
- Mails triés en trois couloirs : Action, À surveiller, Écartés avec raison.
- Agenda : créneaux de production en « disponible » par défaut, « occupé » si échéance ferme menacée ou impact fort.

## Interface

Maquette v2 validée (Matin, Soir, Semaine) sur le canvas [Maximus](https://claude.ai/artifact/2MP2ZsaUTHsoQ8YRaWCX5z). Code couleur des statuts et jauges : voir [05-interface.md](docs/decisions/05-interface.md). Le bleu est réservé à ce qui est cliquable ; chaque couleur est doublée d'une icône et d'un libellé. Titres factuels, aucune formule de type IA.

## Ordre de construction

Le moteur passe avant l'interface : une interface sans données réelles ne se teste pas. Voir [07-plan-de-construction.md](docs/decisions/07-plan-de-construction.md).

## Langue

Documentation, interface et messages en français.
