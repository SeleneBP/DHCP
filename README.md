# DHCP

El protocolo DHCP permite obtener a un ordenador direcciones IP y otros parámetros de forma automática.
Este protocolo tiene una arquitectura cliente/servidor. El servidor escucha por el puerto 67 y el cliente por el 68.

El protocolo DHCP permite tres métodos de asignación de direcciones IP:

  - Configuración estática: El administrador de red es el que configura la red para que asigne una IP fija a determinados equipos. Esto es gracias a los clientes cuando hacen una petición IP, se identifican con su MAC, lo que permite la asignación de una IP en específica.
- Configuración dinámica: El servidor tiene varios rangos de IP, cuando recibe una petición este selecciona una IP adecuada dentro de su rango asignandosela al ordenador que lo ha pedido con un tiempo de alquiler (lease time). Este tiempo se puede prorrogar.
- Configuración automática: El servidor DHCP asigna una IP de forma permanente. Este caso se puede simular asignando mucho tiempo de alquiler, que puede llegar hasta 2 elevado a 32 - 2 segundos.
