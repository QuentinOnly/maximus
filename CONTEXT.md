# Maximus

Agent de planification personnel de Quentin : il transforme ce qui arrive (mails, réunions, demandes) en tâches et planifie les journées selon la capacité réelle.

## Ce que l'agent prépare

**Proposition** :
Ce que Maximus prépare et qui n'agit nulle part tant que Quentin ne l'a pas approuvé : une tâche à créer, une mise à jour, une clôture, un créneau, un brouillon.
_Éviter_ : suggestion, décision en attente (libellé d'écran seulement), tâche à créer

**Tâche** :
Une page de la base Notion Roadmap 2026.2 (ou de sa copie de test). N'existe qu'une fois une proposition approuvée.
_Éviter_ : action, to-do, item

**Entrée** :
Tout ce qui peut faire naître une proposition : mail reçu, engagement dans un mail envoyé, action tirée d'un transcript Wispr, demande dans le chat.
_Éviter_ : source (réservé au lien d'origine d'une tâche), input

## Planification

**Urgence** :
Ce que dicte l'échéance d'une tâche, ferme (imposée par un tiers ou un événement) ou souple.
_Éviter_ : priorité

**Impact** :
L'importance d'une tâche : Faible, Moyen ou Fort. Remplace l'ancienne propriété Priorité.
_Éviter_ : priorité, importance (dans les données)

**Capacité** :
Les heures de travail d'un jour donné, horaires fixes moins les rendez-vous. Maximus planifie à 70 % des heures libres.
_Éviter_ : disponibilité

**Plage** :
La période sur laquelle une tâche longue est planifiée (propriété Planifié le, en plage de dates). Sa fin sert d'échéance souple sans échéance renseignée.

**Pression** :
Pour une tâche longue, heures restantes divisées par heures libres avant la fin de sa plage. Au-delà de 50 %, la tâche entre dans le Top 3.
_Éviter_ : charge (réservé à la charge d'une journée ou d'une semaine)

**Top 3** :
Les trois tâches du jour, classées sans ex aequo.

**Créneau** :
Un événement de l'agenda Outlook de Quentin réservé à une tâche, posé par Maximus après validation et indiscernable d'un créneau posé à la main.
_Éviter_ : bloc, slot

**Trace** :
Le constat daté d'une action faite dans Notion, Outlook, OneDrive ou SharePoint, rattaché à un projet ou un interlocuteur.
_Éviter_ : log, historique (réservé à l'historique du chat)

## Mails

**Facture à déposer** :
Une facture reçue par mail automatique d'un outil, que Quentin doit télécharger et importer dans Pennylane. Toutes alimentent une seule tâche groupée.

**Couloir** :
Le classement d'un mail reçu : Action, À surveiller, ou Écarté (toujours avec une raison).
_Éviter_ : catégorie, dossier, label
