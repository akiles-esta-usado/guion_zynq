# Programmable Logic


# Guión Antiguo
Tomas:
	La principal funcion de la lógica programable es la implementación de aceleradores de hardware, que pueden ser diseñados
	por los desarrolladores o adquiridos de terceros, son llamados Intellectual Property Blocks o Bloques IP.

	En una zynq, siempre es el PS quien se energiza primero, por lo que el uso de la PL esta a merced del software.

	Tanto así, que puede ser configurada durante el proceso de booteo o en algun momento posterior, puede también ser
	reconfigurada múltiples veces completa o parcialmente, esto último se conoce como PR. Lo que permite tratar los Bloques
	IP como si fueran módulos o bibliotecas en software, no se ustedes, pero para mi esto es una locura. Los datos de
	configuración de la PL son conocidos como bitstream

	El software puede apagar totalmente la PL para poder ahorrar energía, aunque debe ser reconfigurada luego de de reactivarla.
