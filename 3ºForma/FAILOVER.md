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

Y luego nos vamos a **/etc/dhcp/dhcpd.conf** y configuramos el *failover*.

![image](img/3.PNG)

También configuramos **/etc/defaul/isc-dhcp-server**. Aquí simplemente ponemos en las opciones *-f -d*, para forzar a poner la tarjeta de red.

![image](img/4.PNG)

Reiniciamos -> ` systemctl restart isc-dhcp-server `

Clonamos la máquina SERVIDOR 1 y a la máquina clon le cambiamos el nombre SERVIDOR 2.

En el SERVIDOR 2, solo cambiamos la IP, porque al ser clonada vendrá la IP del SERVIDOR. 

>Ip nueva: 192.168.1.3

También tenemos que cambiar la IP en el *failover*.


![image](img/5.PNG)

Para hacer la comprobación en el SERVIDOR 2, apagamos el servicio *iscp* y en el cliente ponemos -> ` ipconfig /release `, para que nos renueve la IP y miramos nuestra IP y que servidor nos lo ha proporcionado.

![image](img/6.PNG)

Vemos que la IP que nos ha dado ha sido el SERVIDOR 1. 

Volvemos hacer lo mismo pero al contrario.

En el SERVIDOR 1, apagamos el servicio *iscp* y en el cliente volvemos a poner -> ` ipconfig /release `.

![image](img/7.PNG)

-----------------------------------------------------------------------------------------
#### LICENCIA

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Licencia de Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />Este obra está bajo una <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">licencia de Creative Commons Reconocimiento-CompartirIgual 4.0 Internacional</a>.
