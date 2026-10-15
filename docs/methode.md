# Maximus : méthode de travail dans Claude Code

Reprise du document du 15 octobre 2026 (Quentin), source : <https://claude.ai/code/artifact/c9bc7b4e-2d4e-4e92-9c5a-25d3e107a60a>. Adaptée aux skills installés dans le dépôt : colonne « Skill à invoquer » dans les étapes, skill par temps du cycle, et section « Skills disponibles ».

## Principes

Une session Claude Code a une mémoire de travail limitée : plus elle se remplit, plus les réponses se dégradent. La règle qui en découle : ce qui doit durer vit dans les fichiers du dépôt, jamais seulement dans la conversation.

1. **Une session, une tâche.** Créer le dépôt, écrire la spécification, construire le moteur : trois sessions distinctes.
2. **Les fichiers sont la mémoire.** `CLAUDE.md` pour les règles permanentes, `docs/decisions` pour les choix tranchés, `docs/avancement.md` pour savoir où on en est. Une nouvelle session repart de ces fichiers, pas de tes souvenirs.
3. **Tu valides, Claude exécute.** Chaque changement important passe par un plan que tu lis avant qu'il touche au code.
4. **Petit et vérifiable.** Une étape terminée se teste et s'enregistre (commit) avant de passer à la suivante.

## Changer de session

Change de session dès qu'une tâche est terminée, ou dès que l'un de ces signaux apparaît :

- Claude oublie une règle donnée plus tôt, ou répète une erreur déjà corrigée.
- Les réponses deviennent vagues, plus longues, ou tournent en rond.
- Tu passes à un autre sujet (du moteur à l'interface, par exemple).
- L'indicateur de contexte dépasse environ la moitié.

Avant de fermer une session :

1. Demande : « Mets à jour docs/avancement.md avec ce qui est fait, ce qui reste et les points en suspens. »
2. Si une décision a été prise, fais-la ajouter dans `docs/decisions`.
3. Fais enregistrer le travail : « Fais un commit avec un message clair. »

Pour ouvrir la suivante, une seule phrase suffit : « Lis le CLAUDE.md et docs/avancement.md, puis dis-moi où on en est avant de faire quoi que ce soit. »

**Deux mémoires différentes.** Le skill `handoff` sert au passage d'une session à la suivante : il résume la conversation en cours pour la session d'après. `docs/avancement.md`, lui, garde l'état du projet dans la durée, d'une session à l'autre et d'une semaine à l'autre. **`handoff` n'est pas installé dans ce dépôt** : il enregistre son résumé dans le dossier temporaire de Windows, hors du projet. Le passage entre sessions se fait donc avec `docs/avancement.md` et la phrase d'ouverture ci-dessus.

Deux exceptions. Une session de grill se garde jusqu'au bout et se prolonge directement par `/to-spec` : sa valeur est justement le contexte accumulé. Et pour une conversation devenue longue sur une même tâche, `/compact` résume l'historique sans repartir de zéro.

## Le cycle de chaque tâche

Six temps, toujours dans cet ordre. Les sauter fait gagner dix minutes et en coûte deux heures. Le skill indiqué est celui à invoquer à ce moment-là.

| Temps | Ce qu'on fait | Skill à invoquer |
|---|---|---|
| 1. Cadrer | Une phrase d'objectif et le critère de fin : « Le moteur lit les mails des dernières 24 h et les classe en trois couloirs. Terminé quand je vois le classement de ce matin. » | `/grill-with-docs` quand le sujet est flou ou engage des décisions. Pour une tâche déjà claire, aucun skill : la phrase suffit. |
| 2. Planifier | Active le mode plan (Maj + Tab) : Claude propose sa démarche sans toucher au code. Lis, corrige, valide. | `/to-spec` pour écrire la spec, puis `/to-tickets` pour la découper en lots. `/prototype` si une question de logique ou d'écran doit être tranchée avant. |
| 3. Exécuter | Laisse faire, mais interromps (Échap) dès qu'il part dans une mauvaise direction : corriger tôt coûte moins cher. | `/implement` sur un ticket (il s'appuie sur `/tdd`). `/tdd` seul pour une petite fonction. `/diagnosing-bugs` dès qu'un bogue résiste. |
| 4. Vérifier toi-même | Lance, regarde le résultat réel. « Ça marche » dit par Claude n'est pas une preuve. | `/mattpocock-skills:code-review` pour la relecture du code (voir la note plus bas). La vérification du résultat réel reste la tienne : aucun skill ne la remplace. |
| 5. Enregistrer | Un commit par étape qui fonctionne. C'est ton point de retour si la suite casse. | Aucun skill adapté : commit demandé à Claude. `/implement` fait déjà son commit en fin de ticket. |
| 6. Documenter | `docs/avancement.md` à jour, décision ajoutée dans `docs/decisions` si besoin. | Aucun skill adapté pour `docs/avancement.md`. Pour une décision : format décrit dans `docs/agents/domain.md`. |
| Changer de session | Voir la section « Changer de session ». | Aucun skill installé (`handoff` écarté). `/retro` en fin d'étape ou après une session qui a mal tourné. |

