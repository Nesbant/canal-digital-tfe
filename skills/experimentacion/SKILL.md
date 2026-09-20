# Experimentación

## ⚠️ Precondición
La normalización de "Bitacora de Experimentos" (agregar Hipótesis, ID VWO, URLs, Resultado, Decisión, Aprendizaje, relation a Digital Log) todavía no se ejecutó. Ver `docs/fase-1-estado-actual-notion.md`. No usar los modos `crear`/`actualizar`/`cerrar` hasta que esos campos existan.

## Objetivo
Mantener la bitácora de experimentos trazable de punta a punta: hipótesis → resultado → decisión → aprendizaje.

## Modos
- **crear**: nuevo experimento. Buscar experimentos relacionados por nombre/fecha/ID VWO antes de crear uno nuevo, para no duplicar.
- **consultar**: traer el estado actual de un experimento por nombre, fecha o ID VWO.
- **actualizar**: cambiar estado, registrar resultado o decisión.
- **cerrar**: cerrar el experimento. **Obligatorio** registrar Resultado, Decisión y Aprendizaje antes de marcarlo cerrado — si falta alguno, preguntar antes de cerrar.
- **buscar**: encontrar experimentos por tema, producto o funnel.

## Reglas
- Un experimento cerrado sin Resultado + Decisión + Aprendizaje no cumple el criterio de aceptación — no cerrarlo así.
- Relacionar siempre con el Digital Log cuando exista un evento asociado (release, incidencia, etc.).
- Nunca inventar métricas o resultados no provistos por la persona.
