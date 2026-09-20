# Fase 1.1 — Estado actual de Notion (entregable)

Inspección real vía Notion MCP, sin eliminar ni renombrar nada. Cubre lo pedido en Fase 1.1 del roadmap.

## Bases encontradas relacionadas con Canal Digital

| Base | Ubicación | Qué es hoy | Filas reales vistas |
|---|---|---|---|
| **Bitacora de Experimentos** | página "Go-To-Market Canal Digital TFE" | AB tracker chico: Nombre, Negocio, Paso, Estado, Fecha Inicio, ABT/Diseño/Ticket (urls), Puntaje | no leídas todavía fila por fila |
| **Bitácora Ecommerce** | top-level | Log operativo compartido por **toda la organización**. Tipo (A/B Test/Bug/Incidencia/Despliegue), Owner, Responsable, scoring RICE, fechas, relation rota a Certificaciones | no inspeccionado en detalle (fuera de scope: es de toda la org) |
| **Bitácora Ecommerce TFE** | top-level | Clon del anterior, pero de uso **exclusivo de este equipo**. Mismo schema. | 5 filas leídas (12/ago–10/sep/2026), todas Tipo=A/B Test |
| **Bitácora Retail** | top-level | Misma familia, no inspeccionada | — |
| **🐞 Certificaciones Ecommerce** | desconocida | Existe como relation desde Bitácora Ecommerce / Ecommerce TFE, pero la data source (`collection://9a274a89-0795-4923-b54e-481c0e457fe1`) devuelve **404** — el conector MCP no tiene acceso | inaccesible |

## Duplicaciones identificadas

- "Bitácora Ecommerce" vs. "Bitácora Ecommerce TFE": duplicación **intencional** confirmada por el usuario — la primera es de toda la organización, la segunda es de uso exclusivo del equipo.
- "Bitacora de Experimentos" vs. "Bitácora Ecommerce TFE": **se solapan conceptualmente** (ambas registran AB tests) pero con schemas distintos y sin relación entre sí. Ninguna tiene hoy los campos que pide Fase 1.5 (Hipótesis, ID VWO, Resultado, Decisión, Aprendizaje).

## Comparación contra el roadmap

| Pieza del roadmap | ¿Existe hoy? | Dónde / gap |
|---|---|---|
| Digital Log (Fase 1.2) | **No existe** | Ninguna base actual tiene los tipos genéricos (Release, Decisión, Hallazgo, Certificación, TI, CRM, Proceso, Otro) — todo lo que existe está acotado a A/B Test/Bug/Incidencia/Despliegue |
| Experimentos normalizado (Fase 1.5) | Parcial | "Bitacora de Experimentos" es la base correcta a normalizar (no Bitácora Ecommerce TFE). Faltan: Hipótesis, ID VWO, URL origen, URL variación, Resultado, Decisión, Aprendizaje, relation a Digital Log |
| Aprendizajes (Fase 1.7) | No existe | — |
| Retrospectivas (Fase 1.9) | No existe como base/página estructurada | Hay una retro de prueba (borrador, página suelta) creada ayer sobre datos de Bitácora Ecommerce TFE — sirve como piloto de formato, no como la base definitiva |
| Reglas QA / Certificaciones (Fase 2) | Certificaciones existe pero sin acceso; Reglas QA no existe | Fuera de alcance de Fase 1 |

## Restricciones de acceso vigentes

- No inspeccionar ni escribir nada bajo **"Dashboard CRO TFE"**.
- No escribir en **"Bitácora Ecommerce"** (org-wide) ni en **"Bitácora Retail"** sin autorización nueva.
- No se puede leer **"🐞 Certificaciones Ecommerce"** — pedirle a quien la administra que comparta la data source con la integración de Notion MCP si se necesita para Fase 2.

## Qué se puede reutilizar

- "Bitacora de Experimentos" ya tiene el concepto correcto (AB tests) y algunos campos base (Negocio, Paso, Estado, Fecha Inicio) — normalizarla en vez de crear una tercera base de experimentos.
- El patrón de vistas (Calendario, Cronograma Full, Backlog Ideas) de las bitácoras existentes es reutilizable para Digital Log y Experimentos.

## Propuesta de cambios mínimos para Fase 1 (sin ejecutar todavía)

1. **Crear "Digital Log"** como base nueva (no reemplaza nada existente), con las propiedades mínimas del roadmap: Evento, Fecha, Tipo, Descripción, Relacionado con, Responsable, Estado, Evidencia, Incluir en retro.
2. **Normalizar "Bitacora de Experimentos"** agregando: Hipótesis, ID VWO, URL origen, URL variación/redirect, Fecha fin, Resultado, Decisión, Aprendizaje, relation a Digital Log. **No tocar los datos existentes.**
3. Dejar **Bitácora Ecommerce TFE tal cual está** — no se toca, no se migra, sigue viva para lo que el equipo ya usa hoy (la retro de prueba de ayer puede archivarse o convertirse en el primer registro de Digital Log una vez exista).
4. No tocar "Bitácora Ecommerce" ni "Bitácora Retail".

## Riesgos

- Crear Digital Log sin coordinarlo puede generar una **cuarta** bitácora paralela si el equipo no lo adopta — mitigación: capacitación de 20-30 min (Fase 1.12) antes de darlo por hecho.
- Normalizar "Bitacora de Experimentos" con campos nuevos no rompe datos existentes (son columnas nuevas), pero si alguien ya usa esa base para otra cosa fuera de lo visto acá, hay que confirmarlo antes.
- Seguimos sin acceso a Certificaciones — cualquier intento de automatizar QA (Fase 2) va a chocar con esto de nuevo.

## Gate

~~No se ejecuta ningún cambio en Notion (crear Digital Log, agregar campos a Experimentos) hasta que este plan sea aprobado explícitamente.~~

**Aprobado y ejecutado el 2026-09-20.** Digital Log creada (https://app.notion.com/p/58a9d8fd6f8047c6b9b04e70239a1406) y "Bitacora de Experimentos" normalizada de forma aditiva — cero datos existentes tocados. Ver `references/notion-schema.md` para el detalle final.
