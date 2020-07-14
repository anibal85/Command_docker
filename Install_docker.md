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
    
 Agregue la clave GPG oficial de Docker:

$$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

Verifique que ahora tiene la clave con la huella digital 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88, buscando los últimos 8 caracteres de la huella digital.

$ sudo apt-key fingerprint 0EBFCD88
___________________________________________________________________
pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
_____________________________________________________________________

Use el siguiente comando para configurar el repositorio estable . Para agregar el repositorio nocturno o de prueba , agregue la palabra nightlyo test(o ambos) después de la palabra stableen los comandos a continuación. Aprenda sobre canales nocturnos y de prueba .

Nota : El lsb_release -cssubcomando a continuación devuelve el nombre de su distribución de Ubuntu, como xenial. A veces, en una distribución como Linux Mint, es posible que deba cambiar $(lsb_release -cs) a su distribución principal de Ubuntu. Por ejemplo, si está usando Linux Mint Tessa, podría usar bionic. Docker no ofrece ninguna garantía en distribuciones de Ubuntu no probadas y no compatibles.

x86_64 / amd64
armhf
arm64
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
# INSTALAR DOCKER ENGINE

Actualice el índice del paquete e instale la última versión de Docker Engine y del contenedor, o vaya al siguiente paso para instalar una versión específica:

 $ sudo apt-get update
 $ sudo apt-get install docker-ce docker-ce-cli containerd.io

Para instalar una versión específica de Docker Engine, enumere las versiones disponibles en el repositorio, luego seleccione e instale:

# Enumere las versiones disponibles en su repositorio:

$ apt-cache madison docker-ce

######################################################################################################################
  * docker-ce | 5:18.09.1~3-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
  
  * docker-ce | 5:18.09.0~3-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
  
  * docker-ce | 18.06.1~ce~3-0~ubuntu       | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
  
  * docker-ce | 18.06.0~ce~3-0~ubuntu       | https://download.docker.com/linux/ubuntu  xenial/stable amd64 Packages
 ########################################################################################################################
  
Instale una versión específica utilizando la cadena de versión de la segunda columna, por ejemplo 5:18.09.1~3-0~ubuntu-xenial,.

$ sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io


Verifique que Docker Engine esté instalado correctamente ejecutando la hello-world imagen.

$ sudo docker run hello-world

Este comando descarga una imagen de prueba y la ejecuta en un contenedor.
Cuando se ejecuta el contenedor, imprime un mensaje informativo y sale.
