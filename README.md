# DHCP

El protocolo DHCP permite obtener a un ordenador direcciones IP y otros parámetros de forma automática.
Este protocolo tiene una arquitectura cliente/servidor. El servidor escucha por el puerto 67 y el cliente por el 68.

El protocolo DHCP permite tres métodos de asignación de direcciones IP:

  - Configuración estática: El administrador de red es el que configura la red para que asigne una IP fija a determinados equipos. Esto es gracias a los clientes cuando hacen una petición IP, se identifican con su MAC, lo que permite la asignación de una IP en específica.
- Configuración dinámica: El servidor tiene varios rangos de IP, cuando recibe una petición este selecciona una IP adecuada dentro de su rango asignandosela al ordenador que lo ha pedido con un tiempo de alquiler (lease time). Este tiempo se puede prorrogar.
- Configuración automática: El servidor DHCP asigna una IP de forma permanente. Este caso se puede simular asignando mucho tiempo de alquiler, que puede llegar hasta 2 elevado a 32 - 2 segundos.

--------------------------------------------------------------------------------------------
En el siguiente diagrama muestra los estados por el cual pasa el ordenador antes/durante y despues de pedir una IP.

![serviciodhcp](https://user-images.githubusercontent.com/91204696/194101293-0ed1fbb2-856c-4830-9738-3d5fe21d01a1.PNG)

Cuando un cliente no tiene una dirección IP válida, está en el estado INIT. Durante el proceso de configuración inicial, el cliente se mueve al estado SELECTING, y en el momento en el que está configurado correctamente con una dirección IP, se mueve al estado BOUND. Cuando se reinicia el cliente, se pasa al estado INIT-REBOOT, y después de que se confirma que su dirección IP es válida, se mueve al estado BOUND. Si un servidor envía un mensaje DHCPNAK al cliente, el cliente vuelve al estado INIT.

Antes de que expire el tiempo de concesión (lease time) de la dirección IP del cliente, éste entra en estado de RENEWING e intenta prorrogar su tiempo con esa IP mediante el envío de un mensaje unicast al servidor del que obtuvo su dirección IP. El cliente espera un tiempo, y si no recibe respuesta a su solicitud de renovación, entra en el estado de REBINDING y difunde un mensaje broadcast para extender su prorrogación en cualquier servidor disponible. Si el contrato de arrendamiento expira sin que el cliente renueve con éxito su concesión, el cliente vuelve al estado INIT.
