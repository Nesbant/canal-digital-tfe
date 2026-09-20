# Schema real de Notion — fuente de verdad para los skills

Si el schema cambia en Notion, este archivo se actualiza primero; los skills lo leen antes de escribir o leer nada.

## ⚠️ Estado: Digital Log y Experimentos normalizado NO EXISTEN todavía

Los skills de este toolkit (`registro`, `experimentacion`, `knowledge-search`, `revision-semanal`) asumen las bases de abajo marcadas como "objetivo". **Ninguna se creó/modificó en Notion todavía** — ver `docs/fase-1-estado-actual-notion.md` para el plan pendiente de aprobación. Hasta que se apruebe y ejecute, estos skills no tienen dónde escribir.

## Digital Log (objetivo — Fase 1.2, no creada)

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

## Experimentos (objetivo normalizado — Fase 1.5, base real: "Bitacora de Experimentos")

Base real hoy: https://app.notion.com/p/3524df488cbc80549113e5caf4afa6a1 (`collection://3524df48-8cbc-81ff-a6c5-000b8f0be2a0`), bajo "Go-To-Market Canal Digital TFE".

Campos actuales: Nombre (title), Negocio (select: Tren/TFE), Paso (select: Paso 0-6, Contac center), Estado (status: Idea/Desarrollo/Producción/Testing/Pausado/Done), Fecha Inicio (date), ABT/Diseño/Ticket (url), Puntaje (formula).

Campos a **agregar** (no se toca lo existente):

| Campo | Tipo |
|---|---|
| Hipótesis | text |
| ID VWO | text |
| URL origen | url |
| URL variación / redirect | url |
| Fecha fin | date |
| Resultado | text |
| Decisión | select |
| Aprendizaje | text |
| Digital Log | relation |

## Bitácora Ecommerce TFE (base real, en uso — NO es el objetivo de este toolkit)

Base de uso exclusivo del equipo (no confundir con "Bitácora Ecommerce", que es de toda la organización). URL: https://app.notion.com/p/3cf4df488cbc807bbc23dbae572a70d5 (`collection://f3b4df48-8cbc-8205-9c8f-879320f32419`).

Sigue viva y en uso — el roadmap no pide migrarla ni eliminarla. La retro de prueba generada el 2026-09-19 (https://app.notion.com/p/3e04df488cbc8139a38fc48457b5c20e) se hizo sobre esta base, antes de que existiera este toolkit formal; queda como piloto de formato, no como parte del pipeline definitivo.

## Boundary duro (aplica a todos los skills de este toolkit)

- Nunca escribir en **"Bitácora Ecommerce"** (org-wide) ni en **"Bitácora Retail"**.
- Nunca leer ni escribir nada bajo **"Dashboard CRO TFE"**.
- **"🐞 Certificaciones Ecommerce"** (`collection://9a274a89-0795-4923-b54e-481c0e457fe1`) da 404 — el conector no tiene acceso. No asumir contenido ahí. Relevante recién en Fase 2.
- No crear bases nuevas ni modificar propiedades existentes sin confirmación explícita del usuario en el momento (ver `docs/governance.md`).
