# Check-in du matin

## Quand
« Voici comment je me sens ce matin » · « J'ai dormi six heures, jambes lourdes, moral
bon » · « Fatigue 6, moral 8 » · « Check-in ».

## Ordre des appels
1. Deux notes sur 10 sont requises et c'est l'athlète qui les donne : fatigue
   (10 veut dire frais, 1 épuisé) et humeur (10 veut dire excellente). S'il n'a donné
   que des mots (« jambes lourdes, moral bon »), demande-lui ces deux notes en rappelant
   le sens de l'échelle ; ne traduis jamais ses mots en chiffres à sa place. Courbatures,
   motivation, sommeil en heures et ressenti libre seulement s'il les a donnés, tels
   qu'il les a donnés.
2. Relis-lui les valeurs avec le sens de l'échelle
   (« fatigue 6 sur 10, 10 veut dire frais ») et attends son oui. Tu n'appelles l'outil
   qu'APRÈS son oui, jamais avant, même si tu penses qu'un enregistrement existe déjà ;
   le refus du serveur n'est pas ta relecture.
3. `submit_morning_checkin`. Si Prizm refuse parce qu'un check-in existe déjà aujourd'hui,
   il rend un jeton (`confirmation_token`) : demande à l'athlète s'il veut vraiment
   remplacer ses réponses du matin, puis rappelle l'outil avec le jeton — jamais d'office.
4. Pour la forme du jour et la consigne de séance, `get_athlete_state` : elles se lisent,
   elles ne se déduisent pas du check-in.

## Interdits
- Enregistrer sans relecture.
- Inventer ou déduire une valeur : « j'ai mal dormi » sans chiffre → demande la note,
  n'invente ni le sommeil ni la fatigue ; « jambes lourdes » n'est pas un 4.
- Déduire une fraîcheur ou une consigne du check-in lui-même.

## Quand ça manque
Sur ChatGPT standard, aucune écriture n'est possible : dis-le et renvoie vers
l'application Prizm ou vers Claude.
