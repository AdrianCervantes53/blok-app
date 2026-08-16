# ROADMAP.md — Blok

Visión de implementación a nivel de proyecto. No contiene detalle técnico —
eso vive en `specs/<feature>/` cuando la feature está lista para construirse.

## Fase 1 — MVP: esqueleto funcional sin offline

- [x] `blok-api`: proyecto base (FastAPI, SQLAlchemy, Alembic, Docker)
- [x] `blok-web`: proyecto base (React 19, TypeScript, Vite)
- [x] `blok-web`: módulo de autenticación (`core/auth/`) — JWT compartido
- [ ] Módulo Notas — primera validación end-to-end (API + web)
  - [ ] `blok-api`: endpoints CRUD de notas
  - [ ] `blok-web`: `modules/notas/` (types → api → hook → página)
  - [ ] `blok-android`: pantalla de notas (cuando el módulo esté estable en api + web)
- [ ] Resolver deuda de seguridad conocida (ver `CHECKPOINTS.md`)

## Fase 2 — Módulos adicionales

- [ ] Diario / registro de actividad
- [ ] Inventario
- [ ] Compras
- [ ] Seguimiento de libros/videos
- [ ] Agenda / recordatorios

## Fase 3 — Mejoras transversales

- [ ] Sync offline (explícitamente diferido hasta ahora)
- [ ] Decisión JWT: mantener en `localStorage` con deuda documentada, o migrar a cookies `httpOnly`

## Fuera de scope por ahora

- Auto-discovery de routers en `blok-api` (manual hasta que 4-5 módulos lo justifiquen)
- Cualquier automatización del harness (scripts, CLI) — evaluar solo si el mismo problema aparece varias veces
