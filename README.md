# P2.-Montando-volumenes-apache

**1.Comproba que a tes a imaxe httpd**

Para comprobar que sí temos a iamxe "httpd" escribiremos o comando `docker images` o pola súa parte dende o apartado de imaxes en VSCode.

**2.Crea un contenedor de nome 'asir_httpd'.**

Para crear un contenedor cun nome establecido polo usuario utilizaremos o comando `docker run -d --name (nome do contenedor) (imaxe)`, neste caso crearemolo con este codigo xa que queremos que se execute ao crealo (funcion "run" no comando) e queremos envialo a segundo plano e que non se deteña ao pechar a terminal (funcion "-d" no comando).

Por outra parte se soamente queremos crealo sen executalo podemos escribir o seguinte comando `docker create --name (nome do contenedor) (imaxe)`.

**3.Mapea o porto 80 do contenedor có 8080 da túa máquina.**

**Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección.**

***Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/***

Nesta tarefa xuntaremos os puntos 2 e o punto 3. Para mapear o porto añadiremos ao comando do punto 2 `-p 8080:80` para mapear o porto 80 e ademais `-v "$PWD"/(Directorio a nontar):/usr/local/apache2/htdocs/ (imaxe)` para montar o directorio htdocs do servidor apache no contenedor a partir do directorio actual ($PWD). Con todo isto o comando final quedaría da seguinte forma: `docker run -d --name asir_httpd -p 8080:80 -v /home/iago/htdocs:/usr/local/apache2/htdocs/ httpd`

**4.Mostra unha páxina html aloxada no apache2 dende o teu navegador.**

Para mostrar una paxina html aloxada no apache2 crearemos un arquivo html no directorio asociado no punto anterior, no meu caso dentro do directorio Practica2.
Unha vez feito iso buscamos no noso navegador `localhost:8080/` e se o fixemos ben aparecerá o index coa nosa páxina html.

**5.Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000**

Neste caso crearemos o un contenedor chamado asir_web1 e o mapearemos co porto 80 do contenedor usando o 8000 da nosa máquina.

O comando a executar é o seguinte ` docker run -d --name asir_web1 -p 8000:80 -v /home/iago/htdocs:/usr/local/apache2/htdocs/ httpd`.

**6.Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.**

**Comproba que los dous servidores mostran a mesma páxina**

Ao igual que no punto anterior crearemos un contenedor co nome asir_web2 pero neste caso mapearemos o porto 80 có 8090 da nosa máquina

O comando a executar é o seguinte `docker run -d --name asir_web2 -p 8090:80 -v /home/iago/htdocs:/usr/local/apache2/htdocs/ httpd`.

Por último para comprobar que os dous servidores mostran a mesma paxina web buscaremos no noso navegador web `http://localhost:8000/` para "asir_web1" e `http://localhost:8090/` para "asir_web2"
