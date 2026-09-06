# SIA-Panamá Backend

API REST del **Sistema Interno de Seguimiento Ambiental (SIA-Panamá)**,
construida para MiAmbiente conforme a la **Ley 41** de Panamá.

FastAPI + PostgreSQL + integración nativa con ClamAV para escanear cada
Estudio de Impacto Ambiental (EsIA) antes de guardarlo, y cálculo automático
de plazos legales por categoría de proyecto (I, II, III).

**Código fuente y documentación completa:**
https://github.com/TU_USUARIO/SIA_PANAMA

## Uso rápido

```bash
docker pull TU_USUARIO/sia-panama-backend:latest
```

Este servicio espera correr junto a `postgres` y `clamav` — usa el
`docker-compose.yml` del repositorio para levantar el stack completo con un
solo comando:

```bash
docker-compose up -d
```

## Variables de entorno

| Variable | Default | Descripción |
|---|---|---|
| `DATABASE_URL` | `postgresql://sia_user:sia_pass@postgres:5432/sia_panama` | Cadena de conexión a PostgreSQL |
| `CLAMAV_HOST` | `clamav` | Host del daemon ClamAV |
| `CLAMAV_PORT` | `3310` | Puerto del daemon ClamAV |

## Endpoints principales

- `GET /health` — health check
- `GET /docs` — documentación interactiva (Swagger)
- `POST /expedientes/` — crear expediente con cálculo automático de plazo legal
- `POST /documentos/upload-esia/{id}` — subir y escanear un EsIA

## Tags disponibles

| Tag | Descripción |
|---|---|
| `latest` | Última versión estable, publicada automáticamente desde `main` |
| `vX.Y.Z` | Releases versionados |

Imagen construida y publicada automáticamente vía GitHub Actions en cada
push a `main`.
