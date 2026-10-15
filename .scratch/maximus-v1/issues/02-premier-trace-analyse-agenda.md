# 02: Premier tracé : lancer l'analyse et voir l'agenda du jour

**Status:** ready-for-agent

**À construire :** Quentin ouvre une page locale brute, clique sur « Lancer l'analyse » et voit ses rendez-vous du jour, filtrés sur l'heure exacte de Paris. Ce ticket pose le serveur local, l'adaptateur Claude avec sa liste blanche d'outils de lecture (décision 10), le dossier de données et l'état des sources. Étape 5.

**Bloqué par :** Aucun (peut démarrer tout de suite)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Le serveur local Node.js v24 sert une page brute (sans charte) avec l'heure de la dernière analyse et un bouton « Lancer l'analyse »
- [ ] L'analyse appelle `claude -p` en transmettant l'heure exacte et le fuseau Europe/Paris
- [ ] L'appel d'analyse ne reçoit que des outils de lecture nommés un par un ; un test de l'adaptateur vérifie la liste transmise
- [ ] Un rendez-vous déjà terminé à l'heure du lancement n'apparaît pas comme à venir
- [ ] L'heure de la dernière analyse est enregistrée dans le dossier de données `OneDrive - ONLYNNOV\maximus\` (chemin réglable)
- [ ] Une source en échec est signalée sur la page sans bloquer l'affichage des autres
- [ ] Test de l'API locale avec un adaptateur Claude simulé : lancer l'analyse renvoie les rendez-vous enregistrés
- [ ] La durée et la consommation d'un lancement réel sont notées dans `docs/avancement.md` (inconnues de la décision 06)
- [ ] Le `.gitignore` couvre tout fichier de données créé
