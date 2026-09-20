# Proyecto IA para Canal Digital TFE
## Roadmap por fases, tareas y entregables

> **Versión:** 1.0  
> **Área:** Canal Digital TFE — Inca Rail  
> **Idioma operativo:** Español  
> **Objetivo general:** incorporar una capa de IA al trabajo del equipo para mejorar ejecución, memoria, calidad de certificación, trazabilidad de experimentos y reutilización del conocimiento, sin cambiar el ownership actual de cada función.

---

# 1. Norte del proyecto

El proyecto no busca “usar IA” por sí misma.

Busca que el equipo pueda:

- registrar mejor lo relevante;
- recuperar contexto rápidamente;
- perder menos conocimiento;
- preparar retrospectivas con menos trabajo manual;
- mantener experimentos trazables;
- convertir errores en aprendizaje reusable;
- certificar con mayor cobertura;
- automatizar progresivamente pruebas repetitivas;
- ejecutar más cambios con menos errores y menos carga operativa.

La evolución completa será:

```text
MEMORIA
   ↓
CONOCIMIENTO
   ↓
ASISTENCIA
   ↓
AUTOMATIZACIÓN
```

---

# 2. Principios del proyecto

1. **No reemplazar owners existentes.**
2. **No cambiar procesos que ya funcionan sin necesidad.**
3. **Claude debe adaptarse al trabajo actual del equipo.**
4. **Notion será memoria operativa, no un duplicado de todas las herramientas.**
5. **Claude estructura, recupera, relaciona y propone.**
6. **Las decisiones importantes siguen siendo humanas.**
7. **Automatizar solo procesos entendidos y repetitivos.**
8. **Cada fase debe entregar valor por sí sola.**
9. **No avanzar a la siguiente fase hasta que la anterior tenga uso real.**
10. **Toda automatización debe reducir tiempo, errores o pérdida de conocimiento.**

---

# 3. Sistemas existentes que se mantienen

```text
Power BI / SQL / BigQuery / GA4
→ datos y análisis

VWO
→ ejecución de experimentos A/B

Excel / herramientas TI
→ gestión oficial de desarrollo

Figma
→ diseño UX/UI

HubSpot
→ CRM

Notion
→ memoria, contexto, retrospectivas y conocimiento

Claude
→ capa de IA transversal

Chrome DevTools MCP
→ certificación asistida en fases posteriores

Playwright
→ automatización de regresión en fases posteriores
```

---

# 4. Frame operativo del equipo

El proyecto no crea una nueva metodología de trabajo.

Se apoya sobre el trabajo real del equipo:

```text
TRABAJAR
   ↓
REGISTRAR LO RELEVANTE
   ↓
MANTENER CONTEXTO
   ↓
RECUPERAR CONOCIMIENTO
   ↓
REVISAR
   ↓
APRENDER
   ↓
MEJORAR
```

Para iniciativas y cambios:

```text
DETECTAR
   ↓
DEFINIR
   ↓
PRIORIZAR
   ↓
EJECUTAR
   ↓
VALIDAR
   ↓
APRENDER
```

Claude ayuda en el frame, pero no decide por el equipo.

---

# 5. Arquitectura objetivo

```text
                         EQUIPO
                           │
                           ▼
                        CLAUDE
                           │
             ┌─────────────┼─────────────┐
             ▼             ▼             ▼
          CAPTURA       CONTEXTO       ASISTENCIA
             │             │             │
             └─────────────┼─────────────┘
                           ▼
                         NOTION
                           │
             ┌─────────────┼─────────────┐
             ▼             ▼             ▼
          Digital       Experimentos   Aprendizajes
            Log
             │             │             │
             └─────────────┼─────────────┘
                           ▼
                     Retrospectivas
                           │
                           ▼
                    Knowledge Base
                           │
                           ▼
                     QA Knowledge
                           │
                           ▼
             Chrome DevTools / Playwright
```

---

# 6. Roadmap general

