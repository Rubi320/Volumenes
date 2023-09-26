 # 1. Descarga la imagen 'httpd' y comprueba que está en tu equipo.

    *docker pull httpd:lastest*: Descargamos la imagen de apache 
    *docker images* : Comprobamos que esta en el equipo

# 2. Crea un contenedor con el nombre 'asir_httpd'.

*docker -d -it -name asir_httpd httpd*: Creamos el contenedor
*docker ps* : Comprobamos que esta creado

# 3. Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.

*docker run -d -it -p 8000:80 --name asir_httpd httpd*

Escribimos en un buscador nuestro puerto : **http://localhost:8000** para comprobar que hemos mapeado bien

# 4. Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas. 

*docker run -it -p 8000:80 -v /home/asir2/Documentos/Volumenes/htdocs:/usr/local/apache2/htdocs --name asir_httpd httpd*

# 5. Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.

Creo un **file.html** dentro de la carpeta htdocs que es la carpeta donde guarda Apache2 las paginas web pero en este caso la carpeta es la de nuestro repositorio. En el html escribimos con la etiqueta **<html>**

*docker run -d -it -p 8000:80 -v /home/asir2/Documentos/Volumenes/htdocs:/usr/local/apache2/htdocs --name asir_httpd httpd*

Escribimos **http://localhost:8000/file.html** en el navegador y comprobamos

# 6. Crea un contenedor 'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000

*docker run -d -it -p 8000:80 -v /home/asir2/Documentos/Volumenes/htdocs:/usr/local/apache2/htdocs --name asir_web1 httpd*

# 7. Utiliza Code para hacer un hola mundo en html

Seguimos los pasos que hicimos en el apartado 5. Creamos otro html.

# 8. Crea otro contenedor 'asir_web2' con el mismo directorio y a otro puerto, por ejemplo 9080.

*docker run -d -it -p 9080:80 -v /home/asir2/Documentos/Volumenes/htdocs:/usr/local/apache2/htdocs --name asir_web2 httpd*

# 9. Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador 

# 10. Tienen que salir la misma página web   

Es correcto los dos servidos desde distintos puertos de host muestran la misma pagina web.
