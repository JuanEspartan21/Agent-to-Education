# Modelo de datos inicial

## Principios
- SQLite para el MVP.
- Identificadores internos; evitar identificación directa en índices de búsqueda.
- Separar observaciones, sugerencias de IA y decisiones aprobadas.
- Versionar caracterizaciones y fuentes.
- No almacenar datos clínicos salvo necesidad legítima, autorización y evaluación específica; preferir registrar el apoyo pedagógico funcional requerido.
- Cada registro sensible debe tener finalidad, responsable, fecha, estado y política de retención.

## Entidades principales

### Acceso
- `users(id, username, password_hash, role, is_active, created_at, last_login)`
- Roles permitidos: `ADMIN`, `DOCENTE`.
- `user_settings(user_id, setting_key, setting_value)`

### Organización académica
- `academic_years(id, label, starts_on, ends_on)`
- `groups(id, name, grade, academic_year_id, notes)`
- `students(id, internal_code, display_name, is_active)`
- `group_memberships(id, group_id, student_id, starts_on, ends_on)`

### Caracterización
- `group_profiles(id, group_id, version, status, valid_from, reviewed_at, created_by)`
- `group_needs(id, profile_id, category, description, strategy, evidence_ref)`
- `student_profiles(id, student_id, version, status, valid_from, reviewed_at, created_by)`
- `student_needs(id, profile_id, category, functional_support, strategy, evidence_ref)`
- `profile_evidence(id, scope, profile_id, observation, observed_at, author_id, evidence_type)`

### Biblioteca documental
- `sources(id, title, issuer, source_type, jurisdiction, subject, official_url, status)`
- `source_versions(id, source_id, version_label, published_at, effective_from, effective_until, verified_at, file_hash, storage_path)`
- `document_chunks(id, source_version_id, locator, content, content_hash)`
- `source_relations(id, source_id, related_source_id, relation_type)`

### Planeación y actividades
- `learning_objectives(id, area, grade_band, code, description, source_id)`
- `lesson_plans(id, group_id, title, period, status, created_at, approved_at, created_by)`
- `lesson_activities(id, lesson_plan_id, title, instructions, duration_minutes, materials)`
- `activity_variants(id, activity_id, variant_type, adaptation, intended_support)`
- `lesson_sources(id, lesson_plan_id, source_version_id, chunk_id)`
- `plan_profile_usage(id, lesson_plan_id, profile_scope, profile_id, profile_version)`

### Evaluación y seguimiento
- `assessment_instruments(id, title, instrument_type, criteria_json)`
- `assessment_sessions(id, group_id, lesson_plan_id, instrument_id, date)`
- `group_progress(id, session_id, objective_id, observation, next_action)`
- `student_progress(id, session_id, student_id, objective_id, observation, progress_status, next_action)`
- `progress_evidence(id, scope, progress_id, evidence_type, description, recorded_at, author_id)`

### Sistema
- `audit_logs(id, actor_id, action, entity_type, entity_id, occurred_at, result)`
- `app_settings(key, value)`
- `schema_migrations(version, applied_at)`

## Reglas de integridad
- Foreign keys activadas en cada conexión SQLite.
- Índices para group_id, student_id, source_id, source_version_id y fechas.
- Restricciones CHECK para roles y estados.
- Transacciones para importación/versionado.
- No borrar en cascada evidencias o registros que deban retenerse; aplicar política explícita de archivo/supresión.
- No usar nombres de estudiantes como claves ni como términos indexados en FTS.
- La base de datos y sus copias deben protegerse; SQLite por sí solo no cifra archivos.

## Nota de implementación
Este documento es un modelo lógico inicial, no un esquema SQL aprobado. El SQL físico y las migraciones se construyen en Sprint 1/2 y deben probarse con datos sintéticos.
