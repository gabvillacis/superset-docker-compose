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

## 📊 Monitorización y Logging

- **Estado de contenedores**  
  ```bash
  docker compose ps
  ```  
  Muestra nombre, estado, puertos y tiempo de ejecución de cada servicio.

- **Métricas en tiempo real**  
  ```bash
  docker stats superset_app superset_db redis
  ```  
  CPU, memoria, I/O de disco y red de los contenedores especificados.

- **Logs de Superset**  
  ```bash
  docker compose logs -f superset_app
  ```  
  Sigue en tiempo real los mensajes de arranque, errores y actividad de la aplicación.

- **Logs de Celery (worker)**  
  ```bash
  docker compose logs -f superset_worker
  ```  
  Registra la actividad y posibles fallos de los procesos asíncronos de Superset.

- **Logs de Redis y Postgres**  
  ```bash
  docker compose logs -f redis
  docker compose logs -f db
  ```  
  Permite diagnosticar problemas de caché (Redis) o de la base de datos de metadata (Postgres).
---
