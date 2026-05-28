## Stack
Docker (Dockerfile-based image provider service). No application runtime language detected beyond shell/Docker tooling.

## Constraints
Never modify:
- Any `*.lock` files
- Any credential or secret files (`*.env`, `.env*`, `*secret*`, `*credential*`)
- `.git/` directory and its contents
- Generated files or build artifacts in `dist/`, `build/`, or `out/` directories

## Conventions
- Primary deliverable is Docker images; Dockerfiles are the core of this repository
- Follow Dockerfile best practices: use specific base image tags (not `latest`), minimise layers, use multi-stage builds where applicable
- Base images must be pinned to a digest or explicit version tag — never `latest`
- One logical service or image per Dockerfile
- Dead files (unreferenced, unused assets) should be removed rather than left in place

## Dependency manifests
- `Dockerfile` (and any `Dockerfile.*` variants) — base image versions declared via `FROM` directives
- Any `docker-compose.yml` or `docker-compose.*.yml` files present in the repository
