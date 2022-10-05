# CREAR SERVIDOR DHCP CON 2 TARJETAS

En esta forma vamos a crear el servidor DHCP, lo vamos a configurar con dos tarjetas; 
- 1º tarjeta: Adaptador puente; para poder salir a internet.
- 2º tarjeta: Red interna; para conectar el cliente en una red propia del servidor.

------------------------------------------------------------------------------------------------------

Empecemos con el servidor. 
Nos metemos en el fichero de configuración /etc/network/interfaces, para configurar la ip estáticamente.

