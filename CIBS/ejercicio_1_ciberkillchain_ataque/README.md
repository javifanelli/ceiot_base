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

**Objetivo del ataque:** tomar el control del sensor y actuador de temperatura e iluminación (nodo) para cambiar los parámetros de actuación, generando molestias en los usuarios y pudiendo generar pérdidas materiales en el hardware y sensores o actuadores. Esto se haría obteniendo los datos de logueo de usuario con permisos para cambiar los parámetros de control del sistema.

### Reconnaissance

Técnicas utilizadas: [T1592](https://attack.mitre.org/techniques/T1592/) y [T1590](https://attack.mitre.org/techniques/T1590/)

  - Reconocimiento de la solución a través de las redes sociales o internet.
  - Análisis de la infraestructura y topología de red y la comunicación interna entre nodos y servidor.
  - Análisis de los tipos de nodos y sensores, en especial los parámetros leídos y modificados.
  - Análisis del modelo de aplicación web para comando de los nodos e información almacenada por el servidor.
  
### Weaponization

Técnica utilizada: []()

  - 
  
### Delivery

Técnica utilizada: []()

  - 
  
### Exploit

Técnica utilizada: []()

  - 
  
### Installation

Técnica utilizada: []()

  - 

### Command & Control

Técnica utilizada: []()

  - 
  
### Actions on Objectives

Técnica utilizada: []()

  - 


#### Enlaces:

https://attack.mitre.org/techniques/T1590/
https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html