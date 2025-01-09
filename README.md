# PPS-Unidad1Actividad1-JoseMi
Actividad 1 de la Unidad 1 de Puesta en Producción Segura. Tabajaremos con los Entornos de Desarrollo

Tenemos varios objetivos:

- [Crear un entorno de desarrollo Eclipse con docker](##Eclipse Docker)
- [Instalar extensiones en un IDE](##Instalar extensiones)
- [Probar los entornos de Desarrollo](##Prueba entornos) 
---
##Eclipse Docker

En la siguiente dirección [](https://hub.docker.com/r/dockeruc/eclipse) puedes encontrar podemos crear un contenedor docker con un entorno IDE Eclipse

Lee bien las instrucciones y ten en cuenta que tienes que hacer varias operaciones. Las que tienes a continuación son de un entorno Linux:

1. Crear las carpetas necesarias:
~~~
sudo mkdir -p  $HOME/eclipse/datos
sudo chown -R $(whoami) $HOME/docker/eclipse
sudo chgrp -R $(whoami) $HOME/docker/eclipse
~~~

2. Configurar el entorno gráfico 

~~~
export DISPLAY=:0
startxwin -- -listen tcp &
xhost + 
~~~

3. Lanzar el contenedor

~~~
sudo docker run -ti --rm \
           -e DISPLAY=$DISPLAY \
	       -e artifactory_host='IP:PUERTO'\
		   --name eclipse \
           -v /tmp/.X11-unix:/tmp/.X11-unix \
           -v `pwd`:/workspace \
           -v $HOME/docker/eclipse/datos:/home/developer \
           dockeruc/eclipse	

~~~
 __Explica el comando docker que has utilizado__

##Instalar extensiones



##Prueba entornos


[]()
Busca cuáles son las mejores extensiones de eclipse para programadores y las añades desde la tienda de eclipse (al menos plugins Checkstyle y PMD). Busca y escribe para qué sirven estos plugins y busca los plugins y complementos imprescindibles para eclipse.
Descarga el código fuente de un proyecto java: compila, enlaza y ejecutaló.
Utiliza las herramientas de depuración de Eclipse o Netbeans para depurar el proyecto.
