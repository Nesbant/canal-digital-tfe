# Alcance del proyecto (Fase 0.1)

> Entregable equivalente a `00-alcance-proyecto.md` del roadmap.

## Objetivo general

Incorporar una capa de IA al trabajo del equipo de Canal Digital TFE para mejorar ejecución, memoria, calidad de certificación, trazabilidad de experimentos y reutilización del conocimiento, **sin cambiar el ownership actual de cada función**.

Ver `docs/roadmap.md` para el detalle completo de fases, principios y arquitectura.

## Decidido hasta ahora

- Fase 1 se enfoca solo en Notion + Claude (memoria operativa). Fase 2 en adelante (QA Knowledge, certificación asistida, automatización) es explícitamente posterior y no empieza hasta que Fase 1 tenga uso real.
- El sistema no reemplaza Power BI, VWO, Excel de TI, Figma ni HubSpot — Notion es memoria, no un duplicado de esas herramientas.
- Convención de nomenclatura: castellano para nombres de bases/propiedades en Notion (consistente con lo ya existente); inglés para identificadores técnicos del repo (`tfe-ai-toolkit`, nombres de skill).

## Pendiente de validar con Juan (Fase 0.1 — no resuelto por Claude)

- [ ] Validar alcance del proyecto con Juan.
- [ ] Confirmar que Fase 1 se enfoca solo en Notion + Claude.
- [ ] Confirmar que no se modificará el proceso actual de tickets.
- [ ] Confirmar que no se reemplazará el ownership de analítica, UX, TI o negocio.
- [ ] Definir quién puede aprobar cambios del sistema.
- [ ] Definir quién puede crear/modificar bases de Notion.
- [ ] Definir qué información no debe registrarse en Claude/Notion.

Ver también `docs/governance.md` (roles) y `docs/seguridad.md` (reglas de seguridad).
