# FAILOVERS

En esta forma vamos a crear el servidor DHCP, lo vamos a configurar con tres tarjetas;

1º tarjeta: Adaptador puente; para poder salir a internet.
2º tarjeta: Red interna; para conectar el cliente en una red propia del servidor.
3º tarjeta: Adaptador puente.

-----------------------------------------------------------------------------------------

En el servidor ponemos una nueva tarjeta de red como adaptador puente y comentamos las demás. [NOTA 3](https://github.com/SeleneBP/DHCP/blob/main/NOTAS/NOTAS.md)

![image](img/1.PNG)

Reiniciamos el servicio -> ` systemctl restart networking `

Nos metemos en el fichero **/etc/dhcp/dhcpd.conf** y añadimos las siguientes líneas:

![image](img/2.PNG)

-----------------------------------------------------------------------------------------
#### LICENCIA

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Licencia de Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />Este obra está bajo una <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">licencia de Creative Commons Reconocimiento-CompartirIgual 4.0 Internacional</a>.
