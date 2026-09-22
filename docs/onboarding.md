# Onboarding — instrucciones para el equipo (Fase 1.12)

> Para alguien que ya tiene Claude Code instalado, pero nunca usó este plugin ni conectó Notion por MCP. 5 minutos, una sola vez.

## 1. Conectar tu propia cuenta de Notion (una vez por persona/máquina)

En la terminal, **fuera** de Claude Code:

```bash
claude mcp add --transport http notion https://mcp.notion.com/mcp
```

Después, **dentro** de una sesión de Claude Code:

```
/mcp
```

Elegí `notion` → **Authenticate** → se abre el navegador → aprobá con tu propia cuenta de Notion (la que ya tiene acceso al Teamspace de Canal Digital).

⚠️ Esto es individual: tu acceso en Notion (a qué páginas podés entrar) es el mismo que va a tener Claude cuando actúe por vos. Si vos no podés ver algo en Notion, Claude tampoco va a poder.

## 2. Instalar el plugin del equipo

Dentro de Claude Code:

```
/plugin marketplace add Nesbant/canal-digital-tfe
/plugin install tfe@canal-digital
```

Si los comandos no aparecen enseguida, correr `/reload-plugins`.

## 3. Comandos disponibles

| Comando | Para qué |
|---|---|
| `/tfe:registrar <nota>` | Registrar algo que pasó (incidencia, release, decisión, hallazgo...) en el Digital Log |
| `/tfe:experimento <acción>` | Crear, consultar, actualizar, cerrar o buscar un experimento |
| `/tfe:buscar <tema>` | Buscar conocimiento en Digital Log, Experimentos y Aprendizajes |
| `/tfe:semana <período>` | Generar un borrador de retrospectiva |

## 4. Ejemplo real de uso

```
/tfe:registrar

Hoy se detectó que la variación del AB de checkout mostraba
tarifa extranjera en mobile en una parte del flujo. TI ya
recibió el caso como SD-XXXXX.
```

Claude va a preguntar si algo queda ambiguo (por ejemplo, si no dijiste si es Tren o TFE) — **eso es a propósito**, no es un error. No va a inventar un dato que no le diste.

## 5. Reglas que hay que respetar

- Nunca cargar datos personales de pasajeros (nombre, documento, contacto) en ninguna de las 4 bases.
- Un experimento no se cierra sin Resultado + Decisión + Aprendizaje — si te falta alguno, el comando te lo va a pedir antes de cerrar.
- Si Claude te pregunta algo antes de crear un registro, es porque falta contexto — contestale, no lo evadas, o el registro queda incompleto.

## Si algo no funciona

- `/mcp` de nuevo para revisar el estado de la conexión a Notion.
- `/plugin` para ver qué plugins están instalados.
- Avisarle a Esteban (mantiene este toolkit) si un comando da un error que no entendés.
