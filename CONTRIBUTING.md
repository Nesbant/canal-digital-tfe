# Convenciones de este repo (Fase 0.3)

## Ramas

Rama única `main`. Sin branches por feature por ahora — es un repo chico, mantenido por una o dos personas. Antes de un cambio riesgoso (tocar Notion, reestructurar), crear un **tag** sobre el commit actual como snapshot reversible:

```bash
git tag -a <nombre-descriptivo> -m "snapshot: por qué"
```

Para volver atrás: `git checkout <tag>`. Si el equipo crece o empiezan a trabajar varias personas en paralelo, reevaluar y pasar a feature branches + PRs.

## Commits

Conventional commits (`feat:`, `docs:`, `fix:`, `chore:`), sin línea de atribución de IA. Un commit por unidad de trabajo coherente (ej. "crear Digital Log + docs" es un commit, "agregar Aprendizajes + Retrospectivas" es otro).

## Tags existentes

| Tag | Qué marca |
|---|---|
| `fase-0-1-scaffold` | Estructura inicial del repo, antes de tocar Notion |
| `fase-1-notion-executed` | Digital Log creada + Experimentos normalizado |
| `fase-1-bases-completas` | Las 4 bases de Fase 1 (Digital Log, Experimentos, Aprendizajes, Retrospectivas) con schema y vistas, sin datos reales todavía |
