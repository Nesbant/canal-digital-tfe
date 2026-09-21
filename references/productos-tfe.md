# Productos TFE — lista de referencia (borrador, no confirmado con el equipo)

Usada en el campo `Producto` (multi-select) de la base Aprendizajes:

```text
FDM
Actividad
Paquete
Bundle
All Inclusive
Tours
Otro
```

**Origen**: esta lista es una primera pasada de Claude basada en los nombres de producto que aparecen en los experimentos ya cargados en Notion (menciones a AIC, Bundle, tours, etc.), **no** una lista oficial confirmada por el equipo.

**Antes de confiar en esto para reportes o segmentación real**: validar con el equipo si esta es la taxonomía correcta de productos TFE, o si falta/sobra algo. Si cambia, actualizar acá primero y luego en Notion (`ALTER COLUMN "Producto" SET MULTI_SELECT(...)` sobre `collection://b5da647a-7d02-4116-9f99-4534d982b0f5`).
