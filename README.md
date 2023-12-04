# Instalamos el paquete mendiante el uso del comando:

    sudo apt install isc-dhcp-server

# Editamos la configuración básica 

Se hace uso del fichero ***/etc/dhcp/dhcpd.conf***

Primero creamos la subred con una máscara. Luego se especifica el broadcast, el gateway, el rango y otros valores

![ Configuración dhcpd.conf ](./imagenes/1.png)

Luego en ese mismo documento podemos decirle al servidor que le asigne una IP fija a un cliente mediante el uso de la MAC de este

![ Configuración dhcpd.conf 2 ](./imagenes/2.png)

Luego configuramos las interfaces en el documento ***etc/default/isc-dhcp-server***

![ Configuración isc-dhcp-server ](./imagenes/3.png)

Seguido de lo anterior se configura el documento ***/etc/netplan/00-installer-config.yaml***

![ Configuración 00-installer-config.yaml ](./imagenes/4.png)

Y para finalizar creamos un script para indicarle al sevidor el funcionamiento deseado. Este script se lanzará cada vez que se reinicie el servidor

![ Script ](./imagenes/5.png)

# Comprobamos su funcionamiento

![ Systemctl status ](./imagenes/6.png)

# Ahora revisaremos los clientes

Cliente con IP dińamica

![ IP Dinámica ](./imagenes/7.png)

Cliente con IP fija mendiante uso de su MAC

![ Systemctl status ](./imagenes/8.png)

Podemos comprobar los paquetes DHCP mediante el uso de Wireshark

![ Wireshark ](./imagenes/9.png)



