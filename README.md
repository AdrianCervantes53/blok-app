# Blok

Personal management system built as a full-stack project across three repositories.

## What it does

Blok is a modular app for managing daily personal data: notes, diary, agenda, inventory, purchases, and media tracking (books/videos).

## Architecture

```
blok/
├── blok-api      → REST API (FastAPI + PostgreSQL)
├── blok-web      → Web client (React)
└── blok-android  → Mobile client (Kotlin + Jetpack Compose)
```

The backend exposes a single REST API consumed by both clients independently.

## Repositories

| Repo | Stack | Description |
|------|-------|-------------|
| [blok-api](https://github.com/AdrianCervantes53/blok-api) | FastAPI · PostgreSQL · Alembic · JWT | Backend REST API |
| [blok-web](https://github.com/AdrianCervantes53/blok-web) | React | Web client |
| [blok-android](https://github.com/AdrianCervantes53/blok-android) | Kotlin · Jetpack Compose | Android client |

## Tech Stack

**Backend**
- FastAPI + SQLAlchemy + Alembic
- PostgreSQL
- JWT authentication
- Docker

**Web**
- React

**Android**
- Kotlin + Jetpack Compose

## Status

Active development — modular features added incrementally.
