# Reglas de seguridad (Fase 0.2)

> Entregable equivalente a `01-reglas-seguridad.md` del roadmap.

## Confirmado / en uso

- Conexión con Notion MCP: activa y funcionando (usada durante todo este proyecto).
- Acceso de lectura/escritura validado empíricamente: el equipo/integración puede leer y escribir en "Go-To-Market Canal Digital TFE" y sus bases hijas (Bitacora de Experimentos, Digital Log, Aprendizajes, Retrospectivas). **No** tiene acceso a "🐞 Certificaciones Ecommerce" (404) — pedir que se comparta si hace falta para Fase 2.
- Páginas/bases donde Claude puede escribir: únicamente las creadas para este toolkit (Digital Log, Experimentos normalizado, Aprendizajes, Retrospectivas) más lo que se autorice explícitamente a futuro.
- Excluido explícitamente: "Dashboard CRO TFE" (no leer ni escribir), "Bitácora Ecommerce" (org-wide) y "Bitácora Retail" (sin autorización nueva).

## Reglas duras (por defecto, mientras no se defina lo contrario)

- Nunca guardar credenciales en Notion ni en el repo.
- Nunca registrar datos personales de pasajeros (nombres, documentos, contacto) en Digital Log, Experimentos, Aprendizajes o Retrospectivas — estas bases son para eventos y conocimiento operativo, no para PII.
- Ningún cambio destructivo (borrar propiedades, borrar filas, trashear data sources) sin pedir confirmación explícita en el momento — todo lo ejecutado hasta ahora fue aditivo.

## Pendiente de definir (Fase 0.2 — no resuelto por Claude)

- [ ] Confirmar acceso del equipo (personas, no solo la integración) a Claude.
- [ ] Validar permisos de lectura/escritura del Teamspace a nivel de personas/roles.
- [ ] Lista concreta y exhaustiva de qué datos nunca deben registrarse (más allá de la regla general de arriba).
