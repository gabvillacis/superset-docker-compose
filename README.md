# Superset Docker Compose

Este repositorio contiene una configuración de Apache Superset utilizando Docker Compose.

---

## 🚀 Ejecución

1. Clona el repositorio:

   ```bash
   git clone https://github.com/gabvillacis/superset-docker-compose.git
   cd superset-docker-compose
   ```

2. Configura el archivo de entorno:

   Edita el archivo:

   ```
   docker/.env
   ```

   ### Cambios recomendados:

   #### 1. Contraseña de base de datos

   Modifica las siguientes variables con credenciales seguras:

   ```env
   DATABASE_PASSWORD=superset
   POSTGRES_PASSWORD=superset
   ```

   Opcionalmente puedes personalizar:

   ```env
   DATABASE_USER=superset
   POSTGRES_USER=superset
   POSTGRES_DB=superset
   ```

   #### 2. Clave secreta de Superset

   Modifica esta variable:

   ```env
   SUPERSET_SECRET_KEY=TEST_NON_DEV_SECRET
   ```

3. Levanta los servicios:

   ```bash
   docker compose up -d
   ```

4. Accede a Superset desde tu navegador:

   ```
   http://localhost
   ```

> El puerto `80` está mapeado en el `docker-compose.yml` como puerto de entrada al contenedor.

---

## 🧪 Comandos útiles

- Ver logs en tiempo real:

  ```bash
  docker compose logs -f
  ```

- Reiniciar servicios:

  ```bash
  docker compose restart
  ```

- Detener y eliminar contenedores:

  ```bash
  docker compose down
  ```

---
