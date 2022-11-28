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

## Balanceo de carga

El balanceo de carga es una técnica que se utiliza para distribuir las solicitudes entrantes al grupo de servidores del backend. De esta manera, permite agregar muchos servidores cuando aumenta el tráfico.

Para realizar la practica, necesaitré usar tres servidores con nginx instalado en cada uno. Uno contendrá una página web, utilizaré el ya creado en las practicas anteriores. Otro con otra página web y uno que hará de balanceo de carga. Además, los tres servidores debrán estar en la misma red.

- Servdior segunda pagina

![](Imagenes/2pweb.png)

- Servidor balanceo de carga

![](Imagenes/carga.png)

1. Segunda pagina

- Instalamos NGINX en el servidor:

![](Imagenes/2p.png)

- Configuramos la pagina web por defecto:

![](Imagenes/2pconf.png)

![](Imagenes/2pnav.png)

2. Balanceo de carga:

- Instalamos NGINX en el servidor:

![](Imagenes/bal.png)

## Configuracion del servidor de balanceo

Para empezar debemos borrar el archivo de configuración predeterminado del sitio virtual por defecto y crear un fichero en la ruta de la imagen.

![](Imagenes/fichero.png)

- Añadir las siguientes lineas al fichero creado:

1. Upstream backend: nos permite añadir los servidores de las paginas webs mediante la ip de la red interna por la que se comunican. Además, establecemos el modo de balanceo que vamos a utilizar. Yo he escogido "IP_HASH" El cual nos permite la persistencia de la sesión.

2. Server: indicaremos la ip del servidor de balanceo y su configuracion.

![](Imagenes/balanceo.png)

- Comprobación

1. Para probar si la configuración del fichero está bien implementada se hace con el siguiente comando:

``nginx -t``

Si la configuración está correcta deberá aparecer estos mensajes:

![](Imagenes/comp.png)

2. Reiniciamos el servicio de NGINX

3. En un buscador escirbimos la ip del adaptador puente del balanceo de carga, nos debe salir nuestra primera pagina web y tras esperar unos segundos y refrescar la agina nos saldrá la segunda.

![](Imagenes/bal1.png)

![](Imagenes/bal2.png)
