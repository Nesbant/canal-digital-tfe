# 2026-09-22 — Repo público y plugin instalable

- Push a https://github.com/Nesbant/canal-digital-tfe (rama `main` + tags `fase-0-1-scaffold`, `fase-1-notion-executed`, `fase-1-bases-completas`, `fase-1-validacion-tecnica`).
- Creado `.claude-plugin/marketplace.json` (marketplace `canal-digital`), agregado `author` a `plugin.json`.
- `claude plugin validate .` → validación limpia, sin warnings.
- Documentado en README el flujo de instalación para el equipo: `/plugin marketplace add Nesbant/canal-digital-tfe` → `/plugin install tfe-ai-toolkit@canal-digital` → cada persona conecta su propio MCP de Notion (esto último no lo automatiza el plugin, confirmado con el agente especializado de Claude Code).