| Fase | Nombre | Objetivo principal |
|---|---|---|
| 0 | Preparación | Alinear alcance, seguridad y estructura |
| 1 | Team Memory | Dar memoria operativa al equipo con Notion + Claude |
| 2 | QA Knowledge | Convertir experiencia y errores en reglas de certificación |
| 3 | Assisted Certification | Usar Claude + Chrome DevTools MCP para certificar |
| 4 | Automated Regression | Automatizar regresiones repetitivas con Playwright |
| 5 | Scale & Integration | Integrar fuentes y escalar herramientas que demostraron valor |

---

# FASE 0 — Preparación

## Objetivo

Preparar el entorno sin modificar procesos ni información existente.

## Resultado esperado

- alcance validado;
- Notion inspeccionado;
- permisos definidos;
- repositorio creado;
- estructura técnica inicial disponible.

## 0.1. Alineamiento

- [ ] Validar alcance del proyecto con Juan.
- [ ] Confirmar que Fase 1 se enfoca solo en Notion + Claude.
- [ ] Confirmar que no se modificará el proceso actual de tickets.
- [ ] Confirmar que no se reemplazará el ownership de analítica, UX, TI o negocio.
- [ ] Definir quién puede aprobar cambios del sistema.
- [ ] Definir quién puede crear/modificar bases de Notion.
- [ ] Definir qué información no debe registrarse en Claude/Notion.
- [ ] Definir nomenclatura general del proyecto.

### Entregable

`00-alcance-proyecto.md`

## 0.2. Seguridad y permisos

- [ ] Confirmar acceso del equipo a Claude.
- [ ] Confirmar conexión disponible con Notion MCP.
- [ ] Validar permisos de lectura/escritura del Teamspace.
- [ ] Definir páginas/bases donde Claude puede escribir.
- [ ] Evitar guardar credenciales.
- [ ] Evitar guardar datos personales de pasajeros innecesarios.
- [ ] Documentar límites de acceso.

### Entregable

`01-reglas-seguridad.md`

## 0.3. Repositorio

Crear:

```text
tfe-ai-toolkit/
│
├── README.md
├── docs/
├── commands/
├── skills/
├── references/
└── changelog/
```

### Tareas

- [ ] Crear repositorio Git.
- [ ] Agregar README.
- [ ] Agregar descripción del proyecto.
- [ ] Crear estructura de carpetas.
- [ ] Agregar `.gitignore`.
- [ ] Definir convención de ramas.
- [ ] Definir convención de commits.

### Entregable

Repositorio base funcional.

---

# FASE 1 — Team Memory

## Objetivo

Dar al equipo una memoria compartida y utilizable.

La Fase 1 debe permitir:

```text
PASÓ ALGO IMPORTANTE
        ↓
/tfe:registrar
        ↓
Digital Log
        ↓
Claude puede recuperarlo
        ↓
/tfe:buscar
        ↓
Fin de semana
        ↓
/tfe:semana
        ↓
Retro
```

## 1.1. Inspección del Notion actual

Antes de crear cualquier cosa:

- [ ] Conectar Notion MCP.
- [ ] Identificar páginas actuales de Canal Digital.
- [ ] Encontrar bitácora actual de experimentos.
- [ ] Identificar páginas de retrospectivas.
- [ ] Identificar duplicaciones.
- [ ] Identificar propiedades existentes.
- [ ] No eliminar información.
- [ ] No renombrar propiedades sin aprobación.
- [ ] Documentar estado actual.

### Entregable

`fase-1/01-estado-actual-notion.md`

## 1.2. Diseñar Digital Log

### Propósito

Registrar eventos importantes del equipo, no actividades rutinarias.

### Tipos iniciales

```text
Experimento
Release
Incidencia
Decisión
Hallazgo
Certificación
TI
CRM
Proceso
Otro
```

### Propiedades mínimas

| Campo | Tipo |
|---|---|
| Evento | Título |
| Fecha | Fecha |
| Tipo | Select |
| Descripción | Texto |
| Relacionado con | Relation / URL |
| Responsable | Persona |
| Estado | Select |
| Evidencia | URL / Archivo |
| Incluir en retro | Checkbox |

### Tareas

