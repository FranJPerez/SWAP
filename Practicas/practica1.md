# Práctica 1

Lo primero que hice para esta practica, fue la correcta instalacion de dos maquinas virtuales en Virtualbox, del sistema operativo Ubuntu 16 de 64 bits.

Una vez instalados nombre una como UbuntuServer1 y la otra como UbuntuServer2\. En ambos uso de usuario fran1 (ya que tuve un problema para el correcto funcionamiento del servidor2) y la contraseña 123 (Simplemente para evitar confundirme). Como parte de la configuracion de ambas maquinas he instalado LAMP, ssh y curl. Ademas he habilitado el segundo adaptador interno de virtualbox en ambas maquinas y tambien le he dado la dirección ip. Ademas modifique en ambas maquinas el fichero => _/etc/network/interface_ con el editor _vi_ y he añadido: auto enp0s8 iface enp0s8 inet static address 192.168.1.100 (192.168.1.101 en ubuntuServer2) gateway 192.168.1.1 netmask 255.255.255.0 network 192.168.1.0 broadcast 192.168.1.255

Lo primero que he hecho ha sido ejecutar el comando => _ifconfig_ para ver las direcciones ip de cada una. ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/ifconfig.png)

Despues con ssh me he conectado desde ubuntuServer1 a ubuntuServer2 mediante el comando => _ssh 192.168.1.101_ Despues me ha pedido la contraseña de ubuntuServer2 y ya he accedido. Despues salgo de dicha maquina mediante el comando _exit_. ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/ssh.png)

Y por ultimo he creado en ubuntuServer2 en el directorio _/var/www_ el archivo _hola.html_ y mediante el comando => _curl <http://192.168.1.101/hola.html>_ he accedido a dicho documento. ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/curl.png)
