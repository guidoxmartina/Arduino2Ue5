# Arduino2Ue5

Conectar Arduino a la Pc

Usando "arduino ch340g"

Descargar e Instalar
-drivers de la placa
-Arduino IDE

-Conectar por Usb
- Dentro del software en la pestaña herramientas seleccionar el numero de "puerto COM"
-Test con un pulsador  (Tutorial https://youtu.be/nmul0-Z9lks)

Materiales necesarios

-Una placa Arduino (Cualquier versión sirve)
-Un botón (A elección tuya)
-Una resistencia de 10K Ohm

El esquema quedara de la siguiente forma:

![image](https://user-images.githubusercontent.com/48781895/185523297-5168ba74-4838-44fe-8f99-e5cc7bb339ad.png)

El terminal A1 lo conectaremos a unos de los pines GND de la tarjeta Arduino.

El terminal A2 lo conectaremos al pin que queramos configurar con entrada en Arduino, al pin que conectarías normalmente el botón.

El terminal A3 lo conectaremos al pin (+5V) de tu tarjeta Arduino.

Y listo, ya tendríamos por completo el apartado hardware que usaremos para controlar el pin o las funciones del Arduino con el botón.


Usaremos el siguiente codigo

```
#define Pulsador 2
#define Led 13

int inicio = 0;
int estadoAC = 0;
int estadoAn = 0;

void setup() {
    pinMode (Pulsador, INPUT);
    pinMode (Led, OUTPUT);
}

void loop () {
  estadoAC = digitalRead (Pulsador);
  if (estadoAC && estadoAn == 0) {
    inicio = 1 - inicio;
    delay (500);
  }
  estadoAn = estadoAC; 

  if(inicio==1)
  digitalWrite (Led, HIGH);
  else
  digitalWrite(Led, LOW);
```


# Unreal Engine 5<br>
![image](https://user-images.githubusercontent.com/48781895/185524034-46988ddb-c8cb-4fa1-a9b4-53038f8c4278.png)

https://www.youtube.com/watch?v=ElM9EQVjR-8<br>
https://github.com/videofeedback/Unreal_Engine_SerialCOM_Plugin