- [ ] Crear base `Digital Log`.
- [ ] Crear tipos.
- [ ] Crear estados.
- [ ] Crear vista `Esta semana`.
- [ ] Crear vista `Incidencias`.
- [ ] Crear vista `Experimentos`.
- [ ] Crear vista `Retro`.
- [ ] Crear plantilla de evento.
- [ ] Validar con 5 eventos reales.

### Entregable

Base `Digital Log` operativa.

## 1.3. Definir calidad mínima del Log

Claude debe comprobar que cada registro tenga contexto suficiente.

### Definition of a Good Log

```text
[ ] Fecha
[ ] Qué ocurrió
[ ] Sobre qué ocurrió
[ ] Contexto suficiente
[ ] Estado o resultado
[ ] Relación si existe
```

Opcionales:

```text
[ ] Evidencia
[ ] Impacto
[ ] Aprendizaje
[ ] Próximo paso
```

### Tareas

- [ ] Documentar Definition of a Good Log.
- [ ] Crear reglas para detectar contexto insuficiente.
- [ ] Definir cuándo Claude debe preguntar antes de registrar.
- [ ] Probar entradas ambiguas.
- [ ] Probar entradas completas.
- [ ] Validar que Claude no invente datos.

### Entregable

`references/digital-log-policy.md`

## 1.4. Implementar `/tfe:registrar`

### Objetivo

Permitir registrar un evento usando lenguaje natural.

### Ejemplo

```text
/tfe:registrar

Hoy se detectó que la variación del AB mostraba
tarifa extranjera en mobile en una parte del flujo.
TI ya recibió el caso.
```

Claude debe:

1. interpretar;
2. buscar contexto previo;
3. identificar experimento relacionado;
4. detectar datos faltantes;
5. pedir aclaración si es necesario;
6. crear el registro;
7. relacionarlo;
8. sugerir aprendizaje cuando corresponda.

### Tareas

- [ ] Crear command `registrar.md`.
- [ ] Crear Skill `registro/SKILL.md`.
- [ ] Crear clasificación automática.
- [ ] Crear búsqueda de relaciones.
- [ ] Crear validación de contexto.
- [ ] Crear confirmación previa si hay ambigüedad.
- [ ] Crear registro como borrador cuando corresponda.
- [ ] Probar con 10 casos reales.

### Criterio de aceptación

Claude nunca debe crear un registro ambiguo sin señalar la falta de contexto.

## 1.5. Normalizar Experimentos

### Convención actual

```text
FECHA + descripción breve
```

Ejemplo:

```text
19-09 Cards compactos tours
```

### Campos mínimos

| Campo | Tipo |
|---|---|
| Nombre | Título |
| Hipótesis | Texto |
| ID VWO | Texto |
| URL origen | URL |
| URL variación / redirect | URL |
| Fecha inicio | Fecha |
| Fecha fin | Fecha |
| Estado | Select |
| Resultado | Texto |
| Decisión | Select |
| Aprendizaje | Texto |
| Digital Log | Relation |

### Tareas

- [ ] Auditar bitácora actual.
- [ ] Mantener datos existentes.
- [ ] Definir campos mínimos.
- [ ] Agregar relación con Digital Log.
- [ ] Crear vista `Activos`.
- [ ] Crear vista `Finalizados`.
- [ ] Crear vista `Sin aprendizaje`.
- [ ] Crear vista `Sin resultado`.
- [ ] Probar con experimentos actuales.

### Entregable

Bitácora de experimentos normalizada.

## 1.6. Implementar `/tfe:experimento`

### Modos

```text
crear
consultar
actualizar
cerrar
buscar
```

### Tareas

- [ ] Crear command.
- [ ] Crear Skill.
- [ ] Detectar experimento por nombre/fecha/ID VWO.
- [ ] Permitir actualizar estado.
- [ ] Permitir registrar resultado.
- [ ] Permitir registrar decisión.
- [ ] Obligar a registrar aprendizaje al cerrar.
- [ ] Buscar experimentos relacionados antes de crear uno nuevo.
- [ ] Relacionar eventos del Digital Log.

