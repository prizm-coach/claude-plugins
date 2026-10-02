# Aiguillage — ce que l'athlète dit, ce que Prizm sait faire

Fichier GÉNÉRÉ depuis le catalogue Prizm (`scripts/build_coach_prizm_skill.py --ecrire`).
Ne le modifie pas à la main : la CI le compare au catalogue réel.

Lecture : cherche la phrase la plus proche de ce que dit l'athlète, appelle ce qui est
indiqué en « catalogue complet » ; sur ChatGPT standard, demande la fiche indiquée.
Un outil marqué AJOUTER UNE INFORMATION ou PROPOSER UN CHANGEMENT se relit avant d'agir.

En « catalogue complet », chaque outil est suivi entre parenthèses de son libellé :
le nom sous lequel l'interface le range dans son sélecteur d'outils, et donc sous
lequel tu le trouveras à l'écran. Ce libellé ne se demande jamais comme une fiche —
une fiche est toujours écrite sur la ligne « ChatGPT standard », et nulle part ailleurs.

## Poser une question sur ton entraînement

### Ma forme du jour — DISPONIBLE — CONSULTER
L'athlète dit : « Comment est ma forme aujourd'hui ? » · « Est-ce que je suis frais ? » · « J'ai récupéré de dimanche ? » · « Je peux enchaîner une séance dure aujourd'hui ? » · « Ouvre mon bilan matinal. »
Catalogue complet : get_athlete_state (`Forme du jour`), render_readiness (`Bilan matinal visuel`)
ChatGPT standard : fetch `athlete-state`.
À retenir : Prizm répond, rien ne change dans le plan.

