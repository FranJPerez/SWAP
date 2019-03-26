# Práctica 1

Lo primero que hice para esta practica, fue la correcta instalacion de dos maquinas virtuales en Virtualbox, del sistema operativo Ubuntu 16 de 64 bits.

Una vez instalados nombre una como UbuntuServer1 y la otra como UbuntuServer2\. En ambos uso de usuario fran1 (ya que tuve un problema para el correcto funcionamiento del servidor2) y la contraseña 123 (Simplemente para evitar confundirme). Como parte de la configuracion de ambas maquinas he instalado LAMP, ssh y curl. Ademas he abierto el segundo adaptador interno de virtualbox en ambas maquinas y tambien le he dado la dirección ip.

Lo primero que he hecho ha sido ejecutar el comando "ifconfig" para ver las direcciones ip de cada una (imagen ifconfig) ![img](C:\Users\fj_ph\Documents\GitHub\SWAP\imagenes\ifconfig.png)

Despues con ssh me he conectado desde ubuntuServer1 a ubuntuServer2 mediante el comango=> ssh 192.168.1.101 Despues me ha pedido la contraseña de ubuntuServer2 y ya he accedido. Despues salgo de dicha maquina mediante el comando exit. (imagen ssh)

Y por ultimo he creado en ubuntuServer2 en el directorio /var/www el archivo hola.html y mediante el comando"" he accedido a dicho documento. (imagen curl)
