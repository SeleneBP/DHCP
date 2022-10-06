# CREAR SERVIDOR DHCP CON 2 TARJETAS

En esta forma vamos a crear el servidor DHCP, lo vamos a configurar con dos tarjetas; 
- 1º tarjeta: Adaptador puente; para poder salir a internet.
- 2º tarjeta: Red interna; para conectar el cliente en una red propia del servidor.

------------------------------------------------------------------------------------------------------

Empecemos con el servidor. 
Nos metemos en el fichero de configuración **/etc/network/interfaces**, para configurar la ip estáticamente.

![image](img/1.PNG)

Ahora reiniciaremos el servicio Networking -> 
` systemctl restart networking `

Ahora configuramos el siguiente fichero: **/etc/default/isc-dhcp-server**

> Antes tendremos que mirar el nombre de nuestra tarjeta de red. En mi caso se llame *enp0s3*



-----------------------------------------------------------------------------------------
#### LICENCIA

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Licencia de Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />Este obra está bajo una <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">licencia de Creative Commons Reconocimiento-CompartirIgual 4.0 Internacional</a>.
