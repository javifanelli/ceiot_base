# Ejercicio CiberKillChain - Defensa

Se realizó una copia del documento original utilizándolo como plantilla para la realización del ejercicio, quitando las instrucciones y el ejemplo.

## Alumno

Ing. César Javier Fanelli - Especialización en Internet de las Cosas.

## Enunciado

Desarrollar la defensa en función del ataque planteado en orden inverso.

Para cada etapa elegir una sola defensa, la más importante, considerar recursos limitados.

## Resolución

### Actions on Objectives

Al recibir múltiples quejas y reclamos de parte de los clientes indicando mal funcionamiento se decide hacer una visita a algunos de ellos para verificar el estado del funcionamiento del sistema.

Se desconecta del sistema nodos y servidor y se hace una verificación del funcionamiento de cada uno de ellos. Se corrobora que al enviarle mensajes los nodos responden de forma correcta, accionando sus salidas y reportando los parámetros correctos del ambiente. Luego se procede a verificar el funcionamiento del servidor con un nodo y se corrobora que los comandos de cambio de estado de las salidas son enviados por él de forma errática y fuera de lo normal.

Se llega a la conclusión que el servidor fue comprometido y que es el encargado de enviar los mensajes, mientras que los nodos funcionan de manera correcta y actúan de la forma que el servidor se los mande. Se notifica que el servidor fue víctima de un hackeo por una vulnerabilidad propia y se procede a mitigar los riesgos.

### Command and control

Técnicas utilizadas: [M1047](https://attack.mitre.org/mitigations/M1047/) y [M1033](https://attack.mitre.org/mitigations/M1033/)

   - Se hace una auditoría del sistema del servidor corroborando que se instaló un software que no es parte de la solución.
   - Se bloquea en el sistema operativo la capacidad de instalar software a cualquiera de los grupos y usuarios, previniendo así cualquier tipo de instalación de software malintencionado.

### Installation

Técnica utilizada: [M1038](https://attack.mitre.org/mitigations/M1038/)

   - Se verifica y bloquea todo el software de acceso remoto y se anula la posibilidad de conectarse por SSH al servidor con usuario y contraseña.
   - Se renuevan todos los certificados del broker MQTT y los nodos, a los cuales se les habilita la opción de renovarlos por OTA.

### Exploit

Técnica utilizada: [M1018](https://attack.mitre.org/mitigations/M1018/)

   - Se quita el acceso por SSH de cualquier usuario, dejando un solo usuario administrador. Esto es una continuación del paso en Installation.
   - Se renuevan todos los usuarios y contraseñas y se guardan cifrados en la base de datos de usuarios.

### Delivery

Técnica utilizada: [M1017](https://attack.mitre.org/mitigations/M1017/)

   - Se da un aviso masivo a los clientes de la empresa que se vulneraron los sistemas debido a un mail con phishing, y se los entrena para detectar este tipo de reemplazos de identidad fraudulentos.

### Weaponization

Esta etapa es un tanto complicada de eludir, pero como prevención se intentará mantener informados a los clientes con que no divulguen claves o sepan diferencias enlaces falsos de originales de la solución.

### Reconnaissance

Técnicas utilizadas: [DS0035](https://attack.mitre.org/datasources/DS0035/)

   - Minimizar la información expuesta acerca de clientes y expecificaciones técnicas sobre la solución, a fin de evitar divulgar información que pueda llevar a engaños.
   - Evitar publicar datos sobre los clientes en las redes sociales para disminuir los contactos con ellos.


#### Enlaces:

https://attack.mitre.org/

https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html