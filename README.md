# Prizm — plugins pour Claude Code

Place de marché (marketplace) de plugins Claude Code publiée par Prizm
(<https://prizm-coach.com/>). Elle contient un plugin, `prizm`.

## Ce que fait le plugin

Il branche Claude Code sur ton compte Prizm : forme du jour, zones et seuils, plan de la
semaine, séances réalisées, saison et courses. Il ajoute aussi le skill `coach-prizm`,
qui apprend à Claude à se comporter comme ton coach d'endurance : citer tes repères tels
que Prizm les donne, sans jamais les recalculer.

Exemple : « Comment est ma forme aujourd'hui ? » → Claude lit ta forme dans Prizm et te
répond avec une consigne pour la séance du jour.

## Compte Prizm requis

Le plugin ne fonctionne qu'avec un compte Prizm. Tu te connectes dans le navigateur au
premier usage ; l'accès reste limité à ton compte et tu peux le couper à tout moment
depuis ton espace Prizm.

Lecture et écriture dépendent des droits de ton compte : un compte autorisé en lecture
seule consulte ses données ; un compte autorisé en écriture peut aussi enregistrer des
actions (par exemple noter une séance), toujours après relecture avec toi.

## Installation

```text
/plugin marketplace add prizm-coach/claude-plugins
/plugin install prizm@prizm-plugins
```

Ou en ligne de commande :

```bash
claude plugin marketplace add prizm-coach/claude-plugins
claude plugin install prizm@prizm-plugins
```

`prizm-coach/claude-plugins` est `propriétaire/nom-du-dépôt` sur GitHub, ou une URL Git.
Ensuite, dans une session : `/mcp`, choisis **prizm** et connecte-toi.

## Liens

- Documentation : <https://assistant.prizm-coach.com/espace.html>
- Confidentialité : <https://prizm-coach.com/privacy.html#mcp-assistant-connector>
- Conditions : <https://prizm-coach.com/terms.html>

## Support

Une question ou un souci d'installation : support@prizm-coach.com
