Status: ready-for-agent

# Spec : Maximus V1

Issue du grill du 15 octobre 2026. Décisions de référence : `docs/decisions/01` à `09` (la 09 fait foi en cas d'écart). Vocabulaire : `CONTEXT.md`.

## Problème

Quentin perd des tâches : un mail laissé de côté descend dans la boîte et s'oublie, un engagement pris dans une réponse (« c'est noté ») ne laisse aucune trace, les actions décidées en réunion restent dans les transcripts Wispr. Créer chaque tâche dans Notion avec toutes ses propriétés lui prend du temps, et il planifie ses journées à la main, sans mesure de sa capacité réelle. Trop de tâches sont marquées prioritaires : l'urgence et l'importance sont confondues, et rien ne signale qu'une tâche longue est en train de déraper. Son agenda ne reflète pas le travail réellement prévu.

## Solution

Une application locale, ouverte depuis un raccourci du bureau. Quand Quentin lance l'analyse, Maximus lit ses mails, son agenda, Notion, Wispr, OneDrive et SharePoint, puis prépare des propositions : tâches à créer, mises à jour, créneaux à poser, brouillons de réponse, instances de récurrences, factures à déposer. Il calcule une journée planifiée selon la capacité réelle, un Top 3 sans ex aequo et la pression des tâches longues. Rien n'est écrit nulle part avant un clic de Quentin. Le soir, à sa demande, un débrief enregistre le statut et le temps réel des tâches pour calibrer les estimations. Un écran Semaine planifie les jours suivants, et un chat permet de créer une tâche en langage naturel ou de retrouver une action passée.

Critère de réussite : aucune tâche créée à la main, rien d'oublié, un agenda juste.

## User stories

### Lancement et analyse

1. En tant que Quentin, je veux ouvrir Maximus depuis un raccourci du bureau, afin de ne rien avoir à démarrer à la main dans un terminal.
2. En tant que Quentin, je veux voir l'heure de la dernière analyse dès l'ouverture, afin de savoir si ce que j'ai sous les yeux est à jour.
3. En tant que Quentin, je veux lancer l'analyse moi-même par un bouton, afin que rien ne tourne sans moi.
4. En tant que Quentin, je veux voir que l'analyse est en cours et ce qu'elle lit, afin de patienter sans me demander si elle est bloquée.
5. En tant que Quentin, je veux que l'analyse utilise l'heure exacte de Paris au moment du lancement, afin qu'un rendez-vous déjà passé ne soit jamais présenté comme à venir.
6. En tant que Quentin, je veux que la première analyse de ma vie avec Maximus lise les mails depuis le dernier jour ouvré à 8 h 30, afin de ne pas être noyé sous un balayage de tout l'historique.
7. En tant que Quentin, je veux que chaque analyse reprenne exactement à l'heure de la précédente, afin que rien ne passe entre deux analyses.
8. En tant que Quentin, je veux qu'au retour d'une absence tout ce qui est arrivé soit traité et présenté trié par urgence, afin de ne rien perdre sans lire un résumé à ma place.
9. En tant que Quentin, je veux qu'une relance en cours de journée ne traite que les nouveautés et me propose les écarts au plan, afin de ne pas voir mon Top 3 changer sans raison.
10. En tant que Quentin, je veux pouvoir demander explicitement de refaire le Top 3, afin de reprendre la main quand ma journée a basculé.
11. En tant que Quentin, je veux qu'une analyse qui échoue sur une source me le dise et continue avec les autres, afin d'avoir quand même ma journée.
12. En tant que Quentin, je veux voir l'état de chaque source (lue, en erreur, non configurée), afin de savoir sur quoi repose l'analyse.

### Mails

