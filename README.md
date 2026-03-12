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
cp backend/.env.example backend/.env
# Ajusta API_KEY/DB_* si aplica

docker compose up -d --build
```

Backend: `http://localhost:8000`  
Frontend: `http://localhost:3000`