### Criterio de aceptación

Un experimento cerrado debe tener:

```text
Resultado
Decisión
Aprendizaje
```

## 1.7. Diseñar Aprendizajes

### Objetivo

Guardar conocimiento reusable.

### Campos

| Campo | Tipo |
|---|---|
| Aprendizaje | Título |
| Descripción | Texto |
| Origen | Relation |
| Producto | Multi-select |
| Funnel | Multi-select |
| Tipo | Select |
| Fecha | Fecha |
| Evidencia | URL |
| Estado | Select |

### Tareas

- [ ] Crear base `Aprendizajes`.
- [ ] Crear relación con Experimentos.
- [ ] Crear relación con Digital Log.
- [ ] Crear vista por producto.
- [ ] Crear vista por tipo.
- [ ] Crear vista `Potencial QA`.
- [ ] Definir criterios para crear un aprendizaje.

## 1.8. Implementar `/tfe:buscar`

### Objetivo

Recuperar conocimiento sin navegar manualmente Notion.

### Ejemplos

```text
/tfe:buscar pricing

/tfe:buscar experimentos de bundles

/tfe:buscar qué pasó con Khipu

/tfe:buscar incidencias relacionadas con mobile
```

### Tareas

- [ ] Crear command.
- [ ] Crear Skill.
- [ ] Buscar Digital Log.
- [ ] Buscar Experimentos.
- [ ] Buscar Aprendizajes.
- [ ] Responder con fuente/origen.
- [ ] Diferenciar hechos de interpretación.
- [ ] Indicar cuando no existe evidencia suficiente.
- [ ] Probar con consultas reales del equipo.

## 1.9. Retrospectiva semanal

Se mantiene la metodología existente:

```text
✅ Salió bien
❌ Salió mal
🎯 Nos sorprendió
🚀 Vamos a hacer
```

### Tareas

- [ ] Crear base o página de Retrospectivas.
- [ ] Crear plantilla semanal.
- [ ] Crear estados:
  - Borrador
  - Revisada
  - Presentada
- [ ] Agrupar por tema/tarea.
- [ ] No agrupar por persona.
- [ ] Relacionar eventos del Digital Log.
- [ ] Relacionar experimentos relevantes.
- [ ] Relacionar aprendizajes.
- [ ] Mantener formato compatible con la retro mensual existente.

## 1.10. Implementar `/tfe:semana`

Claude debe consultar:

```text
Digital Log
Experimentos
Aprendizajes
Retro anterior
```

### Output

```markdown
# Revisión semanal

## Hechos relevantes
...

## Experimentos
...

## Pendientes
...

## Aprendizajes
...

# Retrospectiva

## ✅ Salió bien
...

## ❌ Salió mal
...

## 🎯 Nos sorprendió
...

## 🚀 Vamos a hacer
...
```

### Flujo

```text
Claude genera borrador
       ↓
Juan revisa
       ↓
Valeria consolida
       ↓
presentación
```

### Tareas

- [ ] Crear command.
- [ ] Crear Skill.
- [ ] Leer solo período correspondiente.
- [ ] Consultar retro previa.
- [ ] Detectar eventos repetidos.
- [ ] Detectar temas recurrentes.
- [ ] Evitar actividades sin relevancia.
- [ ] Crear borrador.
- [ ] Nunca marcar como presentada automáticamente.
- [ ] Validar con dos semanas reales.

## 1.11. Retrospectiva mensual

### Objetivo

Consolidar las retrospectivas semanales sin rehacer el trabajo.

### Tareas

- [ ] Crear plantilla mensual.
- [ ] Leer retros semanales.
- [ ] Detectar recurrencias.
- [ ] Detectar problemas repetidos.
- [ ] Detectar aprendizajes relevantes.
- [ ] Detectar acciones arrastradas.
- [ ] Respetar formato oficial.
- [ ] Crear borrador mensual.
- [ ] Juan revisa.
- [ ] Valeria consolida.

## 1.12. Adopción Fase 1

### Capacitación de 20–30 minutos

Enseñar solo:

