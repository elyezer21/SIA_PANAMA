# SIA-Panamá Frontend

Interfaz web del **Sistema Interno de Seguimiento Ambiental (SIA-Panamá)**,
construida para MiAmbiente conforme a la **Ley 41** de Panamá.

React + Vite + Framer Motion. Muestra cada expediente como una tarjeta con
semáforo (verde/amarillo/rojo) según la proximidad del vencimiento del
plazo legal.

**Código fuente y documentación completa:**
https://github.com/TU_USUARIO/SIA_PANAMA

## Uso rápido

```bash
docker pull TU_USUARIO/sia-panama-frontend:latest
docker run -p 5173:80 TU_USUARIO/sia-panama-frontend:latest
```

Este servicio consume la API del backend (`sia-panama-backend`) — usa el
`docker-compose.yml` del repositorio para levantar el stack completo:

```bash
docker-compose up -d
```

Luego visita http://localhost:5173

## Tags disponibles

| Tag | Descripción |
|---|---|
| `latest` | Última versión estable, publicada automáticamente desde `main` |
| `vX.Y.Z` | Releases versionados |

Imagen construida como build multi-stage (Node → Nginx) y publicada
automáticamente vía GitHub Actions en cada push a `main`.
