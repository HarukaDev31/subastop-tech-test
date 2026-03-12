# subastop-tech-test

Repo principal (orquestador) que contiene:

- `backend/` como **submodule** → `subastop-tech-test-back`
- `frontend/` como **submodule** → `subastop-tech-test-front`

## Clonar

```bash
git clone --recurse-submodules https://github.com/HarukaDev31/subastop-tech-test.git
```

Si ya clonaste sin submodules:

```bash
git submodule update --init --recursive
```

## Levantar todo con Docker

```bash
cp .env.example .env
cp backend/.env.example backend/.env
# Ajusta API_KEY/DB_* si aplica (se toma desde el .env de la raíz)

docker compose up -d --build

# Setup inicial del backend
docker compose exec app php artisan key:generate
docker compose exec app php artisan migrate
docker compose exec app php artisan db:seed
```

Nota: el contenedor `app` ejecuta `composer install` al arrancar (incluye `require-dev` para que funcionen los seeders).

Si vienes de una versión anterior del compose y te falla Faker o permisos, haz un reset completo:

```bash
docker compose down -v
docker compose up -d --build
```

Backend: `http://localhost:8000`  
Frontend: `http://localhost:3000`