```text
/tfe:registrar
/tfe:experimento
/tfe:buscar
/tfe:semana
```

### Tareas

- [ ] Preparar guía de una página.
- [ ] Hacer demo.
- [ ] Registrar 5 eventos con el equipo.
- [ ] Consultar 3 ejemplos.
- [ ] Generar primera retro.
- [ ] Recoger feedback.
- [ ] Corregir fricciones.

## 1.13. Métricas de Fase 1

- [ ] % de eventos relevantes registrados.
- [ ] % de experimentos con resultado.
- [ ] % de experimentos con aprendizaje.
- [ ] Tiempo de preparación de retro.
- [ ] Número de búsquedas útiles realizadas.
- [ ] Registros rechazados por falta de contexto.
- [ ] Aprendizajes reutilizados.

## Gate para avanzar a Fase 2

No avanzar hasta cumplir:

```text
[ ] El equipo usa el Digital Log
[ ] /tfe:registrar funciona
[ ] /tfe:buscar es útil
[ ] Experimentos están trazables
[ ] La retro semanal se genera desde el sistema
[ ] Juan valida el valor del flujo
```

---

# FASE 2 — QA Knowledge

## Objetivo

Convertir experiencia de certificación y errores históricos en conocimiento reutilizable.

No automatizar todavía el navegador.

## 2.1. Mapear cómo certifica hoy el equipo

- [ ] Entrevistar a Juan.
- [ ] Entrevistar a quienes certifican.
- [ ] Registrar flujo actual.
- [ ] Listar errores históricos.
- [ ] Identificar casuísticas frecuentes.
- [ ] Clasificar por:
  - pricing;
  - nacionalidad;
  - moneda;
  - producto;
  - idioma;
  - device;
  - funnel;
  - checkout;
  - pasarela;
  - tracking;
  - AB tests.

### Entregable

`fase-2/qa-knowledge-base-inicial.md`

## 2.2. Crear base Reglas QA

### Campos

| Campo | Tipo |
|---|---|
| Regla | Título |
| Categoría | Select |
| Aplica cuando | Multi-select |
| Producto | Multi-select |
| Funnel | Multi-select |
| Criticidad | Select |
| Casos mínimos | Texto |
| Resultado esperado | Texto |
| Origen | Relation |
| Estado | Select |

### Tareas

- [ ] Crear base.
- [ ] Migrar primeras reglas.
- [ ] Crear categorías.
- [ ] Crear criticidad.
- [ ] Relacionar con Aprendizajes.
- [ ] Relacionar con Digital Log.
- [ ] Crear vista `Propuestas`.
- [ ] Crear vista `Activas`.
- [ ] Crear vista `Críticas`.

## 2.3. Crear base Certificaciones

### Tareas

- [ ] Crear base.
- [ ] Relacionar con ticket/referencia.
- [ ] Relacionar con experimento.
- [ ] Relacionar con reglas QA.
- [ ] Crear estados.
- [ ] Crear evidencia.
- [ ] Crear resultado.

## 2.4. Implementar `/tfe:certificar`

### Objetivo

Generar checklist dinámico.

### Proceso

```text
Ticket / cambio
     ↓
Claude identifica alcance
     ↓
consulta reglas QA
     ↓
consulta errores históricos
     ↓
selecciona checks
     ↓
humano revisa
     ↓
certificación
```

### Tareas

- [ ] Crear command.
- [ ] Crear Skill.
- [ ] Detectar componentes afectados.
- [ ] Detectar dimensiones relevantes.
- [ ] Buscar reglas QA.
- [ ] Buscar errores similares.
- [ ] Generar checklist.
- [ ] Ordenar por criticidad.
- [ ] Crear certificación como borrador.
- [ ] Permitir agregar checks manuales.

## 2.5. Implementar `/tfe:aprender`

### Objetivo

Convertir fallos nuevos en nuevas reglas.

### Flujo

```text
Fallo
 ↓
¿existía regla?
 ↓
NO
 ↓
Claude propone regla
 ↓
Humano revisa
 ↓
Regla activa
```

