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
