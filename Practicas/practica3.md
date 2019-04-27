# Practica3

Lo primero que he realizado, es la instalacion de una nueva maquina servirdor que usare como balanceador. Y una maquina de peticiones. Para el balanceador he realizado una nueva instalacion para evitar problemas con Apache. Y para la maquina de peticiones he realizado un clon de la maquina 1 y le he cambiado la direccion ip a ambas.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/configuracionnetworkinterfacesbalanceador.png)

Despues he instalado nginx en el balanceador con la orden => sudo apt-get install nginx.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/configuracionnginx.png)

He comprobado que funciona con la orden => sudo systemctl status nginx (previamente lo inicie con start)

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/statusnginx.png) Despues configuro el archivo =>

Para hacer uso del algoritmo Round-Robin modifico el archivo => /etc/haproxy/nginx.conf. Una vez creado, reinicio nginx (restart) para guardar los cambios cada vez que realizaba algun cambio.

Y compruebo el funcionamiento del balanceador, haciendo un curl 192.168.1.102 y segundo la configuracion mostrara el hola.html de la maquina1 o el de la maquina2

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/curlbalanceador.png)

Por ultimo hago un top en las maquinas: 1, 2 y el balanceador, mientras que con peticiones realizo las llamadas al balanceador, que se encargara de repartirlas entre maquinas. Para ello hago uso de la orden =>ab -n 1000000 -c 50 <http://192.168.1.102/hola.html>

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/nginxtop.png)

Una vez comprobado, paro nginx con la orden stop y realizo la instalacion de haproxy.

Configuro el archivo => /etc/haproxy/haproxy.conf

Y hago al igual que con nginx un stop en todas las maquinas mientras hago las llamadas con peticiones.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/haproxytop.png)