### Tareas

- [ ] Crear command.
- [ ] Detectar si ya existe regla equivalente.
- [ ] Proponer regla nueva.
- [ ] Mantener origen.
- [ ] Requerir aprobación humana.
- [ ] Evitar duplicados.

## 2.6. Definition of Done QA

Una certificación está lista cuando:

```text
[ ] Alcance revisado
[ ] Checks críticos ejecutados
[ ] Evidencia guardada
[ ] Observaciones registradas
[ ] Fallos relacionados
[ ] Resultado humano
```

## Gate para avanzar a Fase 3

```text
[ ] Existen reglas QA reutilizables
[ ] Existen certificaciones estructuradas
[ ] /tfe:certificar genera valor
[ ] /tfe:aprender captura nuevos casos
[ ] El equipo identifica checks repetitivos
```

---

# FASE 3 — Assisted Certification

## Objetivo

Usar Claude + Chrome DevTools MCP para ayudar a ejecutar certificaciones funcionales reales.

Claude no aprueba.

## 3.1. Preparar entorno

- [ ] Crear perfil Chrome exclusivo para certificación.
- [ ] Configurar Chrome DevTools MCP.
- [ ] Validar conexión con Claude.
- [ ] Validar acceso a CERT.
- [ ] Evitar cuentas personales.
- [ ] Documentar seguridad.

## 3.2. Definir flujo

```text
Ticket
 ↓
Claude propone plan
 ↓
Humano revisa
 ↓
Chrome DevTools MCP
 ↓
Claude ejecuta navegación
 ↓
UI + Console + Network
 ↓
Evidencia
 ↓
Humano decide
```

## 3.3. Crear primeros journeys guiados

- [ ] FDM.
- [ ] Actividad.
- [ ] Paquete.
- [ ] Bundle.
- [ ] P1 → P2.
- [ ] P2 → P3.
- [ ] P3 → P4.
- [ ] Apertura de pasarela cuando sea seguro.

## 3.4. Evidencia automática

Para cada fallo:

```text
URL
caso
pasos
resultado esperado
resultado real
screenshot
console
network
```

### Tareas

- [ ] Crear formato estándar.
- [ ] Guardar evidencia.
- [ ] Relacionar con certificación.
- [ ] Relacionar con Digital Log.
- [ ] Crear incidencia si aplica.

## 3.5. Integrar con `/tfe:certificar`

- [ ] Seleccionar checks automatizables.
- [ ] Ejecutar mediante Chrome.
- [ ] Marcar PASS/FAIL.
- [ ] Dejar checks manuales pendientes.
- [ ] Crear resumen.
- [ ] Requerir aprobación humana.

## Gate para avanzar a Fase 4

```text
[ ] Existen casos repetitivos claros
[ ] Chrome DevTools reduce tiempo real
[ ] Evidencia generada es útil para TI
[ ] El equipo confía en la asistencia
[ ] Se identificaron journeys maduros
```

---

# FASE 4 — Automated Regression

## Objetivo

Automatizar casos maduros y repetitivos con Playwright.

No convertir todo en automatización.

## 4.1. Seleccionar candidatos

Automatizar solo si:

```text
[ ] Se ejecuta frecuentemente
[ ] Tiene resultado determinista
[ ] Tiene valor alto
[ ] Cambia poco
[ ] Fallar genera riesgo
```

## 4.2. Crear proyecto Playwright

```text
tests/
├── smoke/
├── journeys/
├── pricing/
├── components/
└── visual/
```

### Tareas

- [ ] Configurar Playwright.
- [ ] Configurar ambientes.
- [ ] Configurar browser projects.
- [ ] Configurar screenshots/traces.
- [ ] Configurar reports.

## 4.3. Golden Journeys

Crear inicialmente:

- [ ] FDM.
- [ ] Actividades.
- [ ] Paquetes.
- [ ] Bundle Essential.
- [ ] All Inclusive.
- [ ] Llegar a carrito.
- [ ] Apertura de pasarela cuando sea seguro.

## 4.4. Visual Regression

