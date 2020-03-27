# Resumen de Arquitectura ZYNQ


# Guión Antiguo

Tomas:
	La arquitectura de los Zynq define 2 bloques principales
	- una parte dedicada al procesamiento de aplicaciones de software llamada Processing System, el PS
	- y otra que contiene lógica programable, útil para tareas que se pueden realizar en paralelo. esta se conoce como
	  Programmable Logic, o PL

Akiles:
	Usualmente cuando se trabaja con una zynq, el desarrollo del sistema que correrá en la placa se puede ver de la
	siguiente forma:

	* Primero se define la aplicación que dara solución al problema, esto se implementará en el PS, que es la parte que puede
	  interpretar los datos, tomar decisiones, controlar su flujo con condicionales, ciclos y todas esas cosas de la
	  programación usual. Incluso puede ponerse un sistema operativo.

	* Despues hay que revisar la idea de aplicación y encontrar ciertas etapas que puedan ser aceleradas con hardware, como por
	  ejemplo, el procesamiento de video en programas de visión por computador, entrenamiento de las redes neuronales en
	  aplicaciones de inteligencia artificial. Y los dispositivos que aceleran esas etapas pueden implementarse en la PL,
	  que es una FPGA.

	(..) Lo realmente importante es el eficiente subsistema de comunicación entre estos dispositivos, que se logra gracias
	al sistema de interconección y la interfaz AXI

Tomas:
	Y bueno, ahora comenzará la parte pesada del video, asi que preparense un café que vamos a ponernos densos...
