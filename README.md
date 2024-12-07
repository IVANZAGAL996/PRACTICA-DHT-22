# PRACTICA-DHT-22
07/12/2024

# INTRODUCCION
La Esp32 la utilizamos en un entorno de adquision de datos,  ocuparemos un sensor (DTH 22) para adquirir temperatura y humedad del entorno; eN esta practica se usara un simulador llamado WOKWI.

## Para desarrollar esta practica, necesitaremos lo siguiente:
- Simulador WOKWI
- Tarjeta ESP 32
- Sensor DHT22

## Paso 1
ir al siguiente link
https://wokwi.com/

A continuacon seleccionamos lo siguiente:
![](https://github.com/IVANZAGAL996/PRACTICA-DHT-22/blob/main/Captura%20de%20pantalla%20(334).png)
![](https://github.com/IVANZAGAL996/PRACTICA-DHT-22/blob/main/Captura%20de%20pantalla%20(335).png)

Aparecera la siguiente interfaz:

![](https://github.com/IVANZAGAL996/PRACTICA-DHT-22/blob/main/Captura%20de%20pantalla%20(336).png)
Borraremos el codigo que viene por defecto y realizaremos el siguiente codigo:
```
#include "DHTesp.h"
#include <LiquidCrystal_I2C.h>

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}

 ```
CARGAMOS LA LIBRERIA DTH

![]()
INSERTAMOS EL DH22

![]()

REALIZAMOS LA SIGUIENTE CONEXION

![](https://github.com/IVANZAGAL996/PRACTICA-DHT-22/blob/main/Captura%20de%20pantalla%20(339).png)
