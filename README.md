# Ejercicio-cluster-fstab
## Creación del cluster con dos nodos
Lo que hacemos en crear la máquina virtual sin disco duro ya que usaremos un iso con el que arrancaremos el SO live. El siguiente paso es iniciar los nodos, para ello lo que haremos será crear dos máquinas virtuales las cuales arrancarán desde la tarjeta de red, por lo que tampoco les hace falta disco duro. Nos tenemos que asegurar que tanto los nodos como la maquina principal están en la misma red. Si todo los anterior es correcto una vez iniciados los nodos se configuran automáticamente y se enlazan al cluster.
![cluster.PNG](./cluster.PNG)

## Creación de trabajos con cron
Lo que hacemos es editar con nano el /etc/crontab y escribimos lo siquiente:
![crontab.PNG](./crontab.PNG)

Configurar los servidores DNS a los que va a acudir nuestro servidor en el caso de que nos conozca la IP del nombre por el que le están preguntando.
![named.conf.options.PNG](./named.conf.options.PNG)

Crear las zonas directas de cada sitio donde se relacionan las IP con los nombres.
![rd.sitioa.com.PNG](./rd.sitioa.com.PNG)
![rd.sitiob.net.PNG](./rd.sitiob.net.PNG)
![rd.sitioc.net.PNG](./rd.sitioc.net.PNG)

## Creación del servidor Apache
Crear los host virtuales, para ello hay que crear primero la estructura de carpetas y luego configurar los archivos.
![sitioa.com.conf.PNG](./sitioa.com.conf.PNG)
![sitiob.net.conf.PNG](./sitiob.net.conf.PNG)
![sitioc.net.conf.PNG](./sitioc.net.conf.PNG)

## Comprobación desde el lado del cliente
Comprobación de los host por el terminar de un cliente.
![comprobacionHost.PNG](./comprobacionHost.PNG)

Comprobación de los host en el navegador del cliente.
![navegadorSitioa.PNG](./navegadorSitioa.PNG)
![navegadorSitiob.PNG](./navegadorSitiob.PNG)
![navegadorSitioc.PNG](./navegadorSitioc.PNG)
