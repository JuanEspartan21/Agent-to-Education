# Arquitectura inicial

## Estilo
Aplicación de escritorio local, monolito modular. Evitar microservicios y servicios residentes en segundo plano en el MVP.

## Stack propuesto
- Python 3.x: lógica de aplicación.
- PySide6: interfaz de escritorio.
- SQLite: persistencia.
- SQLite FTS5: búsqueda textual inicial.
- PyMuPDF: extracción PDF.
- python-docx: lectura y generación DOCX.
- pytest: pruebas.
- Ollama/modelo local: experimento opcional, condicionado a benchmark.
- Adaptador cloud: interfaz independiente, deshabilitada para información restringida.

Las versiones concretas se fijarán en Sprint 1 tras comprobar compatibilidad con Windows y el equipo objetivo.

## Capas lógicas
1. **Interfaz:** panel, biblioteca, grupos, caracterización, generación e historial.
2. **Aplicación/casos de uso:** importar fuente, buscar, crear planeación, registrar evidencia.
3. **Dominio pedagógico:** objetivos, perfiles, actividades, adaptaciones y evaluación.
4. **Conocimiento:** registro de fuentes, extracción, fragmentación, indexación y recuperación.
5. **Persistencia:** repositorios SQLite y almacenamiento de archivos autorizados.
6. **Seguridad:** autorización, clasificación, política local/cloud, auditoría y borrado.

## Dos bibliotecas de conocimiento
- **General JARVIS:** normativa y referentes públicos colombianos e internacionales, con metadatos y mantenimiento de versiones.
- **Institucional del cliente:** PEI, SIEE, planes de área, formatos y pautas internas. Separada de la biblioteca general.

La caracterización del grupo y del estudiante no es una biblioteca documental general: es contexto pedagógico restringido, recuperado solo para el grupo y propósito autorizado.

## Flujo de consulta/generación
1. El docente formula la solicitud y selecciona grupo/curso.
2. Se valida identidad, permisos y finalidad.
3. Se clasifica la información que se pretende utilizar.
4. Se recuperan fuentes aplicables y sus fragmentos.
5. Se recupera la caracterización mínima necesaria (grupal y, si procede, individual).
6. El motor pedagógico propone objetivos, actividades, variantes y evaluación.
7. Se valida consistencia de fuentes y se señalan incertidumbres.
8. Se genera borrador DOCX.
9. El docente revisa, modifica y aprueba.
10. Se registra trazabilidad sin copiar texto sensible en logs.

## Hardware objetivo
Lenovo Z480, i5-3210M, 8 GB RAM, HDD 1 TB con unos 500 GB libres, Windows 10 Pro 22H2 build 19045.6466.

Implicaciones:
- Procesamiento por lotes pequeños y streaming cuando sea posible.
- SQLite FTS5 antes de introducir una base vectorial.
- No cargar corpus completo en memoria.
- Indexación incremental y programable.
- No asumir inferencia local fluida; comparar modelo pequeño cuantizado contra generación basada en plantillas y servicios remotos solo para datos públicos/no restringidos.
- Medir RAM, CPU, latencia y estabilidad con corpus de prueba sintético.
- HDD puede penalizar indexación y acceso aleatorio; documentar benchmark.

## Restricción del sistema operativo
Windows 10 22H2 está fuera del soporte general desde octubre de 2025. Antes de procesar información real, comprobar elegibilidad y vigencia de actualizaciones de seguridad extendidas o migrar a un sistema operativo soportado. Esta condición es una puerta de seguridad, no una tarea cosmética.

## Estructura de código prevista
```
src/jarvis/
  app/
  domain/
    academic/
    characterization/
    pedagogy/
    assessment/
  knowledge/
    ingestion/
    retrieval/
    sources/
  infrastructure/
    database/
    documents/
    security/
    llm/
  ui/
tests/
docs/
```

## Decisiones pendientes
- Versión Python y estrategia de empaquetado.
- Instalador y mecanismo de actualización.
- Formato de almacenamiento cifrado y gestión de claves.
- Si se incorpora OCR local.
- Si el hardware permite un modelo local pequeño tras benchmark.
