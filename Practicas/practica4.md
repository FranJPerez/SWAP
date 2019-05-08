# Practica4

## Certificado de seguridad

Lo primero que he realizado ha sido hacer un certificado en mi maquina 1\. Para ello hago uso del comando => a2enmod ssl y reinicio apache2 con => systemctl restart apache2

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/1.png)

Despues creo un directorio en apache para ssl y genero el certificado en mi caso con una duracion de un año. Y para generarlo me pedira unos datos que me inventare para la realizacion de la practica.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/2.png)

Una vez creado el certificado, modifico el archivo de configuración.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/3.png)

Despues activo el servicio ssl y reinicio apache como me indica el terminal.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/4.png)

Para comprobar si funciona correctamente realizo un curl https.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/5.png)

Despues hago un clonado de la maquina uno y cambio su direccion ip y el nombre en los diferentes archivos. Modificando tanto el archivo de la ruta /etc/network/interfaces para cambiar su direccion ip.

Y los archivos de la ruta /etc/hosts y /etc/hostnames

A continuacion compio la carpeta de una de las dos maquinas de ssl en el balanceador con rsync.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/6.png)

Confiuro nginx para que haga uso del puerto 443 con ssl.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/7.png)

Una vez hecho esto compruebo que funciona con un curl con peticiones al balanceador, de nuevo con https.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/8.png)

## cortafuegos

Por ultimo configuro el cortafuegos para que filtre el trafico de la granja web. Para esto utilizo iptables, haciendo un scipt que se iniciara al arrancar la maquina. Dicho script lo almacenare en /usr/local/bin con el nombre de "iptables-script-init.sh".

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/9.png)

Lanzo el demonio con los comandos: => systemctl daemon-reload => systemctl enable iptables-config-init.service

Y creo el script.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/10.png)

Despues reinicio la maquina y compruebo los puertos de escucha activos.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/11.png)

Y por ultimo compruebo que el cortafuegos esta bien configurado.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/12.png)