13. En tant que Quentin, je veux que chaque mail reçu soit classé dans un couloir (Action, À surveiller, Écarté), afin de ne plus fouiller ma boîte.
14. En tant que Quentin, je veux que chaque mail écarté porte sa raison, afin de pouvoir vérifier que Maximus n'a rien jeté à tort.
15. En tant que Quentin, je veux que le statut lu ou non lu ne compte pas, afin qu'un mail ouvert puis oublié soit traité comme les autres.
16. En tant que Quentin, je veux que tous les dossiers de ma boîte soient lus, courrier indésirable compris, afin qu'un mail mal classé par Outlook ne se perde pas.
17. En tant que Quentin, je veux que les éléments supprimés soient ignorés, afin que ce que j'ai jeté ne revienne pas.
18. En tant que Quentin, je veux qu'un mail du couloir Action devienne une proposition de tâche complète, afin de ne plus saisir de tâche à la main.
19. En tant que Quentin, je veux qu'un engagement pris dans un mail envoyé (« c'est noté », « je reviens vers vous ») devienne une proposition de tâche, afin de tenir ce que j'ai promis.
20. En tant que Quentin, je veux qu'une réponse envoyée qui règle un sujet devienne une proposition de tâche Terminé, afin que mon historique reste juste sans clôture automatique.
21. En tant que Quentin, je veux qu'un mail déjà traité ne produise jamais une seconde proposition, afin de ne pas valider deux fois la même chose.
22. En tant que Quentin, je veux voir le nombre de mails reçus depuis la dernière analyse par couloir, afin de mesurer ce qui m'attend.
23. En tant que Quentin, je veux pouvoir déplacer un mail d'un couloir à l'autre, afin de corriger Maximus quand il se trompe.

### Factures

24. En tant que Quentin, je veux que chaque facture reçue par mail soit reconnue, quel que soit l'expéditeur, afin de ne plus en oublier aucune.
25. En tant que Quentin, je veux une liste d'expéditeurs de factures amorcée sur les trois derniers mois et que je valide une fois, afin que la détection soit fiable dès le départ.
26. En tant que Quentin, je veux qu'un nouvel expéditeur de factures devienne une proposition d'ajout à la liste, afin que la liste grandisse sans que je la tienne à la main.
27. En tant que Quentin, je veux que les mails de facture sortent des couloirs, afin qu'ils n'encombrent pas mes actions.
28. En tant que Quentin, je veux une seule tâche ouverte « Factures à déposer », avec le nombre de factures et leurs liens, à faire dans la journée, afin de toutes les déposer d'un coup dans Pennylane.
29. En tant que Quentin, je veux que chaque nouvelle facture soit une proposition de mise à jour de cette tâche (compteur, lien, échéance au jour même), afin qu'aucune modification ne se fasse sans mon accord.
30. En tant que Quentin, je veux qu'une fois la tâche passée en Terminé, la facture suivante propose une nouvelle tâche, afin de ne jamais rouvrir une tâche close.

### Wispr et réunions

31. En tant que Quentin, je veux que chaque transcript Wispr soit analysé une seule fois, à la première analyse qui suit son arrivée, afin de ne pas payer deux fois le même travail.
32. En tant que Quentin, je veux une fiche par réunion, en Markdown, dans mon dossier de données, afin de retrouver ce qui s'est dit sans relire le transcript.
33. En tant que Quentin, je veux que la fiche ne retienne que mes actions, afin de rester concentré sur ce que j'ai à faire.
34. En tant que Quentin, je veux que chacune de mes actions devienne une proposition de tâche, liée au transcript d'origine, afin de ne plus recopier mes notes de réunion.
35. En tant que Quentin, je veux que les réunions sans transcript comptent quand même dans ma capacité, afin que ma journée soit juste.
36. En tant que Quentin, je veux que l'écran Soir me signale une fois une réunion de plus de 30 minutes avec des externes sans transcript, afin de penser à noter ses actions.
37. En tant que Quentin, je veux consulter la liste des fiches réunions, afin de retrouver une réunion passée.

### Propositions et validation

