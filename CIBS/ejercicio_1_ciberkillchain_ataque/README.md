# Ejercicio CiberKillChain - Ataque

Se realizó una copia del documento original utilizándolo como plantilla para la realización del ejercicio, quitando las instrucciones y el ejemplo.

## Alumno

Ing. César Javier Fanelli - Especialización en Internet de las Cosas.

## Enunciado

Armar una cyberkillchain usando técnicas de la matriz de Att&ck para un escenario relacionado al trabajo práctico de la carrera.
  
## Datos trabajo práctico

En el siguiente [link](https://github.com/javifanelli/GdP) se encuentra la planificación del proyecto final hecha en la materia Gestión de Proyectos.

### Descripción

El trabajo práctico final de la carrera consta de un sistema de control de ambientes a distancia. Se pretende controlar la temperatura mediante calefacción y la iluminación de una habitación o recinto dentro de una casa, lo que sería un principio de domótica. El nodo de control estará implementado con un ESP32 y reportará y recibirá los datos de un servidor alojado en una Raspberry Pi de forma local dentro de la casa. Dicho servidor alojará el frontend y el backend, y tendrá una interfaz web con logueo de usuarios para poder ver y cambiar los parámetros del nodo. La comunicación entre las partes se hará por MQTT y en el servidor se alojarán los valores de las mediciones en una base de datos.

Para mayor información, por favor dirigirse a la [planificación del proyecto](https://github.com/javifanelli/GdP) donde se encuentra información detallada. Se recomienda leer la [propuesta de proyecto](https://github.com/javifanelli/GdP/blob/master/Propuesta%20de%20proyecto%20(corregida).pdf) y la [planificación](https://github.com/javifanelli/GdP/blob/master/charter.pdf).

## Resolución

**Objetivo del ataque:** tomar el control de los sensores y actuadores de temperatura e iluminación (nodo) para cambiar los parámetros de actuación, generando pérdidas materiales en el hardware, tanto en sensores como en actuadores. Esto se haría enviando los comandos de encender y apagar los actuadores repetidas veces sin crear los registros en la base de datos de mediciones ni mostrar los estados en la aplicación web vía MQTT. Por ejemplo, si se enciende y apaga consecutivas veces una calefacción eléctrica, se desgasta y daña prematuramente el actuador (contactos de un relé) y puede dañarse el sistema de calefacción, y el usuario no notaría a simple vista que el actuador está cambiando su estado.

**Supuestos:** el nombre de usuario y contraseña para loguearse al sistema se encuentran en una base de datos sin encriptar. El server tiene el servicio de conexión SSH activado.

### Reconnaissance

Técnicas utilizadas: [T1592](https://attack.mitre.org/techniques/T1592/) y [T1590](https://attack.mitre.org/techniques/T1590/)

  - Reconocimiento de la solución a través de las redes sociales o internet.
  - Análisis de la infraestructura y topología de red y la comunicación interna entre nodos y servidor.
  - Análisis de los tipos de nodos y sensores, en especial los parámetros leídos y modificados.
  - Análisis del modelo de aplicación web para comando de los nodos e información almacenada por el servidor.
  - Análisis de la base de datos almacenada en el servidor.
  
### Weaponization

Técnica utilizada: [T1587](https://attack.mitre.org/techniques/T1587/)

  - Diseño de una página web igual o muy similar para solicitar el cambo de contraseña de logueo al sistema.
  - Diseño del sistema de mensajes entre servidor y nodos replicando al original.
  
### Delivery

Técnica utilizada: [T1566](https://attack.mitre.org/techniques/T1566/)

  - Envío de mail al usuario solicitando cambio de usuario y contraseña o las credenciales importantes para tener acceso al servidor.
  
### Exploit

Técnica utilizada: [T1021](https://attack.mitre.org/techniques/T1021/)

  - Acceso remoto al servidor vía SSH con las credenciales enviadas por el usuario.
  - Recolección de toda la información de la red del usuario y de la solución en particular.
  - Recolección de certificados utilizados en el protocolo MQTT para el envío de mensajes.
  
### Installation

Técnica utilizada: [T1543](https://attack.mitre.org/techniques/T1543/)

  - Instalación de malware de forma remota que permita tomar el control del envío de mensajes.

### Command & Control

Técnica utilizada: []()

  - 
  
### Actions on Objectives

Técnica utilizada: [T1059](https://attack.mitre.org/techniques/T1059/)

  - 


#### Enlaces:

https://attack.mitre.org/

https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html