# Copie Notion et correspondances de l'ancien modèle

15 octobre 2026, ticket 01 (étape 4). Précise la décision 03 pour la copie de test, et sert de base à la migration de la base partagée (ticket 16).

- **Copie de test** : page « Roadmap 2026.2 [TEST Maximus] », duplication complète de Roadmap 2026.2 (Projets, Tâches, vues, page de suivi de charge), rangée dans les pages privées de Quentin. Les tâches de Khadidiatou y sont gardées pour que formules et vues restent testables ; Maximus ne lit que les tâches de Quentin. Les identifiants sont dans `reglages.json` du dossier de données, jamais dans le dépôt.
- **Échéance actuelle renommée en Planifié le.** Dans les faits, l'ancienne Échéance (souvent une plage) dit quand la tâche est travaillée. Le renommage garde les valeurs et les formules qui s'appuient dessus. Une nouvelle Échéance, vide, porte désormais la date limite réelle.
- **Correspondance Priorité vers Impact, 1 pour 1** : Faible devient Faible, Moyenne devient Moyen, Forte devient Fort. Une tâche sans Priorité reste sans Impact ; Maximus le proposera.
- **Estimation (h) tirée de Charge** pour les tâches existantes : XS 1 h, S 2 h, M 4 h, L 7 h. Sans Charge, l'estimation reste vide.
- **Priorité et Charge gardées dans la copie** jusqu'à la migration, où leur sort sera tranché (vues et formules qui en dépendent).
- **Récurrences** : Titre, Fréquence (Quotidienne, Hebdomadaire, Mensuelle, Trimestrielle, Annuelle), Jour (texte libre), Charge (h), Délai de préparation (j). Créée vide dans la copie.
- **Limite constatée** : sans l'offre Notion Business, le connecteur refuse les requêtes SQL qui croisent plusieurs bases et plafonne les requêtes SQL sur une base. Le moteur interroge donc une base à la fois et ménage ces requêtes (à mesurer à l'étape 5).
- **Non lu** : le code des formules Heures, Semaine, Suivi du jour, Lundi et Avancement n'est pas lisible par le connecteur. Leur adaptation (ticket 16) passe par l'interface Notion.
