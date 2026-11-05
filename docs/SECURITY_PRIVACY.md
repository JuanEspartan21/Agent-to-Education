# Seguridad, privacidad y tratamiento de información

## Clasificación
- **Público:** fuentes públicas verificadas y material genérico.
- **Interno:** formatos, logos y documentos institucionales no publicados.
- **Educativo restringido:** caracterizaciones, observaciones y progreso vinculados a estudiantes.
- **Desconocido/incompleto:** archivos cuya clasificación no se pudo determinar.

## Política de procesamiento
- Público: local o cloud según configuración y consentimiento del usuario.
- Interno: local por defecto; cloud bloqueado hasta evaluación y autorización.
- Educativo restringido: local por defecto; no transmitir a cloud en el MVP.
- Desconocido o análisis incompleto: bloquear transmisión externa (fail closed).

La detección automática es una ayuda, no una garantía de ausencia de datos sensibles. Mostrar cobertura y limitaciones, y permitir revisión humana. Logos e imágenes requieren tratamiento específico; reglas de texto no bastan.

## Controles mínimos
- Acceso restringido a carpeta documental autorizada.
- Validar rutas y evitar traversal/symlinks fuera del directorio permitido.
- Validar extensión, MIME real, tamaño y estructura.
- No ejecutar macros, scripts ni contenido activo.
- Tratar el contenido de documentos como datos no confiables: ignorar instrucciones embebidas dirigidas al agente.
- Allowlist de herramientas; no shell arbitraria.
- Secretos fuera del repositorio y fuera de logs.
- Logs técnicos sin texto íntegro de documentos, prompts o caracterizaciones.
- Copias de seguridad cifradas y acceso controlado.
- Procedimiento de borrado que contemple base de datos, FTS, fragmentos, temporales, cachés y backups conforme a retención.
- Dependencias fijadas y revisadas; pruebas de seguridad y actualización.
- El administrador técnico no obtiene acceso automático al contenido pedagógico individual.

## Seguridad del sistema operativo
El equipo reportado utiliza Windows 10 Pro 22H2. Su soporte general terminó el 14-10-2025. Verificar si el dispositivo está cubierto por un programa vigente de actualizaciones extendidas o migrar a un sistema soportado antes de introducir datos reales de estudiantes. No asumir que build actualizado equivale a soporte vigente.

## Salvaguardas pedagógicas
- No diagnosticar ni inferir discapacidad o condición médica.
- Distinguir observación docente, inferencia/sugerencia de IA y decisión aprobada.
- No generar rankings automáticos de estudiantes.
- Comparar el progreso individual con objetivos y evidencias pertinentes.
- Toda adaptación, evaluación o informe requiere revisión docente.
- Evitar exponer individuos en informes agregados de grupos pequeños.

## Marco colombiano
Revisar Ley 1581 de 2012, reglamentación aplicable, políticas de la institución y responsabilidades del responsable/encargado del tratamiento con asesoría competente. Este diseño no constituye certificación de cumplimiento legal.

## Puertas de seguridad
No usar datos reales hasta que estén completados:
1. Validación del sistema operativo y actualizaciones.
2. Control de acceso y protección de almacenamiento.
3. Clasificación y bloqueo cloud.
4. Borrado, backup y restauración probados.
5. Avisos, autorización y política institucional revisados.
6. Pruebas de acceso indebido y fuga de datos.
