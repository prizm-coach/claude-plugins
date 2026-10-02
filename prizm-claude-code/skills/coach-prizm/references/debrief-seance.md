# Débriefer une séance réalisée

## Quand
« Comment s'est passée ma sortie de mardi ? » · « Analyse ma séance d'hier » · « J'étais
dans quelles zones dimanche ? » · « Quelle était ma forme avant ma sortie de samedi ? »

## Ordre des appels
1. `get_session_context`. Il désigne la séance SOIT par son identifiant, SOIT par sa date
   locale ET son sport — jamais l'un sans l'autre. Si l'athlète a donné le jour et le
   sport, passe les deux. S'il n'a pas dit le sport (« ma séance d'hier »), appelle
   d'abord `list_recent_activities` et passe l'identifiant de la bonne sortie ; s'il y en
   a deux ce jour-là, demande laquelle. Si Prizm répond qu'il manque un fuseau horaire,
   demande-le à l'athlète et rappelle l'outil avec ; ne le devine pas.
   Il rend la séance, le temps passé dans chaque zone selon les repères qui faisaient foi
   ce jour-là, et l'état de forme qui la précédait. Les BORNES de ce jour-là (allures,
   puissances de chaque zone) ne sont pas servies : si l'athlète les demande, dis qu'elles
   ne sont pas disponibles pour ce jour-là, et ne les remplace pas par celles
   d'aujourd'hui. N'appelle ni `get_training_zones` ni `get_athlete_state` pour cela : ils
   décrivent aujourd'hui, et une séance passée ne se lit pas sur l'échelle d'aujourd'hui.
2. Si la réponse porte `candidates`, demande laquelle — n'en choisis aucune, même par
   l'heure si l'athlète n'a rien précisé.
3. Si elle porte une réserve (zones non fiables, charge partielle), dis-la avant tout
   commentaire.
4. `get_activity_details` pour l'exécution : splits, intervalles, décrochage.

## Interdits
- Ne déduis JAMAIS la zone d'un kilomètre, d'un intervalle ou d'une séance
  passée à partir de sa FC ou de son allure et des repères d'aujourd'hui. Si Prizm ne rend
  pas le temps par zone, la réponse est : Prizm n'a pas la répartition par zone pour cette
  séance. Et rien d'autre.
- Lire les zones d'aujourd'hui pour une séance passée.
- Republier une borne de zone : ce que Prizm rend ici, c'est du TEMPS par zone.
- Trancher entre deux candidates.
- Commenter une forme signalée non fiable sans le dire.

## Quand ça manque
Séance introuvable ce jour-là : dis-le. Ne rends pas la plus récente à la place.
Les bornes de ce jour-là ne sont servies sur aucune des deux surfaces : dis qu'elles ne
sont pas disponibles, et ne les remplace pas par celles d'aujourd'hui.
Sur ChatGPT standard : fetch `recent-activities` pour trouver la sortie, puis
fetch `activity-detail` (sans suffixe, la plus récente ; avec l'identifiant, celle-là).
Le contexte de séance n'a AUCUNE fiche sur cette surface : ni les bornes ni le temps par
zone de ce jour-là n'y sont atteignables, et le détail de sortie ne rend pas le temps par
zone. Dis-le, plutôt que de répondre à « j'étais dans quelles zones mardi ? » avec le
détail de la sortie.
