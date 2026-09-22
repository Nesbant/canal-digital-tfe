# TFE AI Toolkit

Capa de IA para el equipo de Canal Digital TFE (Inca Rail): memoria operativa, trazabilidad de experimentos, conocimiento reutilizable de certificación y, en fases posteriores, asistencia y automatización de pruebas.

Este repo sigue el roadmap en `docs/roadmap.md`. **Fuente de verdad de fases y alcance: esa copia y el original en la raíz del proyecto (`Proyecto_IA_Canal_Digital_TFE_Roadmap.md`).**

## Estado actual

- **Fase 0 (Preparación):** en curso — estructura técnica creada; gates organizacionales (alcance validado con Juan, definición de permisos/ownership) **pendientes**, no resueltos por Claude.
- **Fase 1 (Team Memory):** en diseño — ver `docs/fase-1-estado-actual-notion.md` para el estado real de Notion y el plan propuesto. **Ningún cambio se ejecutó todavía en Notion** para esta fase; falta aprobación explícita.

## Instalación (equipo)

1. `claude mcp add --transport http notion https://mcp.notion.com/mcp` (una vez por persona/máquina, fuera de Claude Code)
2. Dentro de Claude Code: `/mcp` → elegir `notion` → **Authenticate** → aprobar en el navegador con tu propia cuenta
3. `/plugin marketplace add Nesbant/canal-digital-tfe`
4. `/plugin install tfe@canal-digital`
5. Los comandos quedan disponibles como `/tfe:registrar`, `/tfe:experimento`, `/tfe:buscar`, `/tfe:semana`. Si no aparecen, correr `/reload-plugins`.

## Estructura

```text
tfe-ai-toolkit/
├── README.md
├── docs/            → alcance, seguridad, gobernanza, roadmap, estado de Notion
├── commands/        → comandos /tfe:* (solo los de Fase 1 implementados hasta ahora)
├── skills/          → procedimientos que los comandos invocan
├── references/       → schema real de Notion y políticas (fuente de verdad para los skills)
├── automation/      → reservado para Fase 4 (Playwright) — vacío por ahora
└── changelog/        → historial de cambios de este toolkit
```

## Principios (ver roadmap completo para el resto)

1. No reemplazar owners existentes.
2. No cambiar procesos que ya funcionan sin necesidad.
3. Notion es memoria operativa, no un duplicado de todas las herramientas.
4. Las decisiones importantes siguen siendo humanas.
5. No avanzar a la siguiente fase hasta que la anterior tenga uso real.
