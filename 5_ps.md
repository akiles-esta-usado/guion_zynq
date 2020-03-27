# PS



# Guión Antiguo

## El procesador
Tomas:
	Cuando hablamos del procesador, no solo nos referimos a la hermosa pieza de ingeniería que es el Cortex A9 de ARM,
	sino que al conjunto de elementos que permiten que funcione de forma eficiente, es decir, los coprocesadores NEON, la
	caché L1 y la unidad de manejo de memoria MMU

	Tambien hay que mencionar que tiene varias interfaces para comunicarse con los otros elementos del sistema

### Procesador

Tomas:
	El procesador de la zynq es un ARM Cortex A9, puede tener 1 o 2 núcleos,

	Cada CPU implementa una arquitectura ARM v7-A, es decir, el procesador esta destinado a trabajar con aplicaciones.
	Tienen soporte de memoria virtual y la microarquitectura utiliza Pipeline.

	Pueden ejecutar 3 conjuntos de instrucciones
	- ARM de 32 bits
		Tiene instrucciones de procesamiento y control de datos.
	- Thumb de 16 y 32 bits
		esta diseñado para reducir la densidad de código y mejorar la eficiencia de ejecución, puede usarse en conjunto con
		el set ARM, y entre instrucciones de 16 y 32 bits
	-
	- bytecode de java de 8 bits al trabajar en el estado Jazelle

	Cada nucleo tiene para si 2 memorias caché L1 de 32 KB, una para instrucciones y otra para los datos.

### VFU

Tomas:
	Hay una unidad de punto flotante llamada FPU, que trabaja con flotantes simples y flotantes de doble presición



### Coprocesadores NEON

Akiles:
	Los coprocesadores NEON extienden la funcionalidad de los nucleos al proveer el soporte para el conjunto de
	instrucciones VFPv3, que están dedicadas al procesamiento de vectores de números flotantes mediante el uso de
	instrucciones Single Instruction Multiple Data o SIMD.

	Esas instrucciones permiten realizar cómputos sobre varios tipos de datos, como flotantes single-presicion y enteros de
	distinto tamaño, con o sin signo, e inclusive con formatos de video e imágen, como MP4.

	Son eficientes en comparación a la CPU en las siguientes areas:
	- el cálculo de transformada rápida de fourier
	- multiplicación de matrices
	- Gráficos 2D y 3D, manipulación de imágenes
	- Simulaciones físicas

### "Conclusión" de procesador
Tomas:
	Es interesante ver que la microarquitectura de este procesador implementa varios conceptos avanzados, como
	- una unidad de predicción de branches estática y dinámica, lo que permite la ejecución especulativa y reducir los
	  Stalls.
	- Decodificadores superescalares,
	- La presencia de unidades con arquitectura SIMD, como es el caso de NEON
	- Y que varias etapas utilizan el paradigma de ejecución fuera de orden, como es el caso del Write-Back



Tomas:
	Ahora que revisamos los elementos que procesan datos en el lado del PS, revisemos un poco la PL, y veamos su posibles
	aplicaciones


### Snoop Control Unit SCU
El Snoop Control Unit es la encargada de mantener la coherencia entre las memorias L1 y L2

### Memoria L2
Es una memoria compartida de 512KB, almacena instrucciones y datos

### Memoria OCM
memoria de baja latencia que provee de 256KB
8-way set-assosiative
permite bloquear su contenido en una 'line, way, master basis'
