
## 1.Descarga la imagen 'httpd' y comprueba que está en tu equipo.

Descargamos la imagen con el comando:

    docker pull httpd
Y la comprobamos con:

    docker images

## 2.Crea un contenedor con el nombre 'asir_httpd'

El contenedor se crea con:

    docker run -d --name asir_httpd httpd

## 3.Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.

Utilizamos el comando:

    docker run -d --name asir_httpd -p 8000:80 httpd

## 4.Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.


    docker run -d --name asir_httpd -p 8000:80 -v "$PWD/htdocs:/usr/local/apache2/htdocs/" httpd
## 5.Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.


Creamos el html dentro de la carpeta htdocs y comprobamos poniendo en el navegador:


    localhost:8000


## 6.Crea un contenedor 'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000.


Creamos el contenedor 'asir_web1' con:


    docker run -d --name asir_web1 -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd

## 7.Utiliza Code para hacer un hola mundo en html.


Creamos el html en code.


## 8.Crea otro contenedor 'asir_web2' con el mismo directorio y a otro puerto, por ejemplo 9080.


Creamos otro contenedor con el puerto 9080 con el comando:


    docker run -d --name asir_web2 -p 9080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd


## 9/10. Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador. Tienen que salir la misma página web.


Comprobamos poniendo en el navegador:


    localhost:8000


    localhost:9080
