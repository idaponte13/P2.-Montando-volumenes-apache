# P2.-Montando-volumenes-apache

**1.Comproba que a tes a imaxe httpd**
**2.Crea un contenedor de nome 'asir_httpd'.**
**3.Mapea o porto 80 do contenedor có 8080 da túa máquina.**
**Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección.**
        ***Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/***
**4.Mostra unha páxina html aloxada no apache2 dende o teu navegador.**
**5.Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000**
**6.Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.**
**Comproba que los dous servidores mostran a mesma páxina**

**Fai a entrega describindo os pasos usados con comandos no readme dun proxecto público en git, adxunta no entregable o enlace.**