- [ ] Cards.
- [ ] Selectores.
- [ ] CTAs.
- [ ] Modales.
- [ ] Componentes relevantes.
- [ ] Ocultar datos dinámicos.
- [ ] Definir tolerancias.

## 4.5. Matriz de ejecución

Evaluar:

```text
Mobile
Desktop
Chromium
WebKit
Idiomas
Nacionalidad
Moneda
Control
Variación
```

No ejecutar combinatoria completa sin necesidad.

## 4.6. Test Impact Selection

### Objetivo

Ejecutar solo regresión relevante cuando sea posible.

### Tareas

- [ ] Relacionar componentes con tests.
- [ ] Relacionar páginas con journeys.
- [ ] Crear mapa inicial de impacto.
- [ ] Crear fallback a suite mayor si el impacto no es claro.
- [ ] Registrar cobertura.

## 4.7. Smoke post-release

- [ ] Definir smoke seguro.
- [ ] Ejecutar después de release.
- [ ] No generar compras reales.
- [ ] Registrar fallo.
- [ ] Crear alerta cuando corresponda.

## Gate para avanzar a Fase 5

```text
[ ] Suites estables
[ ] Falsos positivos controlados
[ ] Casos críticos cubiertos
[ ] Existe mantenimiento asignado
[ ] Automatización reduce trabajo real
```

---

# FASE 5 — Scale & Integration

## Objetivo

Escalar solamente las integraciones que demostraron utilidad.

## 5.1. SharePoint / disponibilidad

- [ ] Evaluar conexión.
- [ ] Recuperar disponibilidad histórica.
- [ ] Permitir consulta contextual.
- [ ] Evitar duplicar Power BI.

## 5.2. Excel TI

- [ ] Evaluar lectura automática.
- [ ] Relacionar tickets con Notion.
- [ ] Evitar doble mantenimiento.
- [ ] Definir sincronización solo si aporta valor.

## 5.3. HubSpot

- [ ] Evaluar eventos relevantes.
- [ ] Evitar información personal innecesaria.
- [ ] Conectar solo casos con ownership claro.

## 5.4. Knowledge Search ampliado

Permitir búsquedas como:

```text
¿Qué problemas tuvimos antes con pricing?

¿Qué experimentos tocaron bundles?

¿Qué errores de mobile se repitieron?

¿Qué reglas QA nacieron de incidencias?

¿Qué aprendimos de cards?
```

## 5.5. Automatizaciones recurrentes

Solo después de validar:

- [ ] resumen semanal;
- [ ] recordatorio de experimentos sin aprendizaje;
- [ ] certificaciones abiertas;
- [ ] reglas QA propuestas;
- [ ] retros mensuales;
- [ ] seguimiento de acciones.

---

# 7. Roles

| Rol | Responsabilidad dentro del sistema |
|---|---|
| Juan | revisión, dirección, aprobación |
| Valeria | consolidación de retro / información |
| Akash | contexto UX y entregables relacionados |
| Esteban | construcción y evolución del toolkit |
| Equipo | registrar eventos relevantes y usar herramientas |
| Claude | estructurar, recuperar, relacionar, proponer |
| Notion | memoria compartida |

---

# 8. Comandos por fase

## Fase 1

```text
/tfe:registrar
/tfe:experimento
/tfe:buscar
/tfe:semana
```

## Fase 2

```text
/tfe:certificar
/tfe:aprender
```

## Fase 3

```text
/tfe:certificar-asistido
```

## Fase 4

La ejecución debe ser principalmente código/CI, no comandos conversacionales.

---

# 9. Estructura final del repositorio

```text
tfe-ai-toolkit/
│
├── README.md
│
├── docs/
│   ├── proyecto.md
│   ├── seguridad.md
│   ├── governance.md
│   └── roadmap.md
│
├── commands/
│   ├── registrar.md
│   ├── experimento.md
│   ├── buscar.md
│   ├── semana.md
│   ├── certificar.md
│   └── aprender.md
│
├── skills/
│   ├── registro/
│   ├── experimentacion/
│   ├── knowledge-search/
│   ├── revision-semanal/
│   ├── certificacion/
│   └── qa-learning/
│
├── references/
│   ├── digital-log-policy.md
│   ├── notion-schema.md
│   ├── experimentos.md
│   ├── retrospectiva.md
│   ├── qa-rules.md
│   ├── funnel-tfe.md
│   └── productos-tfe.md
│
├── automation/
│   └── playwright/
│
└── changelog/
```

