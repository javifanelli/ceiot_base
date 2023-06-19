# Ejercicio CiberKillChain - Ataque

Se realizó una copia del documento original utilizándolo como plantilla para la realización del ejercicio, quitando las instrucciones y el ejemplo.

## Alumno

Ing. César Javier Fanelli - Especialización en Internet de las Cosas.

## Enunciado

Armar una cyberkillchain usando técnicas de la matriz de Att&ck para un escenario relacionado al trabajo práctico de la carrera.
  
## Datos trabajo práctico

En el siguiente [link](https://github.com/javifanelli/GdP) se encuentra el repositorio con la planificación del proyecto final hecha en la materia Gestión de Proyectos.

### Descripción

El trabajo práctico final de la carrera consta de un sistema de control de ambientes a distancia. Se pretende controlar la temperatura mediante calefacción y la iluminación de una habitación o recinto dentro de una casa, lo que sería un principio de domótica. El nodo de control estará implementado con un ESP32 y reportará y recibirá los datos de un servidor alojado en una Raspberry Pi de forma local dentro de la casa. Dicho servidor alojará el frontend y el backend, y tendrá una interfaz web con logueo de usuarios para poder ver y cambiar los parámetros del nodo. La comunicación entre las partes se hará por MQTT y en el servidor se alojarán los valores de las mediciones en una base de datos.

Para mayor información, por favor dirigirse a la [planificación del proyecto](https://github.com/javifanelli/GdP/blob/master/charter.pdf) donde se encuentra información detallada. Se recomienda leer también la [propuesta de proyecto](https://github.com/javifanelli/GdP/blob/master/Propuesta%20de%20proyecto%20(corregida).pdf).

## Resolución

**Objetivo del ataque:** tomar el control de los sensores y actuadores de temperatura e iluminación (nodo) para cambiar los parámetros de actuación, generando pérdidas materiales en el hardware, tanto en sensores como en actuadores y falta de credibilidad de los usuarios en la solución. Esto se haría enviando los comandos de encender y apagar los actuadores repetidas veces sin crear los registros en la base de datos de mediciones ni mostrar los estados en la aplicación web vía MQTT. Por ejemplo, si se enciende y apaga consecutivas veces una calefacción eléctrica, se desgasta y daña prematuramente el actuador (contactos de un relé) y puede dañarse el sistema de calefacción. De esta forma, los usuarios de la solución comenzarían a volcarse por la competencia. Dato a tener en cuenta, el servidor de la solución está alojado en las instalaciones de cada cliente en una Raspberry Pi, con un SO Linux.

**Supuestos:** el nombre de usuario y contraseña para loguearse al sistema se encuentran en una base de datos sin encriptar. El servidor tiene el servicio de conexión SSH activado.

### Reconnaissance

Técnicas utilizadas: [T1592](https://attack.mitre.org/techniques/T1592/)

  - Reconocimiento de la solución a través de las redes sociales y página oficial de la empresa creadora.
  - Análisis y relevamiento del modelo de aplicación web obtenido de la página oficial de la empresa.
  - Listado de los grandes clientes obtenido de la página de la empresa.
  
### Weaponization

Técnica utilizada: [T1587](https://attack.mitre.org/techniques/T1587/)

  - Diseño de una página web igual a la original para solicitar el cambo de contraseña de logueo al sistema.
  - Diseño de un correo electrónico igual al que enviaría el sistema requiriendo un cambio de contraseña con un link a la página creada en el punto anterior de la Weaponization.
  - Diseño de malware de que permita el envío de mensajes del servidor a los dispositivos.
  
### Delivery

Técnica utilizada: [T1566](https://attack.mitre.org/techniques/T1566/)

  - Selección de un cliente para ser atacado.
  - Envío de mail al usuario solicitando cambio de usuario y contraseña o las credenciales importantes para tener acceso al servidor.
  
### Exploit

Técnica utilizada: [T1021](https://attack.mitre.org/techniques/T1021/)

  - Acceso remoto al servidor vía SSH con las credenciales enviadas por el usuario.
  
### Installation

Técnica utilizada: [T1219](https://attack.mitre.org/techniques/T1219/)

  - Verificación de no detección por parte de ninguno de los componentes del sistema.
  - Recolección de certificados utilizados en el protocolo MQTT para el envío de mensajes.

### Command & Control

Técnica utilizada: [T1543](https://attack.mitre.org/techniques/T1543/)

  - Instalación de malware de forma remota que permita tomar el control del envío de mensajes.
  - Corroboración del funcionamiento del software instalado.
  
### Actions on Objectives

Técnica utilizada: [T1569](https://attack.mitre.org/techniques/T1569/)

  - Configuración y ejecución del malware, que consta de envíos de cambio de estado a las salidas.
  - Corroboración de persistencia del malware en el sistema, y que el propio sistema o usuario no noficó el mal funcionamiento del mismo.


#### Enlaces:

https://attack.mitre.org/

https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html