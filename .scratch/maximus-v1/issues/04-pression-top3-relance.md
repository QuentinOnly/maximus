# 04: Pression, Top 3 et relance en journée

**Status:** ready-for-agent

**À construire :** La page brute affiche la pression de chaque tâche longue, un Top 3 sans ex aequo et le nombre de reports de chaque tâche. Une relance dans la journée ne traite que les nouveautés et propose les écarts au plan, sans changer le Top 3 sauf demande explicite.

**Bloqué par :** 03 (Capacité et journée planifiée)

Spec : `.scratch/maximus-v1/spec.md`.

- [ ] Pression = heures restantes / heures libres avant la fin de plage ; une tâche au-delà de 50 % entre dans le Top 3
- [ ] Le Top 3 est un ordre total : deux candidats à égalité sont départagés de façon déterministe
- [ ] L'urgence (échéance ferme ou souple) et l'impact sont deux critères distincts du classement
- [ ] Les reports d'une tâche sont comptés et affichés
- [ ] Une relance garde le Top 3 du jour et liste les écarts (rendez-vous ajouté, capacité réduite)
- [ ] L'option « Refaire le Top 3 » recalcule le Top 3
- [ ] Tests du planificateur : pression à 49 % et à 51 %, égalités, échéance ferme menacée, écarts au plan