---

# 10. Backlog futuro

No implementar todavía:

- [ ] análisis automático de revenue;
- [ ] reemplazo de Power BI;
- [ ] reemplazo de Excel TI;
- [ ] nueva metodología de tickets;
- [ ] priorización automática;
- [ ] decisiones automáticas;
- [ ] agentes autónomos en producción;
- [ ] full regression desde el día 1;
- [ ] crawler completo de toda la web;
- [ ] knowledge graph complejo;
- [ ] Neo4j;
- [ ] sistema propio de project management.

---

# 11. Métrica global del proyecto

El proyecto funciona si mejora alguno de estos puntos:

```text
menos tiempo operativo
menos errores repetidos
mejor cobertura de certificación
menos pérdida de contexto
mejor trazabilidad de experimentos
retros más rápidas
más aprendizaje reusable
más consistencia
más capacidad del equipo
```

La IA no es el resultado.

El resultado es un equipo que puede ejecutar mejor.

---

# 12. Orden de ejecución recomendado

```text
FASE 0
Preparación
   ↓
FASE 1
Digital Log
   ↓
/tfe:registrar
   ↓
Experimentos
   ↓
/tfe:experimento
   ↓
Aprendizajes
   ↓
/tfe:buscar
   ↓
Retro
   ↓
/tfe:semana
   ↓
VALIDAR USO REAL
   ↓
FASE 2
QA Knowledge
   ↓
/tfe:certificar
   ↓
/tfe:aprender
   ↓
VALIDAR USO REAL
   ↓
FASE 3
Chrome DevTools MCP
   ↓
VALIDAR USO REAL
   ↓
FASE 4
Playwright
   ↓
FASE 5
Integraciones
```

---

# 13. Primera tarea concreta

Antes de construir cualquier base nueva:

```text
1. Conectar Notion MCP.
2. Inspeccionar páginas existentes.
3. Encontrar bitácora actual de experimentos.
4. Documentar schema actual.
5. Identificar qué se puede reutilizar.
6. Proponer cambios mínimos.
7. No modificar todavía.
```

Prompt recomendado:

```text
Quiero implementar la Fase 1 del proyecto TFE AI Toolkit.

Objetivo:
crear una memoria operativa del equipo usando Notion + Claude,
sin cambiar el ownership ni los procesos actuales.

Antes de modificar cualquier contenido:

1. Inspecciona las páginas y bases disponibles de Canal Digital TFE.
2. Identifica la bitácora actual de experimentos.
3. Identifica páginas de retrospectivas.
4. Identifica estructuras que podamos reutilizar.
5. No elimines, renombres ni migres información.
6. Documenta el estado actual.
7. Compara contra este proyecto.
8. Propón únicamente los cambios mínimos necesarios para Fase 1.

Entrega:

- Estado actual
- Bases existentes
- Gaps
- Schema propuesto
- Relaciones
- Riesgos
- Plan de implementación

No ejecutes cambios hasta que el plan sea aprobado.
```

---

# 14. Definición de éxito final

El proyecto habrá madurado cuando el equipo pueda decir:

```text
"Pasó algo importante"
→ se registra en segundos.

"¿Esto ya pasó antes?"
→ Claude lo encuentra.

"¿Qué ocurrió esta semana?"
→ Claude prepara el contexto.

"¿Qué aprendimos?"
→ existe y puede reutilizarse.

"¿Qué debemos probar?"
→ Claude usa historial y reglas.

"¿Puedes ayudarme a certificarlo?"
→ Claude navega CERT y reúne evidencia.

"¿Tenemos que repetir esta prueba?"
→ Playwright ya la ejecuta.
```

Ese es el estado objetivo.
