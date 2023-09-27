# DHCP

El protocolo DHCP permite obtener a un ordenador direcciones IP y otros parámetros de forma automática.
Este protocolo tiene una arquitectura cliente/servidor. El servidor escucha por el puerto 67 y el cliente por el 68.

El protocolo DHCP permite tres métodos de asignación de direcciones IP:

  - Configuración estática: El administrador de red es el que configura la red para que asigne una IP fija a determinados equipos. Esto es gracias a los clientes cuando hacen una petición IP, se identifican con su MAC, lo que permite la asignación de una IP en específica.
- Configuración dinámica: El servidor tiene varios rangos de IP, cuando recibe una petición este selecciona una IP adecuada dentro de su rango asignandosela al ordenador que lo ha pedido con un tiempo de alquiler (lease time). Este tiempo se puede prorrogar.
- Configuración automática: El servidor DHCP asigna una IP de forma permanente. Este caso se puede simular asignando mucho tiempo de alquiler, que puede llegar hasta 2 elevado a 32 - 2 segundos.

--------------------------------------------------------------------------------------------
En el siguiente diagrama muestra los estados por el cual pasa el ordenador antes/durante y después de pedir una IP.

![serviciodhcp](https://user-images.githubusercontent.com/91204696/194101293-0ed1fbb2-856c-4830-9738-3d5fe21d01a1.PNG)

Cuando el cliente no tiene dirección IP entra en el estado INIT, luego en el proceso de configuración inicial 
se mueve al estado SELECTING y por último cuando ya tiene una dirección IP pasa al estado BOUND.
Imaginemos que el cliente reinicia la máquina, no tiene IP, en este caso no empieza en el estado INIT, si no al estado 
INIT-REBOOT, hay muchas ocasiones en las que vuelve a dar la misma direccion IP. Una vez que vuelve a tener IP pasa de 
nuevo al estado BOUND.
Si el servidor envia una petición al cliente (DHCPNAK), el cliente vuelve al estado INIT.

¿Qué pasa si expira el tiempo de concesión (lease time)? El cliente entra en estado RENEWING intentando así prorrogar su 
tiempo con esa IP, enviando un mensaje unicast al servidor del que obtuvo la dirección IP. El cliente espera, pero si no 
recibe una respuesta a su solicitud de renovacion, pasa al estado REBINDING y manda un mensaje broadcast a todos los 
servidores disponibles para obtener su prorrogación, pero si la IP expira sin obtener su prorrogación, el cliente vuelve
al estado INIT.

-----------------------------------------------------------------------------------------

Empecemos: 

[1º Forma:](https://github.com/SeleneBP/DHCP/blob/main/1ºForma/PRIMERA%20FORMA.md)
[2º Forma:]
[3º Forma:]
[4º Forma:]

-----------------------------------------------------------------------------------------
## REFERENCIAS 

[Tutorial servicio DHCP](https://www.fpgenred.es/DHCP/)


-----------------------------------------------------------------------------------------
#### LICENCIA

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Licencia de Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />Este obra está bajo una <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">licencia de Creative Commons Reconocimiento-CompartirIgual 4.0 Internacional</a>.

