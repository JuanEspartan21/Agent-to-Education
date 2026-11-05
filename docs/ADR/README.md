# Architecture Decision Records (ADR)

Registrar aquí decisiones técnicas o de producto que tengan impacto duradero. Formato recomendado: contexto, decisión, alternativas, consecuencias, fecha y estado.

## ADR-001 — Aplicación personal local y monolito modular
**Estado:** aceptada.  
**Decisión:** construir una aplicación de escritorio local con módulos separados; no una plataforma institucional multiusuario en el MVP.  
**Motivo:** se ajusta al caso de un docente y reduce complejidad operativa.

## ADR-002 — Dos roles
**Estado:** aceptada.  
**Decisión:** ADMIN y DOCENTE. El administrador técnico no obtiene acceso automático a datos pedagógicos individuales.

## ADR-003 — Dos bibliotecas y contexto pedagógico separado
**Estado:** aceptada.  
**Decisión:** biblioteca general JARVIS + biblioteca institucional del cliente. Caracterizaciones grupales e individuales se almacenan como contexto restringido, no como conocimiento público.

## ADR-004 — SQLite FTS5 primero
**Estado:** aceptada para MVP.  
**Decisión:** iniciar con SQLite y búsqueda textual FTS5. Evaluar embeddings/vector search solo si las pruebas muestran insuficiencia.

## ADR-005 — Local por defecto para datos restringidos
**Estado:** aceptada como política de producto.  
**Decisión:** caracterización y progreso individual no se envían a servicios cloud en el MVP; análisis incompleto bloquea transmisión externa.

## ADR pendientes
- ADR sobre sistema operativo soportado.
- ADR sobre cifrado de base de datos y backups.
- ADR sobre modelo local y/o proveedor cloud para datos públicos.
- ADR sobre empaquetado y actualizaciones.