Pour un grill, laisse le mode plan désactivé : il pousse Claude à produire un plan vite, alors qu'on veut qu'il continue à poser des questions.

## Les étapes du projet

Une session par ligne. Ne passe à la suivante que lorsque le critère de fin est atteint. L'étape en cours est notée dans `docs/avancement.md`.

| # | Session | Terminé quand | Skill à invoquer |
|---|---|---|---|
| 1 | Dépôt, CLAUDE.md, décisions | Fait. Relecture du CLAUDE.md et des décisions, règle typographique ajoutée | Aucun (fait) |
| 2 | Audit et installation des skills | Tu as lu le résumé de chaque skill et validé l'installation | Aucun skill adapté (fait) |
| 3 | Spécification avec `to-spec` | Une spec dans le dépôt, découpée en lots livrables, relue par toi | `/grill-with-docs`, puis `/to-spec`, puis `/to-tickets` |
| 4 | Copie Notion et nouveau modèle | La copie de Roadmap 2026.2 a les nouveaux champs et la base Récurrences, la base partagée est intacte | Aucun skill adapté : cycle normal avec le mode plan |
| 5 | Moteur du matin, en lecture seule | Une analyse réelle de ta matinée, propositions affichées, rien écrit nulle part | `/implement` (avec `/tdd`), `/prototype` si la logique de tri doit être testée avant |
| 6 | Écritures validées | Une tâche créée dans la copie Notion après ton clic, test écrit en mode automatique | `/implement` (avec `/tdd`), `/diagnosing-bugs` si l'écriture en mode automatique échoue |
| 7 | Logo | Un logo validé, décliné en icône pour la bulle et la barre latérale | Aucun skill installé dans le projet (voir la note sur `logo-design`) |
| 8 | Tableau de bord local | Les écrans Matin, Soir et Semaine fonctionnent avec tes vraies données | `/prototype` pour comparer des variantes d'écran, puis `/implement` |
| 9 | Chat | Créer une tâche et retrouver une action passée marchent depuis la bulle | `/implement` (avec `/tdd`) |
| 10 | Débrief du soir et tâche planifiée | Le rituel complet tourne seul à l'ouverture de session | `/implement` (avec `/tdd`) |
| 11 | Semaine d'essai | Cinq jours d'usage réel sur la copie, ajustements faits, puis migration de la base partagée | `/diagnosing-bugs` pour chaque anomalie, `/retro` en fin de semaine |

Aux étapes 5 à 10, la relecture du code se fait avec `/mattpocock-skills:code-review` avant le commit.

## Skills disponibles

### Installés dans le dépôt (`.claude/skills/`)

Copiés depuis mattpocock/skills, version 1.2.3 (commit `c55ee46`), audités le 15 octobre 2026. Aucun ne télécharge ni n'exécute de script distant, aucun n'envoie de données vers l'extérieur avec la configuration actuelle (suivi des issues en local).

| Commande | Rôle | À savoir |
|---|---|---|
| `/grill-with-docs` | Interrogatoire serré sur un plan, avec glossaire (`CONTEXT.md`) et décisions écrits au fil de l'eau | Appelle `grilling` et `domain-modeling`, fournis par le plugin mattpocock-skills |
| `/to-spec` | Transforme la conversation en spec, sans nouvelle question | Écrit dans `.scratch/<sujet>/spec.md` |
| `/to-tickets` | Découpe une spec en tickets livrables avec leurs dépendances | Écrit dans `.scratch/<sujet>/issues/` |
| `/prototype` | Code jetable pour trancher une question de logique ou d'écran | Le garde sur une branche à part, hors de `main` |
| `/implement` | Réalise un ticket ou une spec | Utilise `/tdd`, demande une relecture, fait un commit (sans pousser) |
| `/tdd` | Développement piloté par les tests, un test à la fois | Les points de test sont validés avec toi avant d'écrire |
| `/diagnosing-bugs` | Méthode pour les bogues tenaces : reproduire, hypothèses, correction, test | Peut lancer l'application en local et un navigateur sans fenêtre pour reproduire |
| `/retro` | Rétrospective : ce qui améliorerait les prochaines sessions | Lit les journaux de session de Claude Code sur ce poste, hors du dépôt (lecture seule) |
| `/setup-matt-pocock-skills` | Configure le suivi des issues et la documentation du domaine | Déjà fait. À relancer seulement pour changer de suivi : choisir GitHub ferait écrire sur GitHub |
| `/git-guardrails-claude-code` | Installe un garde-fou qui bloque les commandes git dangereuses | **Installé mais pas activé.** Bloquerait aussi `git push`. Son script a besoin de `jq`, absent du poste : sans lui, il ne bloquerait rien |

