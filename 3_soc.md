# SoC




# Guión antiguo

Tomas:
	En los inicios de la electrónica, los desarrolladores de sistemas tenian que
	juntar un montón de componentes discretos en placas impresas. Pero esto traia varios problemas para ellos, como
	* El uso de espacio
	* consumo de energía
	* y latencia, entre muchos problemas más

Akiles:
	Es entonces que aparece la idea de desarrollar gran parte del sistema dentro de un solo chip. los System on
	Chip o SoC son precisamente esto, sistemas que se implementan dentro de una sola placa de silicio.

	En un comienzo, hubo 2 formas de implementar los SoC:

	La primera era desarrollando circuitos integrados hechos especificamente para solucionar un problema en particular,
	estos son los ASIC. La gran desventaja de estos dispositivos es el costo de desarrollo y lo poco flexibles que son,
	provocando que un pequeño cambio requiera mucho trabajo y tiempo.

	otra forma es ocupando unos dispositivos llamados FPGA, que son matrices de compuertas lógicas que pueden
	configurarse para realizar cualquier tarea digital. la desventaja es que no son buenos para tareas que requieran
	tomar desciciones a partir de los datos, como si lo es un procesador. y si bien se puede usar para implementar uno, lo que
	se conoce como soft-processor, suelen ser lentos y ocupan bastantes recursos de la placa.


Tomas:
	Es entonces que aparece una solución tecnológica con el rendimiento de un ASIC, y la flexibilidad de una FPGA.
	La familia Zynq de Xilinx, que aparece bajo el nombre de All Programmable System on Chip.

