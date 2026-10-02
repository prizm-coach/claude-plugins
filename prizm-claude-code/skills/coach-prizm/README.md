# Coach Prizm — la compétence à installer sur Claude et sur ChatGPT

Ce dossier apprend à ton assistant à se comporter comme ton coach Prizm : quoi demander à
Prizm pour chaque question, citer tes repères tels quels sans jamais les recalculer, et te
relire avant d'enregistrer quoi que ce soit à ta place.

Exemple concret. Avant, « Quelle est ma fréquence cardiaque de repos ? » partait chercher
ta forme du jour et te répondait à côté. Maintenant la question va chercher tes repères
d'entraînement, là où cette valeur est vraiment rangée.

Avant d'installer : Prizm doit déjà être connecté à ton assistant, depuis l'Espace Prizm,
sur la carte de l'assistant concerné. La compétence ne remplace pas cette connexion, elle
s'en sert.

## Installer sur Claude

1. Ouvre `claude.ai`, puis **Personnaliser › Compétences**.
2. Clique sur **Ajouter**, puis **Importer une compétence**.
3. Choisis le fichier `coach-prizm.zip`.
4. Va dans l'onglet **Vos compétences** et vérifie que « Coach Prizm » y figure, activé.
5. Ouvre une nouvelle conversation et demande : « Comment est ma forme aujourd'hui ? »

Le chemin est le même sur ordinateur et sur téléphone.

## Installer sur ChatGPT

Constaté sur les offres Pro, Business, Enterprise et Edu au 6 septembre 2026. Si tu ne vois
pas l'onglet **Skills**, passe à la section suivante.

1. Ouvre `chatgpt.com`, puis **Plugins › onglet Skills**.
2. Clique sur **+**, puis **Téléverser à partir de votre ordinateur**.
3. Choisis le fichier `coach-prizm.zip`. ChatGPT l'analyse avant de l'activer.
4. Vérifie que « Coach Prizm » figure dans la liste.
5. Nouvelle conversation, et la même première question.

## Sur ChatGPT sans l'onglet Skills : passer par un Projet

1. Crée un **Projet** nommé « Coach Prizm ».
2. Dans les instructions du Projet, colle le contenu de `coach-prizm-instructions.md`,
   fourni à côté du zip.
3. Pose tes questions dans ce Projet.

Ce repli couvre la posture, les règles et l'aiguillage vers le bon geste. Les fiches
détaillées, elles, ne sont pas dans un Projet : les réponses seront un peu plus courtes.

## S'en servir

Dix phrases à essayer :

- « Comment est ma forme aujourd'hui ? »
- « Quelles sont mes allures en course ? »
- « C'est quoi ma prochaine séance ? »
- « Comment s'est passée ma séance d'hier ? »
- « Fais-moi le point sur ma semaine »
- « Aide-moi à préparer ma prochaine course »
- « Où j'en suis dans ma préparation ? »
- « Ce matin fatigue 6, moral 8 »
- « Ma séance d'hier, c'était dur, 8 sur 10 »
- « Qu'est-ce que tu sais faire ? »

Sur Claude, si la réponse ressemble à un tableau de chiffres ou ignore tes repères, écris
`/coach-prizm` en tête de ta question : le skill se charge à coup sûr.

Ce que tu dois voir : un avis de coach, une consigne pour la suite, et rien d'autre. Ni nom
de fonction, ni tableau de champs, ni valeur recalculée sous tes yeux. Avant d'enregistrer
la moindre chose — un ressenti, une note, un changement de plan — l'assistant te relit ce
qu'il s'apprête à faire et attend ton accord.

## Si Prizm semble ne plus répondre

- **Une capacité annoncée manque.** La liste mémorisée par ton assistant est périmée.
  Sur ChatGPT : **Plugins › Prizm › Actions du plugin › Gérer › Actualiser**. Sur Claude :
  reconnecte Prizm depuis **Réglages › Connecteurs**. Puis ouvre une nouvelle conversation.
- **Des refus en série juste après une mise à jour de Prizm.** Ouvre une nouvelle
  conversation : l'ancienne garde en tête l'état précédent.
- **Tout est refusé, partout.** Ton accès a expiré. Retourne dans l'Espace Prizm pour le
  renouveler.

Un guide illustré, pas à pas, est en préparation dans l'Espace de `assistant.prizm-coach.com`.
