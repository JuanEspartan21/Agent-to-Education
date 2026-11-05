# Agent-to-Education (JARVIS)

Agente personal de asistencia pedagógica, inicialmente especializado en Educación Física para el contexto educativo colombiano.

## Propósito
Apoyar a un docente en la consulta de referentes educativos, caracterización pedagógica grupal e individual, planeación, diseño de experiencias motrices, elaboración de materiales, evaluación y seguimiento del aprendizaje. JARVIS propone; el docente revisa y decide.

## Estado
**Fase:** preparación y Sprint 0 (por iniciar).  
**Plan base:** 8 sprints de 2 semanas (16 semanas), sujeto a validación de alcance y disponibilidad.  
**Capacidad estimada:** 12–15 horas por semana.  
**Cliente de referencia:** docente con necesidades iniciales en Educación Física, Colombia/Bogotá.

## Decisiones de producto
- Aplicación personal/local, no plataforma multiinstitucional ni multiusuario en el MVP.
- Roles: `ADMIN` (mantenimiento técnico) y `DOCENTE` (uso pedagógico).
- Dos capas de conocimiento: biblioteca general y biblioteca institucional del cliente.
- Caracterización y seguimiento grupal e individual, con minimización de datos y permisos.
- Procesamiento local por defecto para información educativa restringida.
- Aprobación humana obligatoria para planeaciones, adaptaciones y evaluaciones.
- No diagnosticar ni etiquetar estudiantes.

## Documentación del proyecto
- [Alcance del producto](docs/PRODUCT_SCOPE.md)
- [Arquitectura](docs/ARCHITECTURE.md)
- [Modelo de datos](docs/DATA_MODEL.md)
- [Seguridad y privacidad](docs/SECURITY_PRIVACY.md)
- [Backlog del producto](docs/SCRUM/PRODUCT_BACKLOG.md)
- [Plan de sprints](docs/SCRUM/SPRINTS.md)
- [Ceremonias y flujo Scrum](docs/SCRUM/SCRUM_WORKFLOW.md)
- [Definition of Ready / Done](docs/SCRUM/DEFINITION_OF_DONE.md)
- [Registro de decisiones](docs/ADR/README.md)

## Inicio para desarrollo
1. Leer el alcance, arquitectura y seguridad.
2. Ejecutar Sprint 0: validar necesidades, hardware, sistema operativo, documentos y criterios de aceptación.
3. Crear entorno Python y esqueleto de aplicación solo después de cerrar los criterios de Sprint 0.
4. Trabajar mediante issues pequeños, ramas y pull requests.
5. No incorporar documentos reales con datos personales al repositorio.

## Restricciones conocidas del equipo objetivo
Lenovo Z480: Intel Core i5-3210M, 8 GB RAM, HDD 1 TB (aprox. 500 GB libres), Windows 10 Pro 22H2, build 19045.6466. El HDD condiciona la indexación y el arranque. Antes de procesar información real debe verificarse el estado de soporte/seguridad del sistema operativo y definirse una estrategia de actualización o migración. No se presupone que un LLM local grande pueda ejecutarse adecuadamente.

## Principio de seguridad
El repositorio contiene código y documentación técnica, nunca caracterizaciones, PEI/SIEE privados, datos de estudiantes, credenciales, claves API ni documentos del cliente.
