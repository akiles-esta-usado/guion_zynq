# AXI

## El problema de la conectividad

La ZYNQ contiene varios módulos que tienen una función específica en el PS y da la facilidad de implementar más en la PL,
pero eso no basta para crear un sistema embebido funcional

¿Cómo se hace para que estos módulos se puedan comunicar entre sí?

## Qué es AXI

AXI es la respuesta dada por ARM a ese problema.

AXI es el acrónimo de Advance eXtensible Interface y se define dentro del estandar AMBA.

especifica un estándar de comunicación entre elementos de un sistema SoC.

Con AXI se pueden definir 2 tipos de interfaces, pero antes de hablar de ello es necesario definir algunos conceptos.

## Conceptos (La imágen puede ser esa donde aparecen un esclavo, un maestro y una linea entre ellos)

### Transacción, Maestro y Esclavo

* Solo se necesita el diagrama básico de esto

una transacción es el proceso por el cual los datos son movidos entre los módulos y puede ser para la lectura o escritura de
datos.

En una transacción existen 2 tipos de participantes. El módulo que inicia las transacciones es llamado Maestro, y el módulo objetivo y quien genera la respuesta se denomina Esclavo. dos módulos conectados con una interfaz AXI siempre mantendrán su relación de Maestro esclavo

Un ejemplo sencillo, la CPU es el maestro y un bloque de memoria es el esclavo.
La CPU puede iniciar transacciones de lectura y escritura, y la memoria realiza la operación y responde.

### Tipos de interfaz



### AXI en la ZYNQ

* Mostramos el diagrama de arquitectura ZYNQ

Estos conceptos estan implementados en la ZYNQ, existen 4 grupos de interfaces entre PS y PL

En AXI existen 2 tipos de interfaces, la Memory Mapped o MM y la Stream o S

## Interfaz Memory Mapped o MM

* Pasos de una transacción
* Canales de una interfaz MM

## Interfaz AXI Stream



# Guión Antiguo


## Señales del canal WRITE DATA
Cuando se requiere leer datos, el maestro envia una señal de control junto a la direccion de los datos que quiere leer.

Entonces el módulo esclavo entregará los datos requeridos.

Si se desea escribir en el esclavo, se debe enviar la direccion donde se desea escribir seguido de los datos, finalmente

el esclavo indicará al maestro si la operación fué un éxito o un fracaso.

* INFORMACIÓN ANTIGUA

### AXI Interconnect
El bloque AXI Interconnect es un bloque esencial para el subsistema de comunicación, aquí se crean configuraciones

extensibles entre varios maestros y esclavos, y se asigna una dirección a cada integrante para que así un maestro pueda

comunicarse con un esclavo independiente de su ubicación en la red.

Interconnect puede tener hasta 20 maestros y 20 esclavos, y puede comunicar canales de distinto ancho entre ellos. Tambien

mantiene compatibilidad entre versiones, el PS suele trabajar con AXI3 y el PL con AXI4, sin embargo no hay

problemas de comunicación entre ellos.


## Componentes de AXI Interconnect

El primer elemento es un register Slices, estos son registros que son utilizados para crear retardo en la señal en caso de ser necesario

luego tenemos el UpSiser, que toma un canal de un ancho y lo convierten a otro más grande

A continuación esta un Clock Converter, que permite transferir datos entre 2 canales que trabajan a distinta frecuencia

Luego hay un DownSizer que permite la comunicación hacia un esclavo con un ancho de canal menor

El Data FIFO permite almacenar en una cola los datos que ingresen en caso de recibir más datos de los que se pueden ingresar
en un instante de tiempo

Finalmente el Crossbar permite una comunicación cruzzada entre maestros y esclavos.


Por último pueden encadenar varios AXI Interconnect entre si para superar el límite de 20 esclavos a los que un maestro pudiera comunicarse