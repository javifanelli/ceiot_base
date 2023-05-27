# Ejercicio CiberKillChain - Ataque

Se realizó una copia del documento original utilizándolo como plantilla para la realización del ejercicio, quitando las instrucciones y el ejemplo.

## Alumno

César Javier Fanelli

## Enunciado

Armar una cyberkillchain usando técnicas de la matriz de Att&ck para un escenario relacionado al trabajo práctico de la carrera.
  
## Datos trabajo práctico

En el siguiente [link](https://github.com/javifanelli/GdP) se encuentra la planificación del proyecto final hecha en la materia Gestión de Proyectos.

### Descripción

El trabajo práctico final de la carrera consta de un sistema de control de ambientes a distancia. Se pretende controlar la temperatura mediante calefacción y la iluminación de una habitación o recinto dentro de una casa, lo que sería un principio de domótica. El nodo de control estará implementado con un ESP32 y reportará y recibirá los datos de un servidor alojado en una Raspberry Pi de forma local. Dicho servidor alojará el frontend y el backend, y tendrá una interfaz web con logueo de usuarios para poder ver y cambiar los parámetros del nodo. La comunicación entre las partes se hará por MQTT.
Para mayor información, por favor dirigirse a la [planificación del proyecto](https://github.com/javifanelli/GdP) donde se encuentra información detallada.

## Resolución

<u>Objetivo del ataque:</u> tomar el control del sensor y actuador de temperatura e iluminación (nodo) para cambiar los parámetros de actuación, generando molestias y pudiendo generar pérdidas materiales en el hardware y sistema de calefacción.
  
* Reconnaissance
  - Imagen satelital identifica una pista de aterrizaje.
  - Espías dicen que por el puerto entra el combustible.
  - Espías locales dicen que la playa cercana no tiene buena vigilancia.

* Weaponization
  - Puedo preparar un bombardeo.
  - Decido preparar un equipo de comandos de sabotage.
  
* Delivery
  - Envío al equipo de sabotage a la playa cercana en submarino.
  
* Exploit
  - El equipo logra desembarcar sin incidentes en la playa.
  
* Installation  
  - El equipo se hace pasar por una compañia de circo como camuflaje.

* Command & Control
  - Podría utilizar palomas mensajeras.
  - Decido utilizar Super High TeraHertz Radio que el adversario no puede detectar.
  
* Actions on Objectives
  - El equipo de comandos provoca daños menores en las cañerías.
  - El equipo de comandos coloca minas en el puerto dejando un camino para el desembarco.