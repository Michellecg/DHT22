# Practica ESP32 con DHT22
En este repositorio se muestra una práctica utilizando la página Wokwi para la simulación del sensor DHT22.

## Introducción

### Descripción

La ```Esp32``` la utilizamos en un entorno de adquision de datos, lo cual en esta practica ocuparemos un sensor (```DTH22```) para adquirir temperatura y humedad del entorno; Cabe aclarar que esta practica se usara un simulador llamado [ SIMULADOR WOKWI](https://https://wokwi.com/).


## Material Necesario

Para realizar esta practica necesitas lo siguiente

- [SIMULADOR WOKWI](https://wokwi.com/)
- Tarjeta ESP32
- Sensor DHT22




## Instrucciones

### Requisitos previos

Para poder usar este repositorio necesitas entrar a la plataforma [WOKWI](https://wokwi.com/).


### Instrucciones de preparación de entorno 

1. Al ingresar a la página de [WOKWI](https://wokwi.com/) se selecciona la tarjeta ESP32.

2. Una vez seleccionado la tarjeta ```Esp32```, en la parte izquierda se encuentra la pestaña de código donde se agrega lo siguiente:

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
3. Instalar la libreria de **DHT sensor library for ESPx** como se muestra en la siguente imagen.

![](https://github.com/Michellecg/DHT22/blob/main/Lib_wokwi.PNG)

4. Hacer la conexión de **DHT22** con la **ESP32** como se muestra en la siguente imagen.

![](https://github.com/Michellecg/DHT22/blob/main/Conex_Sim.PNG)

### Instrucciónes de operación

1. Iniciar simulador.
2. Visualizar los datos en el monitor serial.
3. Modificar la temperatura y humedad dando *doble click* al sensor **DHT11** 

## Resultados

Una vez compilado el programa y que no se hayan presentado errores, se podrán observar los datos del sensor tal como se muestra en la siguente imagen.

![](https://github.com/Michellecg/DHT22/blob/main/Sim_wokwi.PNG)


# Créditos

Desarrollado por Michelle Cuatlapantzi González

- [GitHub](https://github.com/Michellecg/)