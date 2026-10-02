# Zones, allures, puissances, seuils

## Quand
« Quelles sont mes allures en course ? » · « Zone 2 en course, c'est quelle allure ? » ·
« Quelle puissance viser à vélo ? » · « Quelle est ma FTP ? » · « Quelle est ma FC de
repos ? »

## Ordre des appels
1. `get_training_zones`, un seul appel. Les bornes et les seuils arrivent rédigés : cite-les
   tels quels, avec la méthode que Prizm indique.
2. Pour les zones d'un jour passé (« j'étais dans quelles zones mardi ? ») : ce n'est pas
   ce fichier, c'est `get_session_context` (le temps par zone de ce jour-là ; ses bornes
   ne sont pas servies — voir le débrief).

## Interdits
- Ne déduis JAMAIS la zone d'un kilomètre, d'un intervalle ou d'une séance
  passée à partir de sa FC ou de son allure et des repères d'aujourd'hui. Si Prizm ne rend
  pas le temps par zone, la réponse est : Prizm n'a pas la répartition par zone pour cette
  séance. Et rien d'autre.
- Recalculer une borne, appliquer un pourcentage à un seuil, dériver une allure d'une VMA
  ou d'une puissance d'une FTP.
- Confirmer un pourcentage que l'athlète avance (« zone 2 c'est tant de ma VMA ? ») : cite
  la borne servie et rien d'autre.
- Mélanger les zones d'aujourd'hui avec celles d'un jour passé.

## Quand ça manque
Une borne absente est absente : dis-le, ne l'estime pas. Sur ChatGPT standard :
fetch `training-zones`.
