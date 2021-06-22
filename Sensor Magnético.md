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
A0 |	40
G	| GND
" +	"| 5V
D0 | D0

![Diagrama](https://github.com/GenaroGonzalezz/Modulo-sensor-KY-025/blob/main/Diagrama025.png)

## Imagen 1
<p>
A continuación se puede observar el circuito completo en el cual se encuentra conectado el módulo al Arduino, así como también se aprecia el imán que será utilizado para llevar a cabo las pruebas.
</p>

![Pruebas1](https://github.com/GenaroGonzalezz/Modulo-sensor-KY-025/blob/main/200281094_4189357484453623_5645018992284595790_n.jpg)

## Imagen 2

![Pruebas2](https://github.com/GenaroGonzalezz/Modulo-sensor-KY-025/blob/main/200087686_160587269438462_2896078833731179641_n.jpg)

## Imagen 3
<p>
En la siguiente imagen es posible observar el cambio de estado del módulo durante su interacción con el imán.
</p>

![Pruebas3](https://github.com/GenaroGonzalezz/Modulo-sensor-KY-025/blob/main/202780707_242333810600301_9135937306506871131_n.jpg)

## Código
```
//========================LIBRERIAS==================
#include "Arduino.h"
#include <LiquidCrystal.h>
#include <Servo.h>

//================sensores======================
int sensor = 40;
int lectura;
//========================LCD config====================================

LiquidCrystal lcd(8, 9, 4, 5, 6, 7);

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  lcd.begin(16,2);
  pinMode(sensor,INPUT);
  
}

void loop() {
  

  lectura = digitalRead(sensor);
  Serial.println(lectura);

  if (lectura == LOW)
    {
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("Magnetismo:");
    lcd.setCursor(1,1);
    lcd.print("Detectado");
    }
   else
  {
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("Magnetismo:");
    lcd.setCursor(1,1);
    lcd.print("No detectado");
    }
  
  delay(200);
}
```
