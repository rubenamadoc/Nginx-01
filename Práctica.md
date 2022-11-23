# Casos prácticos.

## Versión de NGINX.

Para ver la versión de NGINX instalada se utiliza este comando.

`nginx -v`

![](Imagenes/Version.png)

## Ficheros de configuración.

Los ficheros de configuración de NGINX se encuentran en la ruta "/etc/nginx/"

![](Imganes/carpeta_nginx.png)

Existen muchos ficheros, pero en esta ocasión solo utilizaré:

- nginx.conf:Fichero encargado de la configuración general de NGINX.

- sites-available:Directorio donde almacenaramos nuestros sitios virtuales. Por defecto, nos crea con la instalación, un sitio virtual que podemos utilizar como referencia para nuevos sitios. 

![](Imagenes/available.png)

- sites-enable:Directorio donde están los sitios que tenemos activados. Crea un enlace simbólico de los ficheros de sites-available.

![](Imagenes/enable.png)

## Pagina web por defecto

El contenido de nuestras páginas web se alamcena en /var/www/. La página web por defecto de NGINX se encuentra en el directorio html. La página es index.nginx-debian.html:

![](Imagenes/pagina.png)

Este es el resultado despues de modificar la página por defecto:

![](Imagenes/cat.png)

![](Imagenes/mipagina.png)
