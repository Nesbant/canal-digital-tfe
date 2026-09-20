# Schema real de Notion — fuente de verdad para los skills

Si el schema cambia en Notion, este archivo se actualiza primero; los skills lo leen antes de escribir o leer nada.

## ✅ Estado: Digital Log creada y Experimentos normalizado (2026-09-20)

Ambos cambios ya se ejecutaron en Notion, de forma aditiva (no se tocó ningún dato existente). Los skills `registro`, `experimentacion`, `knowledge-search` y `revision-semanal` ya pueden operar.

## Digital Log (creada — Fase 1.2)

- URL: https://app.notion.com/p/58a9d8fd6f8047c6b9b04e70239a1406
- Data source: `collection://2771132d-97bf-45eb-968d-300102270aa2`
- Ubicación: bajo "Go-To-Market Canal Digital TFE", junto a "Bitacora de Experimentos".
- Relation "Relacionado con" ↔ "Bitacora de Experimentos" (dos vías; del lado de Experimentos aparece como propiedad "Digital Log").

| Campo | Tipo | Notas |
|---|---|---|
| Evento | title | — |
| Fecha | date | — |
| Tipo | select | Experimento, Release, Incidencia, Decisión, Hallazgo, Certificación, TI, CRM, Proceso, Otro |
| Descripción | text | — |
| Relacionado con | relation / url | hacia Experimentos, Certificaciones, etc. |
| Responsable | person | — |
| Estado | select | — |
| Evidencia | url / files | — |
| Incluir en retro | checkbox | — |

## Experimentos (normalizada — Fase 1.5, base real: "Bitacora de Experimentos")

URL: https://app.notion.com/p/3524df488cbc80549113e5caf4afa6a1 (`collection://3524df48-8cbc-81ff-a6c5-000b8f0be2a0`), bajo "Go-To-Market Canal Digital TFE".

Campos originales (intactos): Nombre (title), Negocio (select: Tren/TFE), Paso (select: Paso 0-6, Contac center), Estado (status: Idea/Desarrollo/Producción/Testing/Pausado/Done), Fecha Inicio (date), ABT/Diseño/Ticket (url), Puntaje (formula).

Campos **agregados** el 2026-09-20 (aditivo, cero filas existentes modificadas):

| Campo | Tipo |
|---|---|
| Hipótesis | text |
| ID VWO | text |
| URL origen | url |
| URL variación / redirect | url |
| Fecha fin | date |
| Resultado | text |
| Decisión | select (Escalar / Iterar / Descartar / Pendiente) |
| Aprendizaje | text |
| Digital Log | relation (auto-creada por el two-way relation desde Digital Log) |

## Bitácora Ecommerce TFE (base real, en uso — NO es el objetivo de este toolkit)

Base de uso exclusivo del equipo (no confundir con "Bitácora Ecommerce", que es de toda la organización). URL: https://app.notion.com/p/3cf4df488cbc807bbc23dbae572a70d5 (`collection://f3b4df48-8cbc-8205-9c8f-879320f32419`).

Sigue viva y en uso — el roadmap no pide migrarla ni eliminarla. La retro de prueba generada el 2026-09-19 (https://app.notion.com/p/3e04df488cbc8139a38fc48457b5c20e) se hizo sobre esta base, antes de que existiera este toolkit formal; queda como piloto de formato, no como parte del pipeline definitivo.

## Aprendizajes (creada — Fase 1.7)

- URL: https://app.notion.com/p/de75f35d6ce644b0b0a1cd78d42bfc77
- Data source: `collection://b5da647a-7d02-4116-9f99-4534d982b0f5`
- Campos: Aprendizaje (title), Descripción (text), Experimento origen (relation → Experimentos), Digital Log (relation → Digital Log), Producto (multi-select: FDM/Actividad/Paquete/Bundle/All Inclusive/Tours/Otro — lista inicial, ajustable), Funnel (multi-select: P1-P6/Contact Center), Tipo (select: Proceso/Producto/QA/Pricing/UX/Técnico/Otro), Fecha (date), Evidencia (url), Estado (select: Propuesto/Activo/Descartado).
- Vistas: "Por tipo" (board), "Potencial QA" (filtro Tipo=QA). Falta "Por producto" (Producto es multi-select, no admite board por ahora — filtrar manualmente en Notion si hace falta).

## Retrospectivas (creada — Fase 1.9)

- URL: https://app.notion.com/p/6799344710404d998b1ce4c0aab7fc25
- Data source: `collection://09f8ca92-4cbd-4448-b8e5-5af6de9d8117`
- Campos: Nombre (title), Desde/Hasta (date), Tipo (select: Semanal/Mensual), Estado (select: Borrador/Revisada/Presentada), relations a Digital Log, Experimentos y Aprendizajes, Fecha generación/aprobación (date).
- El contenido de la retro (✅❌🎯🚀) va en el cuerpo de la página, no en propiedades — ver `references/retrospectiva.md`.
- Vista: "Por estado" (board).

## Boundary duro (aplica a todos los skills de este toolkit)

- Nunca escribir en **"Bitácora Ecommerce"** (org-wide) ni en **"Bitácora Retail"**.
- Nunca leer ni escribir nada bajo **"Dashboard CRO TFE"**.
- **"🐞 Certificaciones Ecommerce"** (`collection://9a274a89-0795-4923-b54e-481c0e457fe1`) da 404 — el conector no tiene acceso. No asumir contenido ahí. Relevante recién en Fase 2.
- No crear bases nuevas ni modificar propiedades existentes sin confirmación explícita del usuario en el momento (ver `docs/governance.md`).