### Mon sommeil et ma récupération passés — DISPONIBLE — CONSULTER
L'athlète dit : « Comment dormais-je en juin ? » · « Montre ma récupération de la semaine dernière. » · « Pourquoi mon sommeil était irrégulier cette semaine ? »
Catalogue complet : get_recovery_sleep_history (`Historique de recuperation et sommeil`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm répond, rien ne change dans le plan.

### Mes repères d'entraînement — DISPONIBLE — CONSULTER
L'athlète dit : « Quelles sont mes allures en course ? » · « Quelle allure tenir pour un effort soutenu ? » · « Quelle puissance viser à vélo ? » · « Quelle est ma puissance de référence à vélo ? » · « Quelle est ma FC de repos ? »
Catalogue complet : get_training_zones (`Zones et seuils`)
ChatGPT standard : fetch `training-zones`.
À retenir : Prizm répond, rien ne change dans le plan.

### Mon plan à venir — DISPONIBLE — CONSULTER
L'athlète dit : « C'est quoi ma prochaine séance ? » · « Que dit mon plan demain ? » · « À quoi ressemble ma semaine ? » · « Combien de temps dure ma sortie longue ? »
Catalogue complet : get_planned_sessions (`Séances à venir`), get_planned_session_sheet (`Fiche détaillée d'une séance`), render_weekly_plan (`Plan hebdomadaire visuel`), render_weekly_plan_v2 (`Plan hebdomadaire interactif`)
ChatGPT standard : fetch `planned-sessions` · fetch `planned-session-sheet.v1`.
À retenir : Prizm répond, rien ne change dans le plan.

### Ce qui a changé dans mon plan — DISPONIBLE — CONSULTER
L'athlète dit : « Qu'est-ce qui a changé dans mon plan ? » · « Ma régénération a fait quoi exactement ? » · « Quelles séances ont bougé cette semaine ? » · « J'ai perdu une séance, laquelle ? »
Catalogue complet : summarize_plan_change (`Ce qui a changé dans le plan`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm répond, rien ne change dans le plan.

### Où j'en suis, cette semaine et dans ma préparation — DISPONIBLE — CONSULTER
L'athlète dit : « Fais-moi le point sur ma semaine. » · « Où j'en suis dans ma préparation ? » · « Il me reste combien de temps avant mon objectif ? »
Catalogue complet : get_week_context (`Contexte de ma semaine`), get_season_context (`Contexte de ma saison`)
ChatGPT standard : fetch `week-context` · fetch `season-context`.
À retenir : Prizm répond, rien ne change dans le plan.

### Mon bilan de semaine et mes sorties — DISPONIBLE — CONSULTER
L'athlète dit : « Débriefe ma semaine. » · « Est-ce que j'ai bien suivi mon plan ? » · « Montre-moi mes dernières sorties. » · « Est-ce que j'ai décroché sur la fin dimanche ? » · « Analyse ma sortie d'hier. »
Catalogue complet : get_week_report (`Débrief de la semaine`), render_week_comparison (`Réalisé vs planifié de la semaine`), list_recent_activities (`Dernières sorties`), get_activity_details (`Analyse d'une sortie`), get_activity_laps (`Tours et longueurs d'une sortie`), get_activity_segments (`Structure réalisée d'une sortie`), get_session_context (`Lire le contexte d'une séance`)
ChatGPT standard : fetch `week-report` · fetch `recent-activities` · fetch `activity-detail`.
À retenir : Prizm répond, rien ne change dans le plan.

### Relier une séance prévue à ce qui a été réalisé — DISPONIBLE — CONSULTER
L'athlète dit : « Compare cette sortie à la séance qui était prévue. » · « Quels blocs ai-je réellement exécutés ? » · « Les observations de cette séance sont-elles assez fiables ? »
Catalogue complet : get_session_performance_feedback (`Retour de séance complet`), get_comparison_details (`Comparaison détaillée prévu-réalisé`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm répond, rien ne change dans le plan.

### Ma saison et mon évolution — DISPONIBLE — CONSULTER
L'athlète dit : « Combien de semaines avant mon objectif ? » · « Est-ce que mon entraînement progresse comme prévu ? »
Catalogue complet : get_season_overview (`Ma saison`)
ChatGPT standard : fetch `season-overview`.
À retenir : Prizm répond, rien ne change dans le plan.

### Mes courses et ma préparation — DISPONIBLE — CONSULTER
L'athlète dit : « C'est quand ma prochaine course ? » · « Est-ce que je suis prêt pour le marathon ? » · « Comment je gère mon effort le jour J ? »
Catalogue complet : get_race_plan (`Mes courses`)
ChatGPT standard : fetch `race-plan`.
À retenir : Prizm répond, rien ne change dans le plan.

### Mon niveau, mes records et mes progrès — DISPONIBLE — CONSULTER
L'athlète dit : « Est-ce que je progresse ? » · « Quels sont mes records récents ? » · « Quel est mon point fort en vélo ? »
Catalogue complet : get_performance_report (`Rapport de performance`), render_training_progress (`Progression d'entraînement visuelle`)
ChatGPT standard : fetch `performance-report`.
À retenir : Prizm répond, rien ne change dans le plan.

### Ce que le coach me propose — DISPONIBLE — CONSULTER
L'athlète dit : « Le coach me propose quoi ? » · « Est-ce que je dois adapter ma semaine ? » · « Qu'est-ce qui attend ma décision ? » · « Compare mon plan à la proposition avant que je choisisse. »
Catalogue complet : get_active_proposals (`Propositions du coach`), render_proposal_comparison (`Comparaison d’une proposition du coach`)
ChatGPT standard : fetch `active-proposals`.
À retenir : Prizm répond, rien ne change dans le plan.

### Comprendre et suivre une décision — DISPONIBLE — CONSULTER
L'athlète dit : « Pourquoi cette adaptation a-t-elle été proposée ? » · « Cette décision a-t-elle vraiment été exécutée ? » · « Quelles règles et alternatives ont conduit à cette décision ? »
Catalogue complet : explain_decision (`Expliquer une décision`), get_execution_status (`Suivre l'exécution d'une décision`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm répond, rien ne change dans le plan.

### Savoir ce que je peux demander — DISPONIBLE — CONSULTER
L'athlète dit : « Qu'est-ce que tu sais faire ? » · « Sur quoi je peux te poser des questions ? » · « Qu'est-ce que tu ne sais pas encore faire ? »
Catalogue complet : get_prizm_capabilities (`Ce que Prizm sait faire`)
ChatGPT standard : fetch `guide:capacites`.
À retenir : Prizm répond, rien ne change dans le plan.

### Situer ma durabilité à vélo — DISPONIBLE — CONSULTER
L'athlète dit : « Où en est ma durabilité à vélo par rapport à mon objectif ? » · « Ma mesure de durabilité est-elle encore fraîche ? » · « Pourquoi mon écart de durabilité est-il inconnu ? »
Catalogue complet : get_bike_durability_gap (`Écart de durabilité à vélo`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm répond, rien ne change dans le plan.

### Retrouver la bonne information — DISPONIBLE — CONSULTER
L'athlète dit : « Qu'est-ce que tu sais de mon entraînement ? » · « Retrouve ma forme du jour. » · « Explique-moi ma forme du jour en détail. »
Catalogue complet : search (« Recherche dans mes données »), fetch (« Lecture d'une fiche »)
ChatGPT standard : ce sont les deux outils de cette surface, appelle-les directement.
À retenir : Prizm répond, rien ne change dans le plan.

### Vérifier que tout fonctionne — DISPONIBLE — CONSULTER
L'athlète dit : « Est-ce que Prizm peut répondre ? » · « Est-ce que tout fonctionne entre ma plateforme LLM et Prizm ? »
Catalogue complet : ping (`État de la passerelle`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm répond, rien ne change dans le plan.

### Ce qui m'attend — DISPONIBLE — CONSULTER
L'athlète dit : « Qu'est-ce qui m'attend ? » · « J'ai des choses à traiter ? » · « Montre-moi tout ce qui est en attente. »
Catalogue complet : list_pending_items (`Ce qui attend l'athlète`), render_pending_items (`Ce qui attend l'athlète (carte)`), get_plan_confirmations (`Lire les plans à confirmer`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm répond, rien ne change dans le plan.

### Voir le cycle en préparation — DISPONIBLE — CONSULTER
L'athlète dit : « Montre-moi le cycle qui vient d'être préparé. » · « Qu'est-ce qu'il y a dans mon nouveau cycle ? » · « Il ressemble à quoi, ce brouillon ? » · « Relance le moteur sur mon plan. »
Catalogue complet : get_cycle_draft (`Voir le cycle en préparation`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm répond, rien ne change dans le plan.

## Dire ce que ta montre ne mesure pas, et essayer une idée

### Dire comment je vais — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « J'ai dormi sept heures, jambes lourdes, motivation moyenne. » · « Ma séance d'hier était plus dure que prévu. » · « Note que je me sens fatigué depuis trois jours. »
Catalogue complet : submit_morning_checkin (`Enregistrer le check-in du matin`), log_session_feedback (`Noter le ressenti d'une séance`), add_activity_logbook_note (`Ajouter une note de carnet`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Tester une idée sans rien changer — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Qu'est-ce que ça donnerait si je m'entraînais plus dur cet hiver ? » · « Où j'en serais dans six semaines à ce rythme ? » · « Montre-moi le résultat quand il est prêt. »
Catalogue complet : simulate_training_load (`Simuler une charge d'entraînement`), get_job_status (`Suivi d'un travail en cours`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Trouver une course et la situer avant de l'inscrire — DISPONIBLE — CONSULTER
L'athlète dit : « Trouve-moi le marathon de Paris. » · « Quels triathlons il y a en Espagne au printemps ? » · « Est-ce que ce trail doit devenir un objectif de saison ? » · « Je fais cette course pour le plaisir, ça change quoi ? »
Catalogue complet : search_races (`Chercher une course`), classify_objective (`Classer un objectif ou un challenge`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm répond, rien ne change dans le plan.

### Donner mon avis sur Prizm — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Dis à l'équipe que mes nouvelles sorties n'arrivent pas. » · « J'aimerais voir le résumé de ma semaine dès l'écran d'accueil. » · « Signale que le débrief de ma sortie longue ne s'affiche pas. »
Catalogue complet : send_prizm_feedback (`Envoyer un retour à Prizm`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Mes séances mises de côté — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Garde cette séance, je veux la refaire. » · « Quelles séances j'ai mises de côté ? » · « Refais-moi ma séance de seuil habituelle. »
Catalogue complet : list_session_templates (`Mes séances mises de côté`), save_session_template (`Mettre une séance de côté`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Mon profil alimentaire — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Je passe végétarien. » · « Ajoute les fruits à coque à mes allergies. » · « Je n'ai plus le temps de cuisiner le soir. »
Catalogue complet : set_nutrition_preferences (`Régler les préférences alimentaires`), set_food_allergies (`Mettre à jour les allergies alimentaires`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Mon matériel — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Quels vélos j'ai enregistrés ? » · « Range mon ancienne paire de chaussures, je ne cours plus avec. » · « Corrige la marque de mon vélo de route. »
Catalogue complet : list_equipment (`Voir mon matériel`), update_equipment (`Mettre à jour un matériel`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Déclarer une séance faite sans montre — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « J'ai couru une heure ce matin, ma montre était déchargée. » · « Ajoute ma séance de natation d'hier. » · « J'ai fait du home-trainer sans capteur, note-le. »
Catalogue complet : log_manual_activity (`Déclarer une séance faite sans montre`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Mes courses préparées — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « J'ai une course le 20 septembre, prépare-la. » · « Le départ est finalement à 8h, pas 9h. » · « Quelles courses j'ai en préparation ? »
Catalogue complet : list_race_events (`Voir mes courses préparées`), create_race_event (`Enregistrer une course à préparer`), update_race_event (`Modifier une course préparée`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Mes séances regroupées — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Les totaux de mon brick sont faux. » · « Ma sortie a été coupée en deux, recalcule. » · « Quelles séances ont été regroupées cette semaine ? »
Catalogue complet : list_activity_groups (`Voir mes séances regroupées`), recompute_activity_group (`Recalculer une séance regroupée`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Ranger mes alertes — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Marque toutes mes alertes comme lues. » · « J'ai tout vu, vide mes notifications. »
Catalogue complet : set_notification_state (`Marquer les alertes comme lues`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

## Trancher ce que le coach propose

### Trancher ce que le coach propose — DISPONIBLE — PROPOSER UN CHANGEMENT
L'athlète dit : « Accepte le changement proposé pour la semaine. » · « Refuse, je garde ma semaine telle quelle. » · « Reporte cette décision à demain. »
Catalogue complet : respond_to_proposal (`Repondre a une proposition`), respond_to_daily_adaptation (`Repondre a l'adaptation du jour`), act_on_coach_event (`Agir sur un evenement du coach`), respond_to_plan_confirmation (`Répondre à un plan à confirmer`), resolve_plan_choice (`Trancher entre deux consignes`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm propose un changement : montre l'avant et l'après, et n'applique rien sans son oui.

### Signaler une blessure et la suivre — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « J'ai mal au tendon d'Achille depuis lundi. » · « Ma douleur au genou a disparu. »
Catalogue complet : declare_injury (`Declarer une blessure`), update_injury_status (`Mettre a jour une blessure`), mark_injury_healed (`Marquer une blessure guerie`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Récupérer mes nouvelles sorties et relancer une analyse — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Récupère mes dernières sorties. » · « Relance l'analyse de ma sortie de dimanche. »
Catalogue complet : trigger_provider_sync (`Synchroniser un service connecte`), request_session_analysis (`Analyser une seance realisee`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Préparer mon ravitaillement et noter mes prises — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Comment je me ravitaille sur ce marathon ? » · « J'ai pris un gel au trentième kilomètre. » · « J'ai sauté le ravitaillement du deuxième tour. »
Catalogue complet : compute_fuel_plan (`Calculer un plan de ravitaillement`), log_nutrition_intake (`Journaliser une prise alimentaire`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Répondre à une proposition d'adaptation — DISPONIBLE — PROPOSER UN CHANGEMENT
L'athlète dit : « Qu'est-ce que Prizm me propose ? » · « Je prends la deuxième option. » · « Applique l'adaptation à partir de lundi. »
Catalogue complet : get_compliance_proposal (`Voir la proposition d'adaptation`), request_compliance_proposal (`Demander une proposition d'adaptation`), select_compliance_option (`Choisir une option d'adaptation`), apply_compliance_option (`Appliquer l'adaptation choisie`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm propose un changement : montre l'avant et l'après, et n'applique rien sans son oui.

### Retirer un objectif de ma saison — DISPONIBLE — PROPOSER UN CHANGEMENT
L'athlète dit : « Le marathon est annulé, retire-le de ma saison. » · « Je ne ferai pas le 10 km de septembre. » · « Enlève cet objectif mais garde mon objectif principal. »
Catalogue complet : cancel_season_objective (`Retirer un objectif de la saison`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm propose un changement : montre l'avant et l'après, et n'applique rien sans son oui.

### Ma calibration métabolique — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Où j'en suis dans ma calibration ? » · « Lance le protocole de calibration. » · « Il me reste quoi à faire pour finir les mesures ? »
Catalogue complet : get_calibration_status (`Où en est ma calibration`), start_metabolic_calibration (`Démarrer la calibration métabolique`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Réparer mon plan de saison — DISPONIBLE — PROPOSER UN CHANGEMENT
L'athlète dit : « Mon calendrier affiche deux fois la même semaine. » · « Il y a deux blocs qui se chevauchent dans ma saison. » · « Répare mon plan, il est incohérent. »
Catalogue complet : fix_season_plan_overlap (`Réparer ma saison`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm propose un changement : montre l'avant et l'après, et n'applique rien sans son oui.

## Tenir ton plan quand la vie s'en mêle

### Préparer et créer mon premier plan — PLANIFIÉ — À VENIR
L'athlète dit : « Prépare mon premier plan à partir de mon profil. » · « Montre-moi l'aperçu avant de confirmer. » · « Valide l'aperçu et crée mon premier plan. » · « Où en est la création de mon premier plan ? »
À retenir : Pas encore disponible depuis l'assistant : dis-le, ne propose aucun substitut.

### Adapter mon plan moi-même — DISPONIBLE — PROPOSER UN CHANGEMENT
L'athlète dit : « Je ne peux plus m'entraîner le mardi ce mois-ci. » · « Déplace ma sortie longue au dimanche. » · « Allège ma semaine, je pars en déplacement. » · « Pas de course rapide le mardi. »
Catalogue complet : move_or_skip_session (`Deplacer ou passer une seance`), preview_merge_sessions (`Prévisualiser une fusion de séances`), apply_merge_sessions (`Confirmer une fusion de séances`), preview_athlete_constraints (`Vérifier mes contraintes de cycle`), set_athlete_constraints (`Appliquer mes contraintes de cycle`), set_cycle_constraints (`Poser mes contraintes sur un cycle`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm propose un changement : montre l'avant et l'après, et n'applique rien sans son oui.

### Composer une séance et l'envoyer sur ma montre — DISPONIBLE — PROPOSER UN CHANGEMENT
L'athlète dit : « Prépare-moi un 4x8 minutes au seuil pour jeudi. » · « Envoie cette séance sur ma Garmin. » · « Crée cette séance dans Prizm et envoie-la sur Wahoo. » · « Ajoute cette séance même si mon cycle est cassé. » · « Ma séance de demain n'est pas arrivée sur ma montre. »
Catalogue complet : preview_planned_session (`Previsualiser une seance`), create_planned_session (`Creer une seance et l'envoyer`), generate_race_session (`Fabriquer la séance du jour J`), retry_provider_push (`Renvoyer une seance sur la montre`), reschedule_provider_push (`Replanifier une séance sur la montre`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm propose un changement : montre l'avant et l'après, et n'applique rien sans son oui.

### Supprimer une séance de Prizm et des services — DISPONIBLE — PROPOSER UN CHANGEMENT
L'athlète dit : « Supprime ma séance de demain de Prizm et de Garmin. » · « Retire cette séance de Wahoo et de mon calendrier Prizm. » · « Vérifie que la séance a bien été supprimée partout. »
Catalogue complet : preview_session_deletion (`Vérifier avant suppression`), remove_session_from_plan (`Supprimer une séance planifiée`), get_session_deletion_status (`Vérifier la suppression d'une séance`), retry_session_deletion (`Reprendre une suppression déjà confirmée`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm propose un changement : montre l'avant et l'après, et n'applique rien sans son oui.

### Mes tests et mes seuils — DISPONIBLE — PROPOSER UN CHANGEMENT
L'athlète dit : « J'ai refait un test de course, mets à jour mes repères. » · « Ce n'était pas un test, écarte-le. » · « Mets à jour ma puissance à vélo après mon test d'hier. »
Catalogue complet : list_test_proposals (`Tests à valider`), validate_test_proposal (`Valider un test`), dismiss_test_proposal (`Écarter un test proposé`), record_manual_test (`Enregistrer un test passé`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm propose un changement : montre l'avant et l'après, et n'applique rien sans son oui.

### Régler ma façon d'être coaché et mon matériel — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Parle-moi de façon plus directe. » · « Explique-moi les chiffres plus simplement. » · « Je préfère mes séances dures le mardi. » · « J'ai changé de vélo. »
Catalogue complet : set_coaching_preferences (`Régler le ton du coaching`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

## Donner un nouvel objectif à ta saison

### Ajouter une course ou un objectif — DISPONIBLE — PROPOSER UN CHANGEMENT
L'athlète dit : « Ajoute le marathon de Paris du douze avril. »
Catalogue complet : request_objective (`Demander l'ajout d'un objectif`), resolve_objective_request (`Trancher une demande d'objectif`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm propose un changement : montre l'avant et l'après, et n'applique rien sans son oui.

## Préparer mes prochaines semaines

### Préparer mes prochaines semaines — DISPONIBLE — AJOUTER UNE INFORMATION
L'athlète dit : « Prépare mes prochaines semaines d'entraînement. » · « Génère-moi un nouveau cycle. »
Catalogue complet : generate_training_cycle (`Lancer la génération d'un cycle`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : L'athlète ajoute une information : relis-lui ce que tu vas enregistrer et attends son oui.

### Publier le cycle — DISPONIBLE — PROPOSER UN CHANGEMENT
L'athlète dit : « Publie ce cycle. » · « Mets ce plan dans mon calendrier. » · « C'est bon, je valide ce cycle. »
Catalogue complet : publish_cycle_draft (`Publier le cycle préparé`)
ChatGPT standard : non atteignable, dis-le et renvoie vers l'application Prizm ou vers Claude.
À retenir : Prizm propose un changement : montre l'avant et l'après, et n'applique rien sans son oui.
