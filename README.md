# Command_docker
                                                     Comando Utiles para Docker

Estos son los comandos que he necesitado para hacer funcionar Docker en un entorno Vagrant.
Construir una imagen:
docker build --build-arg -t <nombre_imagen> .
Construir una imagen detrás de un proxy:
docker build --build-arg http_proxy=http://<proxy>:<port> --build-arg https_proxy=http://<proxy>:<port> -t <nombre_imagen> .
Hacer pull de una imagen ya construida:
docker pull nginx:1.13-alpine
Añadir un TAG a una imagen:
docker tag <nombre_imagen> <nombre_imagen>:<tag>
Inspeccionar una imagen:
docker inspect <nombre_imagen>
Guardar imagen en un fichero TAR:
docker save <nombre_imagen> > <fichero>.tar
Eliminar imagen:
docker rmi <nombre_imagen>:<TAG>
Eliminar todas las imágenes:
docker rmi `docker images -q`
Ejecutar contenedor:
docker run -v <unidad_host>:<unidad_docker> -it --name <nombre_contenedor> -d <nombre_imagen>
Eliminar contenedor:
docker rm <nombre_contenedor>
Eliminar todos los contenedores parados:
docker rm `docker ps -a -q`
Lista de imágenes:
docker images
Ver contenido de una imagen:
docker run -it image_name sh
  
# Lista contenedores en ejecución:
docker ps -a
  
# Conectar a un contenedor en ejecución:
docker exec -i -t a9ddb677957f /bin/bash

# Build Docker-Compose:
docker-compose build
  
# Configurar Dockerfile para mantener el docker en ejecución:
CMD tail -f /dev/null
  
# Up Docker-Compose segundo plano:
docker-compose up -d
  
# Ver salida de Docker-Compose:
docker-compose logs -f -t

# Detener un Docker-Compose:
docker-compose down
  
# Detener un Docker-Compose y eliminar volúmenes:
docker-compose down -v
  
# Ver Docker-Compose en ejecución:
docker-compose ps

# Ejecutar un comando en un conenedor de docker-compose:
docker-compose exec <nombre-servicio> /bin/bash

# Eliminar Docker-Compose detenidos:
docker-compose rm

