

## **Docker Cheat Sheet**

#### **Instalación y Configuración**
- **Instalar Docker (Linux):**
  ```bash
  sudo apt-get install docker-ce docker-ce-cli containerd.io
  ```
- **Verificar instalación:**
  ```bash
  docker --version
  ```

#### **Comandos Básicos**
- **Verificar que Docker está corriendo:**
  ```bash
  docker info
  ```
- **Listar imágenes descargadas:**
  ```bash
  docker images
  ```
- **Listar contenedores en ejecución:**
  ```bash
  docker ps
  ```
- **Listar todos los contenedores (incluidos los detenidos):**
  ```bash
  docker ps -a
  ```

#### **Imágenes**
- **Descargar una imagen desde Docker Hub:**
  ```bash
  docker pull <nombre_imagen>
  ```
- **Construir una imagen desde un Dockerfile:**
  ```bash
  docker build -t <nombre_imagen> .
  ```
- **Eliminar una imagen:**
  ```bash
  docker rmi <nombre_imagen>
  ```

#### **Contenedores**
- **Correr un contenedor:**
  ```bash
  docker run <nombre_imagen>
  ```
  - **Correr un contenedor en segundo plano (detached):**
    ```bash
    docker run -d <nombre_imagen>
    ```
  - **Correr un contenedor con nombre:**
    ```bash
    docker run --name <nombre_contenedor> <nombre_imagen>
    ```
  - **Mapear puertos (host:contenedor):**
    ```bash
    docker run -p <puerto_host>:<puerto_contenedor> <nombre_imagen>
    ```
  - **Montar un volumen:**
    ```bash
    docker run -v <ruta_host>:<ruta_contenedor> <nombre_imagen>
    ```

- **Detener un contenedor:**
  ```bash
  docker stop <nombre_contenedor>
  ```
- **Iniciar un contenedor detenido:**
  ```bash
  docker start <nombre_contenedor>
  ```
- **Eliminar un contenedor:**
  ```bash
  docker rm <nombre_contenedor>
  ```
- **Eliminar todos los contenedores detenidos:**
  ```bash
  docker rm $(docker ps -a -q)
  ```

#### **Gestión de Volúmenes**
- **Listar volúmenes:**
  ```bash
  docker volume ls
  ```
- **Crear un volumen:**
  ```bash
  docker volume create <nombre_volumen>
  ```
- **Eliminar un volumen:**
  ```bash
  docker volume rm <nombre_volumen>
  ```

#### **Docker Compose**
- **Correr un stack con `docker-compose.yml`:**
  ```bash
  docker-compose up
  ```
- **Correr un stack en segundo plano:**
  ```bash
  docker-compose up -d
  ```
- **Detener un stack:**
  ```bash
  docker-compose down
  ```

#### **Inspección y Debugging**
- **Ver logs de un contenedor:**
  ```bash
  docker logs <nombre_contenedor>
  ```
- **Ver detalles de un contenedor:**
  ```bash
  docker inspect <nombre_contenedor>
  ```
- **Ingresar en un contenedor en ejecución:**
  ```bash
  docker exec -it <nombre_contenedor> /bin/bash
  ```

#### **Limpieza**
- **Eliminar contenedores detenidos, imágenes no utilizadas y redes:**
  ```bash
  docker system prune -a
  ```
- **Eliminar volúmenes no utilizados:**
  ```bash
  docker volume prune
  ```
