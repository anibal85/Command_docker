Desinstalar versiones anteriores 

Las versiones anteriores de Docker fueron llamados docker, docker.ioo docker-engine. Si están instalados, desinstálelos:

$ sudo apt-get remove docker docker-engine docker.io containerd runc

# CONFIGURAR EL REPOSITORIO

Actualice el aptíndice del paquete e instale paquetes para permitir uso de un repositorio sobre HTTPS:

$ sudo apt-get update

$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
