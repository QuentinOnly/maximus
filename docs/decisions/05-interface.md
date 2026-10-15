# Interface

La maquette v2 est validée : trois écrans (Matin, Soir, Semaine) sur le canvas [Maximus](https://claude.ai/artifact/2MP2ZsaUTHsoQ8YRaWCX5z), au design system QDM.

| Élément | Décision |
|---|---|
| Charte | Design system QDM : fond papier, Geist, bleu réservé aux actions et au point animé des titres, trois points en signature, boutons en pilule |
| Navigation | Barre latérale anthracite, zone sombre unique de la page. Rituels (Matin, Soir, Semaine), Mémoire (Réunions, Traçabilité, Récurrences), état des sources, Réglages |
| Matin | Jauge de capacité, charge de la semaine, décisions en attente, mails depuis hier. Top 3, journée, citation du jour en post-it, questions, pression des tâches longues |
| Soir | Statut par tâche, graphique estimé contre réel, ressentis, reports, traces du jour |
| Semaine | Kanban : À planifier puis une colonne par jour avec sa jauge de charge, alertes de surcharge |
| Horaires | La ligne des horaires de travail n'est jamais affichée |
| Chat | Bulle en bas à droite, panneau façon Claude. Crée des tâches en langage naturel, retrouve des actions passées, produit des comptes rendus par projet. Conversation du jour conservée, les précédentes archivées |
| Avatars | Photo ronde de Quentin sur ses tâches, celle de Khadidiatou sur les siennes. Source prévue : les profils des personnes assignées dans Notion |
| Vocabulaire | Titres factuels, aucune formule de type IA |
| Écrans | Grand écran en principal, lisible sur le portable 15 pouces. Pas de mobile |
| Logo | À créer avec le skill logo-design-skill. « M » provisoire en attendant |

## Code couleur des statuts

Validé (écran Statuts du canvas) :

| Famille | État | Affichage |
|---|---|---|
| Avancement | À planifier | Icône cercle pointillé, contour gris |
| Avancement | Planifié | Icône cercle vide, gris clair `#f1efe9` |
| Avancement | En cours | Icône demi-cercle, encre `#16150f` |
| Avancement | En attente | Icône pause, gris moyen `#e6e3db` |
| Avancement | Terminé | Icône coche, vert `#067647` sur `#ecfdf3` |
| Délai | Dans les temps | Aucun marquage |
| Délai | À risque | Pastille triangle, ambre `#93370d` sur `#fffaeb` |
| Délai | En retard | Pastille point d'exclamation, rouge `#b42318` sur `#fef3f2` |

L'avancement est toujours affiché en icône, le délai seulement en cas de problème. Jauges de pression et de charge : neutre sous 50 %, ambre de 50 à 80 %, rouge au-delà ou en cas de retard. Chaque couleur est doublée d'une icône et d'un libellé. Pas de bleu pour les statuts : il reste réservé à ce qui est cliquable.

Réunions, Traçabilité, Récurrences et Réglages ne sont pas maquettés : ils reprendront les mêmes composants dans le code.