38. En tant que Quentin, je veux voir toutes les propositions en attente au même endroit, afin de les traiter en une fois.
39. En tant que Quentin, je veux approuver ou rejeter chaque proposition d'un clic, afin de garder la main sur tout ce qui s'écrit.
40. En tant que Quentin, je veux que chaque proposition de tâche arrive avec toutes ses propriétés pré-remplies (titre, impact, estimation, échéance, ferme, planifié le, source), afin de valider sans saisir.
41. En tant que Quentin, je veux que les propriétés devinées avec peu de certitude soient marquées, afin de savoir où regarder avant d'approuver.
42. En tant que Quentin, je veux pouvoir corriger une propriété dans la carte avant d'approuver, afin de ne pas devoir rouvrir Notion.
43. En tant que Quentin, je veux qu'une question ne me soit posée que pour une propriété obligatoire impossible à déduire, afin de ne pas répondre à un questionnaire à chaque tâche.
44. En tant que Quentin, je veux que l'estimation soit obligatoire et saisissable en raccourci (XS 1 h, S 2 h, M 4 h, L 7 h), afin que toute tâche puisse être planifiée.
45. En tant que Quentin, je veux que chaque tâche créée garde le lien vers son entrée d'origine (mail, transcript, conversation), afin de remonter au contexte en un clic.
46. En tant que Quentin, je veux qu'une proposition rejetée ne revienne pas à l'analyse suivante, afin de ne pas refuser deux fois la même chose.
47. En tant que Quentin, je veux qu'aucune tâche existante ne soit modifiée et qu'aucune tâche ne soit close sans mon approbation, afin que Notion reste fidèle à mes décisions.
48. En tant que Quentin, je veux valider en lot les propositions répétitives (récurrences, factures), afin de ne pas cliquer vingt fois chaque matin.
49. En tant que Quentin, je veux voir ce qui s'est passé après mon clic (écrit, en échec, avec la raison), afin de ne jamais croire qu'une tâche existe alors qu'elle n'a pas été créée.
50. En tant que Quentin, je veux pouvoir relancer une écriture en échec, afin de ne pas reprendre la proposition depuis le début.

### Planification du jour

51. En tant que Quentin, je veux que ma capacité du jour parte de mes horaires (lundi 9 h à 12 h et 13 h 30 à 17 h ; mardi à vendredi 9 h à 12 h 30 et 13 h 30 à 18 h) moins mes rendez-vous, afin que le plan tienne dans ma vraie journée.
52. En tant que Quentin, je veux que Maximus ne planifie que 70 % de mes heures libres, afin de garder de la marge pour l'imprévu.
53. En tant que Quentin, je veux une jauge de capacité du jour, afin de voir d'un coup d'œil si ma journée est tenable.
54. En tant que Quentin, je veux un Top 3 sans ex aequo, afin de savoir exactement par quoi commencer.
55. En tant que Quentin, je veux que l'urgence (échéance, ferme ou souple) et l'impact soient deux critères distincts, afin que tout ne soit plus « prioritaire ».
56. En tant que Quentin, je veux qu'une tâche sans échéance prenne la fin de sa plage comme échéance souple, afin qu'elle ne soit jamais repoussée indéfiniment.
57. En tant que Quentin, je veux voir la pression de chaque tâche longue (heures restantes sur heures libres avant la fin de plage), afin de savoir laquelle dérape.
58. En tant que Quentin, je veux qu'une tâche longue dont la pression dépasse 50 % entre dans le Top 3, afin de ne pas la découvrir trop tard.
59. En tant que Quentin, je veux que les reports soient visibles (combien de fois une tâche a glissé), afin de repérer ce que j'évite.
60. En tant que Quentin, je veux voir les décisions en attente et la charge de la semaine sur l'écran Matin, afin d'avoir tout mon matin sur un seul écran.
61. En tant que Quentin, je veux une citation du jour en post-it, afin de commencer la journée sur une note légère.
62. En tant que Quentin, je veux que la ligne de mes horaires de travail ne soit jamais affichée, afin de ne pas surcharger l'écran d'une information que je connais.

### Agenda

63. En tant que Quentin, je veux que Maximus me propose des créneaux de production dans mon agenda Outlook, afin que mon agenda reflète mon travail prévu.
64. En tant que Quentin, je veux que ces créneaux soient « disponible » par défaut et « occupé » si une échéance ferme est menacée ou si l'impact est fort, afin que mes collègues puissent quand même me réserver du temps.
65. En tant que Quentin, je veux qu'un créneau porte le titre de la tâche et aucune marque Maximus, afin que mes collègues ne distinguent pas un créneau posé par Maximus d'un créneau posé par moi.
66. En tant que Quentin, je veux que Maximus retrouve ses propres créneaux pour les déplacer ou les retirer, afin que l'agenda reste juste quand le plan change.
67. En tant que Quentin, je veux qu'un créneau que j'ai déplacé ou supprimé à la main ne soit jamais recréé sans proposition, afin que mes décisions dans Outlook soient respectées.

