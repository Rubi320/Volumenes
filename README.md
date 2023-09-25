1.Descarga la imagen 'httpd' y comprueba que está en tu equipo.

    docker pull httpd:lastest
    docker images

2.Crea un contenedor con el nombre 'asir_httpd'.

docker -d -it -name asir_httpd httpd
docker ps

3.Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.

docker run -d -it -p 8000:80 --name asir_httpd httpd

escribimos en un buscador nuestro puerto : http://localhost:8000 para comprobar que hemos mapeado bien

4.Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas. 

docker run -it -p 8000:80 -v /home/asir2/Documentos/Volumenes/htdocs:/usr/local/apache2/htdocs --name asir_httpd httpd

5.Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.

docker run -it -p 8000:80 -v /home/asir2/Documentos/Volumenes/htdocs/file.hmtl:/usr/local/apache2/htdocs --name asir_httpd httpd

6.Crea un contenedor 'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000