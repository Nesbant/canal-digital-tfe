# 2026-09-21 — Validación de lógica de skills (dry-run, sin escribir en Notion)

Cubre parcialmente Fase 1.3 ("Probar entradas ambiguas", "Probar entradas completas", "Validar que Claude no invente datos") y Fase 1.6 (criterio de aceptación de cierre). Casos sintéticos, no eventos reales — no se creó ninguna fila en Notion para esto.

## Test A — entrada ambigua (debe preguntar, no crear)

**Input**: "Hoy hubo un problema con el checkout."

**Traza contra `skills/registro/SKILL.md`**: falta "sobre qué" (¿qué experimento/página?), `Tipo` ambiguo (¿Bug o Incidencia?), `Negocio` no inferible (¿Tren o TFE?).

**Resultado esperado**: el skill debe preguntar por estos 3 puntos antes de crear el registro. **PASS** — la regla "Si falta contexto esencial, preguntar antes de crear el registro — no adivinar" cubre los 3 casos explícitamente.

## Test B — entrada completa (debe crear directo)

**Input**: "Hoy detectamos que el experimento P2 TFE Modal Seguir Comprando mostraba el modal duplicado en mobile. TI lo escaló como incidencia SD-99999."

**Traza**: Negocio=TFE (explícito), Tipo=Incidencia (explícito "incidencia"), Nombre inferible, relación clara con el experimento real "P2 TFE | Modal Seguir Comprando" (https://app.notion.com/p/3d74df488cbc81e39792e1ff0ffa6533) vía Digital Log ↔ Experimentos.

**Resultado esperado**: crear sin preguntar, relacionar con el experimento real. **PASS** — no hay ambigüedad que dispare la regla de "preguntar antes".

## Test C — cierre de experimento incompleto (debe bloquear)

**Input**: "Cerrá el experimento Bundles Plus que elimina el guía."

**Traza contra `skills/experimentacion/SKILL.md`**: el experimento real (https://app.notion.com/p/3524df488cbc804fa8f5edf7dd78b7eb) tiene Resultado/Decisión/Aprendizaje vacíos.

**Resultado esperado**: el skill NO debe marcarlo Done sin esos 3 campos — debe preguntar por ellos primero. **PASS** — regla explícita: "Un experimento cerrado sin Resultado + Decisión + Aprendizaje no cumple el criterio de aceptación — no cerrarlo así."

## Conclusión

Las 3 reglas anti-invento funcionan como están escritas en el papel. Esto valida el **diseño** de los skills, no reemplaza probarlos con el equipo usándolos de verdad (eso sigue pendiente y requiere al equipo).
