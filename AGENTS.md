# AGENTS.md — Mapa de navegación para agentes de IA

> Punto de entrada para cualquier agente (Claude, OpenCode, etc.) que trabaje
> en el proyecto Blok. Este archivo es un mapa, no una lista exhaustiva de
> reglas: lee lo que necesites cuando lo necesites.

## 1. Antes de empezar

1. Lee `progress/current.md` — estado de la última sesión.
2. Lee `feature_list.json` — qué feature está activa y en qué repo(s).
3. Si la feature tiene entrada en `specs/<feature>/`, léela antes de tocar código.

## 2. Estructura del proyecto

Blok es 3 repos de código + este repo de coordinación (`blok-app`), clonados
juntos localmente:

```
blok-app/            (este repo — harness, sin código)
├── blok-api/         (gitignored aquí, repo propio en GitHub)
├── blok-web/         (gitignored aquí, repo propio en GitHub)
├── blok-android/     (gitignored aquí, repo propio en GitHub)
├── specs/
├── progress/
└── ...
```

Cada uno de `blok-api/`, `blok-web/`, `blok-android/` tiene su propio
`AGENTS.md` y `CHECKPOINTS.md`, específicos de su stack. Este `AGENTS.md`
cubre solo lo que aplica a los 3 por igual.

## 3. Mapa del repositorio

| Archivo / carpeta       | Qué contiene                                             | Cuándo leerlo |
|--------------------------|-----------------------------------------------------------|---------------|
| `feature_list.json`      | Features con estado por repo (`pending`/`in_progress`/`done`/`blocked`) | Siempre, al empezar |
| `ROADMAP.md`              | Fases y orden de construcción a nivel Blok                | Para elegir la siguiente feature |
| `progress/current.md`    | Estado de la sesión activa                                 | Siempre, al empezar |
| `progress/history.md`    | Bitácora append-only                                        | Si necesitas contexto histórico |
| `specs/<feature>/`       | `requirements.md` + `design.md` (compartidos) + `tasks.md` por repo | Antes de implementar esa feature |
| `CHECKPOINTS.md`          | Definición de "hecho" a nivel proyecto                     | Para auto-evaluarte |

## 4. Reglas duras (no negociables)

- **Una sola feature a la vez** — no mezcles cambios de varias tareas en la misma sesión, ni en el mismo repo ni entre repos.
- **Nunca commits directos a `main`/`master`.** Siempre desde una rama: `feature/`, `fix/`, `refactor/`, `docs/`, `chore/`.
- **Conventional Commits**, en minúsculas, en imperativo:
  ```
  <tipo>(<scope opcional>): <descripción>
  ```
  Tipos: `feat`, `fix`, `refactor`, `test`, `docs`, `chore`.
- **Un commit = una sola idea completa.**
- **No declares una feature `done` en `feature_list.json`** sin que los checkpoints del repo correspondiente pasen (ver `CHECKPOINTS.md` de cada repo).
- **Estructura limpia**: una responsabilidad por archivo/carpeta, sin mezclar conceptos.
- **Actualiza el estado** (`feature_list.json`, `progress/current.md`) mientras trabajas, no solo al final.

## 5. Flujo de trabajo

```
ROADMAP.md → elegir feature → specs/<feature>/ (si aplica) → implementar en el/los repo(s) → checkpoints del repo → feature_list.json actualizado → progress/history.md
```

Para features que tocan más de un repo (ej. un módulo nuevo con API + UI):
1. `specs/<feature>/requirements.md` y `design.md` cubren la feature completa (contrato entre repos incluido).
2. `specs/<feature>/api/tasks.md`, `web/tasks.md`, `android/tasks.md` — un checklist por repo.
3. Cada repo se implementa y verifica de forma independiente; `feature_list.json` trackea el estado de cada uno por separado.

## 6. Si te bloqueas

No inventes un workaround. Documenta el bloqueo en `progress/current.md` y para la sesión.
