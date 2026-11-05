# Alcance del producto

## Visión
JARVIS es un asistente personal de apoyo pedagógico para que un docente pueda consultar referentes educativos y elaborar, adaptar, evaluar y hacer seguimiento a experiencias de aprendizaje. El primer dominio de especialización es Educación Física en Colombia, con contexto territorial de Bogotá.

## Usuarios y roles
- **ADMIN:** mantenimiento técnico, configuración, versiones, actualizaciones de la biblioteca general, diagnóstico y copias de seguridad. El rol técnico no concede acceso automático al contenido pedagógico individual.
- **DOCENTE:** usuario principal. Gestiona grupos, caracterizaciones, planeaciones, actividades, evaluaciones, seguimiento y documentos institucionales autorizados.

El MVP se diseña para una instalación personal y un docente principal. No incluye gestión de múltiples instituciones o docentes.

## Capacidades funcionales objetivo
1. Biblioteca de fuentes con metadatos, versiones, vigencia y trazabilidad.
2. Importación y consulta de PDF y DOCX desde una carpeta autorizada.
3. Caracterización pedagógica grupal e individual: necesidades, capacidades observadas, ritmos, barreras y apoyos pertinentes.
4. Planeación de clases, unidades y secuencias.
5. Diseño de juegos, circuitos, retos y actividades motrices con variantes.
6. Generación de talleres, guías, rúbricas, listas de cotejo y evaluaciones.
7. Seguimiento grupal e individual basado en objetivos y evidencias.
8. Exportación DOCX con fuentes y advertencias de revisión.
9. Historial y versionado de productos pedagógicos.

## Fuera del MVP
- Plataforma institucional multiusuario/multi-tenant.
- Integraciones con LMS, correo, sistemas de notas o bases de datos escolares.
- Diagnóstico médico, psicológico o de discapacidad.
- Calificación autónoma o decisiones automatizadas sobre estudiantes.
- Automatización general del sistema operativo, voz permanente o wake word.
- Entrenamiento de modelos con documentos o datos del cliente.
- Envío automático de información restringida a servicios cloud.

## Principios pedagógicos
- Educación integral y participación significativa.
- Diferenciación de actividades sin estigmatizar ni fijar etiquetas.
- Progreso individual frente a objetivos y evidencias, no ranking entre estudiantes.
- Las adaptaciones son propuestas revisables por el docente.
- Distinguir observación del docente, sugerencia de IA y decisión aprobada.
- No inferir diagnósticos ni inventar capacidades o limitaciones.

## Fuentes iniciales del cliente
Inventario recibido:
1. Ley 115 de 1994.
2. Ley 181 de 1995.
3. Ley 934 de 2004.
4. Lineamientos Curriculares de Educación Física (2000).
5. Orientaciones Pedagógicas del MEN, Documento 15 (2010).
6. Orientaciones Curriculares del MEN (2022).
7. PEI y SIEE vigentes (pendientes de entrega).
8. Orientaciones de Educación Física de la Secretaría de Educación de Bogotá.

Los archivos originales de los seis primeros documentos están disponibles para el equipo, pero deben incorporarse solo después de verificar procedencia, versión, vigencia y metadatos. PEI y SIEE quedan como dependencias del cliente. No incluir copias privadas en Git.

## Criterios de éxito del MVP
- Importar PDF/DOCX autorizados y mostrar errores de extracción.
- Recuperar fragmentos con documento y ubicación trazables.
- Distinguir fuente normativa, referente curricular y documento institucional.
- Generar una planeación de Educación Física revisable, con fuentes y objetivos explícitos.
- Proponer variantes para necesidades grupales e individuales sin revelar datos innecesarios.
- Registrar evaluación y progreso con evidencia y aprobación docente.
- Mantener datos restringidos localmente por defecto.
- Ejecutarse de forma estable en el hardware objetivo, con límites de memoria y procesamiento.