### Récurrences

68. En tant que Quentin, je veux une base Notion Récurrences (titre, fréquence, jour, charge, délai de préparation), afin de décrire une fois ce qui revient.
69. En tant que Quentin, je veux qu'une première liste de récurrences soit détectée dans Notion et Outlook et me soit proposée, afin de ne pas la saisir moi-même.
70. En tant que Quentin, je veux que chaque instance de récurrence soit une proposition validée en lot chaque matin, afin que la charge soit réservée à l'avance sans écriture sans clic.
71. En tant que Quentin, je veux consulter et gérer mes récurrences dans un écran dédié, afin de les ajuster sans ouvrir Notion.

### Semaine

72. En tant que Quentin, je veux un kanban avec une colonne À planifier puis une colonne par jour, chacune avec sa jauge de charge, afin de voir ma semaine d'un coup d'œil.
73. En tant que Quentin, je veux une alerte quand un jour est surchargé, afin de rééquilibrer avant qu'il soit trop tard.
74. En tant que Quentin, je veux un bouton « Planifier la semaine » qui produit un plan sous forme de propositions groupées par jour, afin de ne plus planifier à la main.
75. En tant que Quentin, je veux déplacer une carte d'un jour à l'autre avant de valider, afin d'ajuster le plan à ce que je sais et que Maximus ignore.
76. En tant que Quentin, je veux valider un jour entier, la semaine entière ou tâche par tâche, afin de choisir mon niveau de contrôle.
77. En tant que Quentin, je veux que le recalcul quotidien ne propose que les écarts au plan validé, afin de ne pas revalider toute la semaine chaque matin.

### Soir

78. En tant que Quentin, je veux lancer le débrief du soir moi-même quand je m'y mets, afin qu'il ne m'interrompe pas.
79. En tant que Quentin, je veux saisir le statut de chaque tâche du jour, afin que Notion reflète ce qui s'est vraiment passé.
80. En tant que Quentin, je veux saisir le temps réel passé sur chaque tâche, afin que les estimations futures soient calibrées.
81. En tant que Quentin, je veux mettre à jour les heures restantes de mes tâches longues, afin que leur pression soit juste demain.
82. En tant que Quentin, je veux noter mes ressentis de la journée, afin de garder un journal de travail.
83. En tant que Quentin, je veux un graphique estimé contre réel, afin de voir si je sous-estime systématiquement.
84. En tant que Quentin, je veux voir mes reports et les traces du jour dans le débrief, afin de faire le point sur ce que j'ai réellement fait.
85. En tant que Quentin, je veux que mes changements de statut et de temps réel soient des propositions que j'approuve, afin que la règle « aucune écriture sans clic » tienne aussi le soir.
86. En tant que Quentin, je veux que le journal du soir soit enregistré en Markdown dans mon dossier de données, afin de le relire plus tard.
87. En tant que Quentin, je veux qu'un débrief oublié me soit proposé le lendemain matin en version courte (statut et temps réel), que je peux passer, afin que mon Top 3 parte de données justes.

### Brouillons et style

88. En tant que Quentin, je veux qu'un mail du couloir Action puisse recevoir une proposition de réponse dans mon style, afin de répondre plus vite.
89. En tant que Quentin, je veux qu'après mon clic le brouillon soit créé dans Outlook, dans le bon fil, afin de l'envoyer moi-même depuis Outlook.
90. En tant que Quentin, je veux que Maximus n'envoie jamais de mail, afin qu'aucun message ne parte en mon nom sans que je l'aie envoyé.
91. En tant que Quentin, je veux un profil de style construit à partir de mes 200 derniers mails envoyés, dans un fichier lisible et corrigeable, afin de comprendre et d'ajuster ce que Maximus imite.
92. En tant que Quentin, je veux que l'écart entre un brouillon et le mail que j'ai réellement envoyé enrichisse le profil, afin que les brouillons s'améliorent avec mes corrections.

### Traçabilité

