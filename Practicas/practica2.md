# Practica2

Para la realizacion de la practica2, lo primero que he hecho ha sido instalar en ambas maquinas la herramienta **rsync**. Despues he hecho que usuario sea el dueño de la carpeta que se va a usar con rsyn con el comando => **sudo chown fran1:fran1 -R /var/www** Para coprobar su correcto funcionamiento clono en la maquina2 la carpeta /var/www de la maquina1 mediante el comando => **rsync -avz -e ssh ipmaquina1:/var/www/ /var/www/** ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/rsync.png) Y lo compruebo con el comando => **ls** en ambas maquinas.

Lo siquiente es hacer el acceso entre maquinas sin tener que usar continuamente una contraseña. Para ello genero una clave para la autenticación con el comando => **ssh-keygen -b 4096 -t rsa** ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/generateKey.png) Dejo en blanco passphrase y una vez creada la clave la copio en la otra maquina mediante => **ssh-copy-id UbuntuServer1** Para comprobarlo hago un ssh y veo que no me pide la clave. ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/sshSinKey.png)

Por ultimo hago uso de la herramienta crontab para la automatizacion de tareas. En mi caso hare que actualize el contenido de la carpeta /ver/www cada minuto. Para ello edito el archivo => ****y añado la linea =>****  ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/crontModif.png)

Compruebo pasado un minuto que se esta actualizando la carpeta con => **ls** ![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/copiaCron.png)
