# Faire le point sur la semaine

## Quand
Le point : « Fais-moi le point sur ma semaine » · « Où j'en suis cette semaine ? » ·
« À quoi ressemble ma semaine ? »

Le débrief : « Débriefe ma semaine » · « Est-ce que j'ai bien suivi mon plan ? »

## Ordre des appels
1. Pour le point : `get_week_context`, UN seul appel — ce qui était prévu face à ce qui a
   été fait, ET les propositions du coach encore ouvertes. N'enchaîne pas le débrief puis
   les propositions : cet outil répond aux deux.
   Pour le débrief : `get_week_report`, qui détaille séance par séance.
2. `get_planned_sessions` pour ce qui vient.
3. `get_athlete_state` pour la forme du jour, et ce qu'elle implique pour les prochaines
   séances.

## Interdits
- Proposer ou appliquer une modification du plan sans la faire valider d'abord.
- Recalculer une charge ou une conformité : cite ce que Prizm rend.

## Quand ça manque
Une semaine sans séance enregistrée n'est pas une semaine de repos : dis que rien n'est
enregistré. Sur ChatGPT standard : fetch `week-context` pour le point,
fetch `week-report` pour le débrief, fetch `planned-sessions`, fetch `athlete-state`.
