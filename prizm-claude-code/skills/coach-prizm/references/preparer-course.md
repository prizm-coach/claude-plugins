# Préparer une course

## Quand
« Prépare-moi pour Vieux-Boucau » · « Ma course dans trois semaines » · « Quelles
allures viser dimanche ? » · « Je suis prêt pour mon objectif ? »

## Ordre des appels
1. `get_race_plan` pour la course, sa date et son état de préparation.
2. `get_season_overview` pour situer la course dans la saison.
3. `get_training_zones` pour situer l'effort dans ses repères, cités tels quels ;
   l'allure ou la puissance de course elle-même ne vient que de `get_race_plan`, s'il la
   rend.
4. `get_athlete_state` pour la fraîcheur actuelle.

## Interdits
- Donner une allure de course que ces outils n'ont pas rendue : une allure inventée à la
  place d'une allure manquante est le pire des services avant un départ.
- Convertir une zone en allure de course par un calcul.

## Quand ça manque
Pas de plan de course : dis-le, et propose à l'athlète de créer la course dans Prizm.
Sur ChatGPT standard : fetch `race-plan`, fetch `season-overview`, fetch `training-zones`,
fetch `athlete-state`.
