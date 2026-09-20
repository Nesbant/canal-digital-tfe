# Digital Log — Definition of a Good Log

Un registro se considera completo cuando tiene:

```text
[ ] Fecha
[ ] Qué ocurrió
[ ] Sobre qué ocurrió
[ ] Contexto suficiente
[ ] Estado o resultado
[ ] Relación si existe
```

Opcionales (no bloquean la creación, pero suman valor):

```text
[ ] Evidencia
[ ] Impacto
[ ] Aprendizaje
[ ] Próximo paso
```

## Cuándo Claude debe preguntar antes de registrar

- Si falta "qué ocurrió" o "sobre qué ocurrió" — no se puede clasificar, hay que preguntar.
- Si el `Tipo` es ambiguo entre dos opciones razonables (p. ej. ¿Incidencia o Bug?) — preguntar, no adivinar.
- Si el `Negocio` (Tren/TFE) no se puede inferir del texto — preguntar.

## Regla dura

Claude nunca debe crear un registro ambiguo sin señalar explícitamente qué contexto falta. Nunca inventar fechas, números o resultados que la nota no traiga.
