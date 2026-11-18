# Prizm pour Claude Code

Branche Claude Code sur ton compte Prizm : forme du jour, zones et seuils, plan de la
semaine, séances réalisées, saison et courses. Le plugin apporte le connecteur
(`https://mcp.prizm-coach.com/mcp`) et le skill `coach-prizm`.

## Installer

```bash
claude plugin marketplace add prizm-coach/claude-plugins
claude plugin install prizm@prizm-plugins
```

Dans une session Claude Code, tape ensuite `/mcp`, choisis **prizm** et connecte-toi à
ton compte Prizm dans le navigateur. Premier essai : « Comment est ma forme aujourd'hui ? ».
Le skill s'appelle `/prizm:coach-prizm`.

## Couper l'accès

Depuis ton espace Prizm (`https://assistant.prizm-coach.com/espace.html`), ou en
désinstallant le plugin : `claude plugin uninstall prizm@prizm-plugins`.

## Ce que fait ce plugin, et ce qu'il envoie

- **Il n'exécute rien sur ta machine** : aucun script, aucun hook, aucune commande locale. Il ajoute un skill (`coach-prizm`, des consignes de coaching en texte) et déclare une connexion à un serveur distant.
- **Serveur distant :** `https://mcp.prizm-coach.com/mcp`, en HTTPS. Tu t'y connectes avec ton propre compte Prizm (connexion OAuth dans le navigateur). Sans compte Prizm, le plugin ne renvoie rien.
- **Données lues, uniquement les tiennes :** forme du jour, zones et seuils, plan de la semaine, séances réalisées, saison et courses. Une partie relève de la **santé** au sens du RGPD (article 9) : fréquence cardiaque, sommeil, récupération et valeurs qui en découlent. Tu donnes ton consentement explicite dans Prizm avant que ces données soient lisibles.
- **Ce que le plugin peut écrire :** selon les droits donnés à ton compte, il peut enregistrer des informations (par exemple un check-in, une note de séance ou une séance planifiée). Pour les séances, un aperçu précède l'enregistrement. Tu peux couper l'accès à tout moment depuis ton espace Prizm.
- **Autres services :** le plugin lui-même ne contacte que le serveur Prizm. Comment Prizm et ses prestataires traitent ensuite tes données est décrit dans la politique de confidentialité ci-dessous. Le plugin ne contacte aucun autre service.
- **Politique de confidentialité :** https://prizm-coach.com/privacy.html#mcp-assistant-connector
- **Support :** support@prizm-coach.com
