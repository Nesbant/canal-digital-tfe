# 2026-09-22 — Rename del plugin + guía de onboarding

- **Fix importante**: el plugin se llamaba `tfe-ai-toolkit`, lo que hacía que los comandos reales quedaran namespaced como `/tfe-ai-toolkit:registrar` en vez de `/tfe:registrar` (el nombre que usa el roadmap en todos lados). Se renombró el plugin a `tfe` en `plugin.json` y `marketplace.json` — ahora los comandos coinciden exactamente con lo documentado.
- Instalación actualizada: `/plugin install tfe@canal-digital`.
- Creado `docs/onboarding.md` (Fase 1.12): pasos verificados para que cualquiera del equipo conecte su propio Notion MCP e instale el plugin, con ejemplo real de uso y las reglas duras (no PII, no cerrar experimentos incompletos).
- `claude plugin validate .` → limpio después del rename.
