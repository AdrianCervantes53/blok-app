# CHECKPOINTS.md — Blok (nivel proyecto)

Criterios objetivos de "hecho" que aplican al proyecto completo, sin importar
el repo. Cada repo (`blok-api`, `blok-web`, `blok-android`) tiene además su
propio `CHECKPOINTS.md` con sus checks de stack (tests, linter, etc.) — este
archivo no los reemplaza, los complementa.

## Antes de marcar cualquier feature como `done` en `feature_list.json`

- [ ] El o los repos involucrados pasan sus propios checkpoints (ver `CHECKPOINTS.md` de cada repo)
- [ ] `progress/current.md` refleja el trabajo hecho, luego se mueve a `progress/history.md`
- [ ] El estado en `feature_list.json` es correcto por repo (no solo "done" global si falta un cliente)
- [ ] Los commits siguen Conventional Commits y vienen de una rama, no de `main`/`master`

## Deuda de seguridad conocida (revisar antes de dar por "portfolio-ready" una feature relacionada)

- [ ] `blok-api/app/config.py`: sin valores default para `database_url` ni `secret_key` — Pydantic debe exigir `.env`
- [ ] `blok-web/.env`: confirmar que está excluido por `.gitignore` (se commiteó una vez, verificar que no vuelva a pasar)
- [ ] JWT en `localStorage`: decisión pendiente (mantener con deuda documentada vs. migrar a `httpOnly` cookies) — ver `ROADMAP.md` Fase 3

## Antes de considerar el proyecto "portfolio-ready"

- [ ] Sin credenciales hardcodeadas en ningún repo
- [ ] README significativo en cada repo
- [ ] Tests sin warnings
- [ ] Arquitectura y estructura de carpetas consistentes con lo documentado
