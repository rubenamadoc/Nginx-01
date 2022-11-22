# Comparativa con apache

Apache es uno de los princiaples rivales de NGINX. Existiendo el primero desde los años 90, ha podido conslolidar una gran comunidad de usuarios.
Para saber cual es el que más se adecua a las necesidades, voy a comparar ambos servicios, dividiéndola por partes:

- Compatibilidad con S0'S: Ambos servicios funcionan perfectamente en sistemas operativos que soportan Unix. Pero en este caso, Apache gana. Debido a que el rendimiento de NGINX en Windows no es tan bueno como el de apache.
- Soporte: El mejor servicio para usuarios novatos es NGINX. Es cierto que ambos presentan una comunidad activa en foros. Pero, NGINX, presenta un soporte por parte de la compañía.
- Rendimiento: NGINX es capaz de ejecutar simultnéamente 1000 conexiones de contenido estático dos veces más rápido que Apache y utilizando menos memoria. Sin embargo, ambos empatan en el rendimiento de contenido dinámico.
- Escalabilidad: NGINX es capaz de administrar varias solicitudes de clientes, esta arquitectura basada en eventos permite tener un rendimiento mayor incluso si se trata de un tráfico pesado. Esto es imposible en Apache, debido a su arquitectura de subprocesos múltiples que dificultan la escalabilidad. Además, Apache procesa las solicitudes de un usuario por medio de HTTP o HTTPS de una a una. Mientras que, NGINX al ser más robusto, es apto para todo tipo de sitios y tráfico web.
