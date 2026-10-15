# 05: Mails reçus en couloirs

**Status:** ready-for-agent

**À construire :** Chaque mail reçu depuis la dernière analyse est classé dans un couloir (Action, À surveiller, Écarté avec raison). Les mails du couloir Action deviennent des propositions de tâche complètes, affichées dans la page brute sans aucune écriture.

**Bloqué par :** 02 (Premier tracé : lancer l'analyse et voir l'agenda du jour)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Le premier lancement lit depuis le dernier jour ouvré à 8 h 30 ; les suivants reprennent à l'heure exacte de l'analyse précédente, quel que soit l'écart
- [ ] Tous les dossiers sont lus sauf le courrier indésirable et les éléments supprimés, qui ne sont jamais demandés aux sources
- [ ] Le statut lu ou non lu n'intervient pas
- [ ] Chaque mail écarté porte sa raison
- [ ] Un mail déjà traité ne produit jamais une seconde proposition (mémoire des mails traités)
- [ ] Une proposition de tâche porte toutes les propriétés pré-remplies, la source (lien vers le mail) et le marquage des propriétés incertaines
- [ ] Le contenu des mails est transmis comme donnée ; une consigne écrite dans un mail ne change rien au comportement
- [ ] Une sortie Claude non conforme au schéma est rejetée et signalée
- [ ] Tests de l'API : reprise à l'heure, mail déjà traité ignoré, sortie non conforme rejetée, courrier indésirable jamais demandé
- [ ] Vérification manuelle par Quentin sur un vrai matin, avec un mail de test contenant une consigne cachée
