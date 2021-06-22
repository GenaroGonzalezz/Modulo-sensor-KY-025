# MÓDULO DE INTERRUPTOR DE LÁMINAS KY-025

## Descripción General
<p> 
El módulo de interruptor de láminas KY-025 para Arduino es un pequeño interruptor eléctrico operado por un campo magnético aplicado, comúnmente utilizado como sensor de proximidad.

El módulo tiene salidas digitales y analógicas. Se utiliza un recortador para calibrar la sensibilidad del sensor.
</p>
<div style="text-align:right"><img src="https://arduinomodules.info/wp-content/uploads/KY-025_Reed_switch_module_arduino-240x240.jpg" /></div>

## Especificaciones
<p>
  El módulo KY-025 consta de un interruptor de lengüeta normalmente abierto de 2x14 mm , un comparador diferencial dual LM393, un potenciómetro trimmer 3296W-104, seis resistencias y dos LED. La placa tiene una salida analógica y una digital.
</p>

Tensión de funcionamiento | Dimensiones de la placa
----------------|--------------------------------
3,3 V a 5,5 V | 1,5 cm x 3,6 cm [0,6 pulgadas x 1,4 pulgadas]

## Desarrollo de la práctica
<p>
Se llevó a cabo la conexión del sensor Reed Switch en conjunto con un display LCD de manera que se pueda conocer el estado actual del componente al interactuar con un elemento que posea propiedades magnéticas, interactuando así con el circuito y alterando su comportamiento el cual se presenta en pantalla por medio de un mensaje de cambios.
</p>
 
 ### Diagrama de conexión
 
KY-025	| Arduino
--------|-------
A0 |	A0
G	| GND
" +	"| 5V
D0 | 3