93. En tant que Quentin, je veux que chaque action réglée dans Notion, Outlook, OneDrive ou SharePoint devienne une trace datée, afin de retrouver ce qui a été fait.
94. En tant que Quentin, je veux consulter les traces par projet ou par interlocuteur, afin de répondre à « où en est-on avec ce client ? ».
95. En tant que Quentin, je veux que les traces OneDrive et SharePoint ne portent que le nom du fichier et sa date de modification, rattachés au projet par leur dossier, afin qu'aucun contenu ne soit lu et qu'aucune attribution fausse ne soit faite.
96. En tant que Quentin, je veux une liste d'exclusion dans les Réglages (par exemple les fichiers de mots de passe), afin que des fichiers sensibles n'apparaissent jamais.

### Chat

97. En tant que Quentin, je veux une bulle de chat en bas à droite de chaque écran, afin de demander quelque chose sans changer d'écran.
98. En tant que Quentin, je veux créer une tâche en langage naturel dans le chat, afin de capter une idée en une phrase.
99. En tant que Quentin, je veux que toute écriture demandée dans le chat apparaisse en carte de proposition avec Approuver et Rejeter, et qu'un « oui » tapé n'écrive rien, afin que le chat suive la même règle que le reste.
100. En tant que Quentin, je veux retrouver une action passée dans le chat (« quand ai-je relancé Dupont ? »), afin de ne plus fouiller trois outils.
101. En tant que Quentin, je veux un compte rendu par projet sur une période, construit à partir des traces, des fiches réunions et des tâches, affiché avec un bouton Copier et enregistré seulement si je le demande, afin de préparer un point client en une minute.
102. En tant que Quentin, je veux que le chat reprenne la conversation du jour et que les précédentes soient archivées, afin de garder le fil sans mélanger les journées.

### Réglages et données

