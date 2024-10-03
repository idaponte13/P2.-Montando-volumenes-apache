# P2.-Montando-volumenes-apache

**1.Comproba que a tes a imaxe httpd**

Para comprobar que sí temos a iamxe "httpd" escribiremos o comando `docker images` o pola súa parte dende o apartado de imaxes en VSCode.

**2.Crea un contenedor de nome 'asir_httpd'.**

Para crear un contenedor cun nome establecido polo usuario utilizaremos o comando `docker run -d --name (nome do contenedor) (imaxe)`, neste caso crearemolo con este codigo xa que queremos que se execute ao crealo (funcion "run" no comando) e queremos envialo a segundo plano e que non se deteña ao pechar a terminal (funcion "-d" no comando).

Por outra parte se soamente queremos crealo sen executalo podemos escribir o seguinte comando `docker create --name (nome do contenedor) (imaxe)`.

**3.Mapea o porto 80 do contenedor có 8080 da túa máquina.**

**Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección.**

***Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/***

Nesta tarefa xuntaremos os puntos 2 e o punto 3. Para mapear o porto añadiremos ao comando do punto 2 `-p 8080:80` é ademais `-v "$PWD"/(Directorio a nontar):/usr/local/apache2/htdocs/ (imaxe)` para montar o directorio htdocs do servidor apache no contenedor a partir do directorio actual ($PWD). Con todo isto o comando final quedatía da seguinte forma; `docker run -d --name asir_httpd -p 8080:80 -v /home/iago/Practica2:/usr/local/apache2/htdocs/ httpd`

**4.Mostra unha páxina html aloxada no apache2 dende o teu navegador.**

**5.Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000**

**6.Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.**

**Comproba que los dous servidores mostran a mesma páxina**

**Fai a entrega describindo os pasos usados con comandos no readme dun proxecto público en git, adxunta no entregable o enlace.**