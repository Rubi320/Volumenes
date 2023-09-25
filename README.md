1.Descarga la imagen 'httpd' y comprueba que está en tu equipo.

    docker pull httpd:lastest
    docker images

2.Crea un contenedor con el nombre 'asir_httpd'.

docker -d -it -name asir_httpd httpd
docker ps
