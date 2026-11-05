# Roadmap Scrum — 8 sprints / 16 semanas

## Supuestos de planificación
- Duración: 2 semanas por sprint.
- Capacidad inicial: 12–15 horas semanales (24–30 horas por sprint).
- Equipo: desarrollador principal individual. El cliente actúa como Product Owner/representante de necesidades y valida incrementos.
- Las estimaciones se revisan al finalizar Sprint 0; no son compromisos rígidos.
- Reservar aproximadamente 15–20% de capacidad para defectos, investigación y contingencias.
- Las fechas calendario se asignarán al confirmar inicio real.

## Sprint 0 — Descubrimiento y preparación (semanas 1–2)
**Objetivo:** reducir incertidumbre y preparar una base ejecutable.
- Confirmar flujos del docente y priorizar escenarios.
- Revisar los seis documentos base: origen, formato, integridad, fecha, versión y vigencia.
- Solicitar PEI, SIEE, planes de área y formatos institucionales.
- Verificar Windows, soporte/ESU, RAM, disco y espacio; decidir actualización/migración antes de datos reales.
- Definir política de clasificación y carpeta autorizada.
- Crear repositorio, convenciones, backlog y criterios de aceptación.

**Entregables:** alcance validado, inventario de fuentes, matriz de riesgos, entorno evaluado, backlog priorizado y Definition of Done.

**Salida:** no iniciar ingesta de datos reales si las puertas de seguridad siguen abiertas.

## Sprint 1 — Fundamentos de aplicación (semanas 3–4)
**Objetivo:** esqueleto mantenible y seguro.
- Estructura Python modular, entorno reproducible y dependencias fijadas.
- PySide6 con navegación básica.
- Configuración local y carpeta autorizada.
- SQLite, migraciones iniciales y roles ADMIN/DOCENTE.
- Logs técnicos minimizados y manejo de errores.
- CI básico y pytest.

**Demo:** aplicación abre, configura carpeta, crea/valida base y restringe acceso básico.

## Sprint 2 — Ingesta y biblioteca documental (semanas 5–6)
**Objetivo:** importar y consultar fuentes.
- Lectura PDF/DOCX.
- Registro de metadatos, hash y versiones.
- Extracción con localizadores de página/sección.
- SQLite FTS5.
- Separación biblioteca general/institucional.
- Detección inicial de archivos problemáticos.

**Demo:** importar un corpus sintético/de prueba y recuperar fragmentos con trazabilidad.

## Sprint 3 — Caracterización pedagógica (semanas 7–8)
**Objetivo:** contexto grupal e individual controlado.
- CRUD y versionado de grupos.
- Caracterización grupal.
- Ficha individual mínima y permisos restringidos.
- Evidencias y distinción observación/sugerencia/decisión.
- Pruebas de aislamiento y minimización.

**Demo:** crear perfil grupal y un perfil individual sintético; recuperar solo el contexto permitido.

## Sprint 4 — Planeación y experiencias motrices (semanas 9–10)
**Objetivo:** primer flujo pedagógico de extremo a extremo.
- Objetivos y secuencias.
- Juegos, circuitos y actividades.
- Variantes por complejidad y necesidades.
- Recuperación de fuentes y contexto.
- Generación DOCX.
- Revisión/aprobación del docente.

**Demo:** crear una planeación de Educación Física con variantes, evaluación y referencias.

## Sprint 5 — Evaluación y seguimiento (semanas 11–12)
**Objetivo:** registrar evidencias y progreso.
- Instrumentos, rúbricas y listas de cotejo.
- Seguimiento grupal.
- Seguimiento individual con permisos.
- Comparación contra objetivos y línea de base.
- Informes con protección contra revelación de grupos pequeños.

**Demo:** registrar una sesión de evaluación y producir resumen grupal e individual autorizado.

## Sprint 6 — Calidad, seguridad y rendimiento (semanas 13–14)
**Objetivo:** endurecer el producto para piloto controlado.
- Pruebas de autorización, rutas, archivos malformados y prompt injection.
- Prueba de bloqueo cloud para información restringida.
- Backup, restauración y borrado.
- Benchmark CPU/RAM/latencia en Lenovo objetivo.
- Resolver defectos prioritarios y revisar accesibilidad/usabilidad.

**Demo:** informe de pruebas y decisión de aptitud para piloto.

## Sprint 7 — Piloto, empaquetado y entrega (semanas 15–16)
**Objetivo:** entregar una versión instalable y documentada.
- Instalador y configuración inicial.
- Carga controlada de fuentes verificadas.
- Prueba de aceptación con docente usando datos ficticios o autorizados.
- Manual de usuario y guía de administración.
- Registro de limitaciones conocidas y plan posterior.
- Retrospectiva y backlog de siguiente versión.

**Demo:** recorrido completo desde consulta hasta material pedagógico aprobado.

## Criterios para replanificar
- Si la capacidad real es menor de 12 h/semana, extender a 24–30 semanas.
- Si el hardware no soporta inferencia local, priorizar búsqueda, plantillas y generación determinista; no forzar un LLM.
- Si el sistema operativo no está soportado, mantener el piloto sin datos personales hasta resolverlo.
- Si PEI/SIEE no llegan, avanzar con fuentes públicas y dejar explícitas las limitaciones institucionales.
