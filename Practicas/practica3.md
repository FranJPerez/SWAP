# Practica3

Lo primero que he realizado, es la instalacion de una nueva maquina servirdor que usare como balanceador. Y una maquina de peticiones. Para el balanceador he realizado una nueva instalacion para evitar problemas con Apache. Y para la maquina de peticiones he realizado un clon de la maquina 1 y le he cambiado la direccion ip.

Despues he instalado nginx en el balanceador con la orden => sudo apt-get install nginx

He comprobado que funciona con la orden => sudo systemctl status nginx (previamente lo inicie con start)

Una vez creado, reinicio nginx (restart) para guardar los cambios cada vez que realizaba algun cambio.

Y compruebo el funcionamiento del balanceador, haciendo un curl 192.168.1.102 y segundo la configuracion mostrara el hola.html de la maquina1 o el de la maquina2

Como no puedo instalar haproxy uso directamente top para hacer peticiones desde una maquina distinta a las maquinas1, maquina2 y el balanceador.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/statusnginx.png) ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/configuracionnginx.png) ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/curlbalanceador.png) ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/nginxtop.png) ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/haproxytop.png) ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/configuracionnetworkinterfacesbalanceador.png)
