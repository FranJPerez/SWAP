# Practica5

## Crear una BD e insertar datos

Para la realizacion de la practica he hecho uso de MySQL y he creado una tabla con algunos datos.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/1P5.png)

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/2P5.png)

## Replicar una BD MySQL con mysqldump

Lo segundo sera hacer una copia de seguridad de la BD que tengo en la maquina1 en la maquina2\. Para ello hare uso de mysqldump.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/3P5.png)

Antes de hacer la copia, tengo que evitar que se cambien las BD y desbloquear las tablas.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/4P5.png)

Como ya he creado el fichero con mysqldump, puedo aceder a la maquina2(esclavo) para copiarlo con el comando scp.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/5P5.png)

Creo la base de datos.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/6P5.png)

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/7P5.png)

## Replicación de BD mediante una configuracion maestro-esclavo

Por ultimo hago que la sincronizcion entre maquinas sea automatica modificando el archivo /etc/mysql/mysql.conf.d/mysqld.cnf en modo superusuario, tanto en el maestro, como en el esclavo.

Las lineas que modificare seran:

- Comentar bind-address.
- Indicar log_error = /var/log/mysql/error.log.
- Descomentar server-id = 1 y log_bin = /var/log/mysql/bin.log.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/8P5.png)

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/8.2P5.png)

Reinicio mysql.service

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/9P5.png)

Ahora creo un usuario en mysql con privilegios en la maquina1.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/10P5.png)

Por ultimo ejecuto un comando que fijara las variables de mysql.

![img](https://github.com/FranJPerez/SWAP/blob/master/imagenes/11P5.png)
