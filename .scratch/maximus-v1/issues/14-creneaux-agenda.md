# 14: Créneaux dans l'agenda

**Status:** ready-for-agent

**À construire :** Après approbation, Maximus pose, déplace ou retire des créneaux de production dans l'agenda Outlook de Quentin, sans aucune marque visible, et les retrouve grâce à un registre local.

**Bloqué par :** 12 (Premier tracé d'écriture : approuver crée la tâche), 04 (Pression, Top 3 et relance en journée)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Un créneau porte le titre de la tâche, sans catégorie ni mention Maximus
- [ ] « Disponible » par défaut, « occupé » si l'échéance ferme est menacée ou l'impact fort
- [ ] Le registre `memoire/` relie l'identifiant de l'événement Outlook à la tâche
- [ ] Un créneau déplacé ou supprimé à la main n'est jamais recréé ni remis en place sans nouvelle proposition
- [ ] Seul l'agenda de Quentin est touché
- [ ] Tests de l'API : pose, déplacement, créneau supprimé à la main
- [ ] Vérification réelle : un créneau posé, déplacé et retiré dans l'agenda de Quentin
