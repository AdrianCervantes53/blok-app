# specs/

Contiene las especificaciones de las features en construcción, una carpeta
por feature.

Para features que solo tocan un repo:
```
specs/<feature>/
├── requirements.md
├── design.md
└── tasks.md
```

Para features que cruzan repos (API + web y/o android):
```
specs/<feature>/
├── requirements.md   # EARS, la feature completa de punta a punta
├── design.md          # decisiones técnicas + contrato entre repos
├── api/tasks.md
├── web/tasks.md
└── android/tasks.md
```

Se crea la carpeta de una feature cuando pasa de `pending` a `spec_ready` en
`feature_list.json`, no antes.
