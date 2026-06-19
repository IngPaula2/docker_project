# Practica Docker Compose - CI

Proyecto de practica con backend Spring Boot, frontend HTML/JavaScript servido por Nginx y base de datos MySQL usando Docker Compose.

## Servicios

- Backend Spring Boot: <http://localhost:8091>
- Frontend Nginx: <http://localhost:8082>
- MySQL: `localhost:3308`

## Ejecutar con Docker Compose

1. Abrir Docker Desktop.
2. En la raiz del proyecto ejecutar:

```bash
docker compose up --build
```

Para reconstruir desde cero:

```bash
docker compose down
docker compose build --no-cache
docker compose up -d
```

## Endpoints de prueba

- <http://localhost:8091/saludar>
- <http://localhost:8091/estado>
- <http://localhost:8091/lista>
- <http://localhost:8091/sumar?numero1=5&numero2=7>

## Git y CI

Comandos sugeridos para subir el proyecto a GitHub:

```bash
git init
git add .
git commit -m "Primer version docker compose"
git branch -M main
git remote add origin https://github.com/USUARIO/docker-ci-cd.git
git push -u origin main
```

El workflow de CI esta en `.github/workflows/ci.yml`. En cada push o pull request hacia `main`, GitHub Actions compila el backend con Java 21 y construye las imagenes Docker del backend y frontend.