103. En tant que Quentin, je veux que toutes les données de Maximus soient dans mon dossier `OneDrive - ONLYNNOV\maximus\`, privé, afin qu'elles soient sauvegardées sans être partagées.
104. En tant que Quentin, je veux qu'aucune donnée ne finisse dans le dépôt GitHub, afin qu'aucun mail ni transcript ne soit publié.
105. En tant que Quentin, je veux un écran Réglages pour la liste des expéditeurs de factures, les exclusions de traçabilité et le chemin du dossier de données, afin d'ajuster Maximus sans toucher au code.
106. En tant que Quentin, je veux une navigation par barre latérale (Matin, Soir, Semaine ; Réunions, Traçabilité, Récurrences ; état des sources ; Réglages), afin de passer d'un rituel à l'autre.

### Construction et migration

107. En tant que Quentin, je veux que tout changement du modèle Notion soit d'abord appliqué et testé sur une copie de Roadmap 2026.2, afin que l'équipe ne subisse aucune casse.
108. En tant que Quentin, je veux que la base partagée migre dès que les écritures sont validées sur la copie, avec les formules Heures, Semaine, Suivi du jour et la page de suivi de charge adaptées, afin de travailler pour de vrai sans priver l'équipe de la vue sur mes tâches.
109. En tant que Quentin, je veux utiliser l'analyse du matin dès qu'elle existe, même en lecture seule, afin de profiter de Maximus avant qu'il soit fini.

## Décisions d'implémentation

### Modules

- **Planificateur** (module pur, le cœur testé). Entrée : une photo du jour (tâches, événements, récurrences, heure exacte de Paris, horaires de travail, plan validé précédent). Sortie : un plan (capacité et heures libres, part planifiable à 70 %, créneaux proposés avec leur disponibilité, pression de chaque tâche longue, Top 3 ordonné sans ex aequo, jauges du jour et de la semaine, alertes de surcharge, écarts au plan validé). Aucun accès réseau, aucun appel à Claude, aucune horloge implicite : l'heure fait partie de l'entrée.
- **Adaptateur Claude**. Seul module qui lance `claude -p`, avec l'heure exacte et le fuseau Europe/Paris dans chaque appel. Il demande des sorties JSON conformes à des schémas fixés (mails classés, engagements, actions Wispr, factures détectées, brouillons, récurrences détectées, traces, réponses du chat) et rejette toute sortie non conforme. Les connecteurs claude.ai (Microsoft 365, Notion, Wispr Flow) sont utilisés à travers lui, en lecture pendant l'analyse.
- **Analyse**. Orchestration d'un lancement : lit les sources par l'adaptateur Claude et le dossier synchronisé, compare avec la mémoire de traitement, produit la photo du jour, appelle le planificateur, puis génère les propositions. Une source en échec est signalée et n'arrête pas les autres.
- **Propositions**. Un journal des propositions avec leur cycle de vie (en attente, approuvée, rejetée, écrite, en échec). Types : créer une tâche, mettre à jour une tâche, clore une tâche, poser un créneau, déplacer ou retirer un créneau, créer un brouillon, ajouter un expéditeur de factures, instance de récurrence. Chaque proposition garde son entrée d'origine. Une proposition rejetée est mémorisée pour ne pas revenir.
- **Écrivain**. Interface unique de toutes les écritures (Notion, agenda Outlook, brouillons Outlook). Il n'accepte qu'une proposition approuvée et refuse toute autre demande. Il n'existe aucune opération d'envoi de mail.
- **Mémoire**. Fichiers du dossier de données : mails traités, propositions rejetées, heure de la dernière analyse, registre des créneaux (identifiant d'événement Outlook relié à la tâche), traces, transcripts déjà analysés.
- **Serveur local**. Node.js v24, sert l'interface et une API locale : état du jour, lancer l'analyse (avec option de refaire le Top 3), liste des propositions, approuver, rejeter, corriger une proposition, valider un lot, débrief, semaine, réunions, traces, récurrences, réglages, chat.
- **Interface**. React, Tailwind, shadcn/ui, design system QDM, conforme à la maquette v2 et au code couleur de la décision 05. Une page brute de validation (sans charte) précède le tableau de bord et est remplacée par lui.
- **Lanceur**. Raccourci du bureau qui démarre le serveur et ouvre le navigateur sur Matin. Pas de tâche planifiée Windows.

### Données et schéma

- Notion Roadmap 2026.2 reste la source de vérité des tâches. Nouvelles propriétés : Planifié le (date ou plage), Échéance, Ferme (case), Impact (Faible, Moyen, Fort, remplace Priorité), Estimation (h, obligatoire), Temps réel (h), Source (URL). Nouvelle base Récurrences : titre, fréquence, jour, charge, délai de préparation.
- Dossier de données : `C:\Users\Quentin\OneDrive - ONLYNNOV\maximus\`, réglable. Contenu : `reunions/` (une fiche Markdown par réunion), `journal/` (un Markdown par soir), `chat/` (un fichier par jour), `memoire/` (JSON), `comptes-rendus/`, `profil-style.md`, `reglages.json`.
- OneDrive et SharePoint sont lus dans le dossier synchronisé (SharePoint sous `Share-ONLYNNOV - onlynnov`), en métadonnées seulement (nom, chemin, date de modification).

### Règles de planification encodées dans le planificateur

- Horaires : lundi 9 h à 12 h et 13 h 30 à 17 h ; mardi à vendredi 9 h à 12 h 30 et 13 h 30 à 18 h. Heures libres = horaires moins rendez-vous, calculées sur l'heure et pas seulement sur la date.
- Part planifiable : 70 % des heures libres.
- Échéance absente : la fin de la plage sert d'échéance souple.
- Pression = heures restantes / heures libres avant la fin de plage. Au-delà de 50 %, la tâche entre dans le Top 3.
- Jauges : neutre sous 50 %, ambre de 50 à 80 %, rouge au-delà ou en cas de retard.
- Créneau « occupé » si l'échéance ferme est menacée ou l'impact fort, sinon « disponible ».
- Top 3 : ordre total, départage déterministe.

### Interactions fixées

- Aucune écriture sans clic. Le chat produit des cartes de proposition ; le texte tapé n'écrit jamais.
- Validation en lot pour les récurrences et les factures.
- Factures : détection par contenu, renforcée par la liste d'expéditeurs ; une seule tâche groupée ouverte ; chaque facture est une proposition de mise à jour.
- Mails : premier lancement depuis le dernier jour ouvré à 8 h 30, puis reprise à l'heure exacte de l'analyse précédente ; tous les dossiers sauf les éléments supprimés.
- Relance en journée : nouveautés et écarts seulement, Top 3 inchangé sauf demande.

### Découpage en lots (ordre de `docs/methode.md`)

1. Étape 4 : copie Notion, nouveau modèle, base Récurrences.
2. Étape 5 : moteur du matin en lecture seule (planificateur, adaptateur Claude, analyse, mémoire), traçabilité et profil de style compris. Résultat consultable sans écriture.
3. Étape 6 : propositions, écrivain, page brute de validation, sur la copie Notion et l'agenda Outlook.
4. Étape 7 : migration de la base partagée.
5. Étape 8 : logo.
6. Étape 9 : tableau de bord complet et lanceur du bureau.
7. Étape 10 : chat.
8. Étape 11 : débrief du soir.
9. Étape 12 : semaine d'essai sur la base partagée.

Le détail en tickets vient de `/to-tickets`.

## Décisions de test

- Un bon test vérifie un comportement observable depuis l'extérieur du module (entrée, sortie, effets demandés à l'écrivain), jamais la manière dont le code y parvient. Un test ne doit pas casser lors d'une refactorisation qui garde le comportement.
- **Point de test 1 : le planificateur.** Testé en profondeur, cas par cas, avec des photos du jour écrites à la main : lundi contre mardi, rendez-vous qui chevauche la pause, rendez-vous déjà terminé à l'heure du lancement, journée pleine, tâche sans échéance, pression à 49 % et à 51 %, Top 3 avec des candidats à égalité, échéance ferme menacée, écarts au plan validé.
- **Point de test 2 : l'API du serveur local**, avec l'adaptateur Claude remplacé par un adaptateur simulé qui rejoue des sorties JSON enregistrées, et l'écrivain remplacé par un écrivain simulé qui enregistre les demandes. Cas couverts : circuit analyse, propositions, approbation, écriture ; aucune écriture sans approbation ; proposition rejetée qui ne revient pas ; mail déjà traité ignoré ; reprise à l'heure de la dernière analyse ; tâche groupée des factures (mise à jour, puis nouvelle tâche après Terminé) ; lot des récurrences ; registre des créneaux (créneau déplacé à la main non recréé) ; source en échec signalée sans bloquer l'analyse ; sortie Claude non conforme rejetée.
- Les tests ne touchent jamais Notion, Outlook ni Claude réels. Les données de test sont fictives et vivent dans le dépôt ; aucune donnée réelle n'y entre.
- Non testé automatiquement : le jugement de Claude (couloirs, engagements, actions Wispr, style des brouillons). Vérifié par Quentin sur de vrais matins, au temps 4 du cycle.
- Les écritures réelles sont vérifiées une fois à l'étape 6, sur la copie Notion et l'agenda de Quentin.
- Pas de tests unitaires des composants React : l'interface se vérifie en l'utilisant.
- Aucun test existant dans le dépôt : pas d'antériorité, les deux points de test sont à créer.

## Hors périmètre

- Tâches de Khadidiatou : ni tâches créées pour elle, ni suivi de sa charge, ni sa photo.
- Envoi de mails par Maximus.
- Lancement automatique (ouverture de session, tâche planifiée Windows) et notifications.
- Widget de bureau (envisagé pour une V2).
- Alertes marketing (SEO, AEO HubSpot, planning éditorial).
- Teams et fichiers locaux hors OneDrive.
- Lecture du contenu des fichiers OneDrive et SharePoint, et attribution d'auteur.
- Version mobile.
- Toute dépense : hébergement, API facturée, Vercel.

## Notes

- Inconnues à mesurer en construisant (décision 06) : quota d'usage Claude sur une matinée complète, latence du chat, écriture par les connecteurs en mode non interactif (`claude -p`). Si l'écriture en mode non interactif échoue, l'étape 6 bloque tout le reste : la traiter en premier dans le lot correspondant.
- Le premier test du 15 octobre a montré un événement terminé listé comme « prochain » : le filtrage sur l'heure est une exigence testée du planificateur.
- Le `.gitignore` exclut les noms du dossier de données ; vérifier avant chaque commit qui ajoute des fichiers.