### Fournis par le plugin mattpocock-skills (installé pour ton compte, version 1.2.3)

| Commande | Pourquoi par le plugin |
|---|---|
| `/mattpocock-skills:code-review` | Pas copié dans le dépôt : Claude Code a déjà une commande intégrée `/code-review`, différente. Le même nom dans le dépôt créerait une confusion. Quand `/implement` demande « /code-review », utiliser celui-ci |

### Écartés

| Skill | Raison |
|---|---|
| `handoff` | Il enregistre son résumé dans le dossier temporaire de Windows, donc hors du projet |
| `logo-design` | Ses scripts écrivent des fichiers temporaires hors du projet et lancent Chrome en arrière-plan. Il reste installé pour ton compte depuis le 15 octobre |
| `qa` | N'existe plus dans mattpocock/skills : remplacé par `triage` et `to-tickets` |

## Sécurité et données

Maximus lit tes mails et peut écrire dans Notion et Outlook : les erreurs ont des conséquences réelles. Cinq règles.

1. **Tests sur la copie Notion uniquement**, jamais sur Roadmap 2026.2 tant que la semaine d'essai n'est pas terminée.
2. **Aucun envoi de mail pendant les tests.** Brouillons seulement. Un envoi réel n'arrive qu'en fin de projet, après ton clic.
3. **Aucune donnée dans GitHub.** Ni contenu de mail, ni transcript, ni fiche réunion : elles vont dans OneDrive. Fais vérifier le fichier `.gitignore` dès la première session de code.
4. **Aucun secret dans le code.** Pas de mot de passe ni de jeton écrit dans un fichier. Si Claude en propose un, refuse.
5. **Lis les demandes de permission.** Quand Claude Code demande l'autorisation d'exécuter une commande, lis-la avant d'accepter. N'autorise jamais tout d'office pour la session.

## À ne pas faire

- **Demander tout le projet d'un coup** (« construis Maximus ») : tu obtiendrais un code énorme, impossible à vérifier, qui semble marcher et casse au premier vrai matin.
- **Valider sans lire** : répondre « ok, ok, ok » aux plans, c'est laisser Claude décider à ta place.
- **Garder une session qui dérive** en espérant qu'elle se reprenne : ferme, mets à jour l'avancement, repars propre.
- **Corriger au même endroit trois fois de suite** : après deux échecs, arrête, décris le problème à neuf dans une nouvelle session.
- **Laisser une décision dans le chat** : si elle n'est pas écrite dans le dépôt, la prochaine session l'ignore.
- **Commencer par l'interface** : sans le moteur et de vraies données, tu peaufines des écrans qui ne montrent rien de vrai.
- **Changer de cap en cours de tâche** : une nouvelle idée se note dans `docs/avancement.md` et attend sa propre session.
- **Installer un skill ou un paquet non audité**, surtout pour un outil qui lit tes mails.

## Commandes utiles

| Commande | Usage |
|---|---|
| `/clear` | Vide la conversation et repart de zéro, dans le même projet |
| `/compact` | Résume l'historique pour libérer du contexte sans tout perdre |
| `/context` | Montre l'occupation de la mémoire de travail |
| `/resume` | Reprend une session précédente |
| `/mcp` | Liste les connecteurs actifs dans la session |
| `/permissions` | Montre et règle ce que Claude peut faire sans te demander |
| Maj + Tab | Bascule en mode plan, puis revient au mode normal |
| Échap | Interrompt Claude en cours de route |
| Échap deux fois | Revient à un message précédent pour reprendre autrement |

Les commandes évoluent avec les versions : `/help` donne la liste exacte de ta version.
