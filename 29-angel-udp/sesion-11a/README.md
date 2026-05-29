# sesion-11a

26-05-2026

## apuntes

Investigamos y avanzamos por cuenta propia sobre chips, y el 4015 fue el que decidimos desarrollar.

Por cuenta propia, desarrollé una simulación del chip 74HC595.

![imagen 1](./imagenes/avance.png)

## Cuales son los parametros del curso

Estamos construyendo un sistema para que nuestros proyectos se interconecten con los de otros grupos.

Sitio web ModularGrid: da un contexto de cuánta gente está trabajando en este rubro.

Vamos a configurar algunos parámetros para que después podamos movernos teniendo eso en cuenta.

Hay que fijarnos en la configuración y también en el Barrel Switch.

Al Audio Jack Switch hay que editarle los nombres por los números 1, 2 y 3, de arriba hacia abajo.

Tamaño máximo de la placa: 10 x 10.

---

Tarea de grupo:

Investigar sobre el funcionamiento del chip 4015 (cómo funciona, con qué no funciona y qué pines son necesarios).

## Cip 4015

El 4015 tiene dos registros de desplazamiento de 4 etapas independientes dentro del mismo chip, cada vez que recibe un pulso en el pin de reloj (clock), el dato de entrada avanza una posición.

Esto permite crear secuencias, encender leds en orden, generar patrones y trabajar en secuenciadores

**Funciones o limitaciones**

- No funciona correctamente sin alimentación eléctrica.
- No debe recibir voltajes mayores al permitido.
- Puede fallar con señales de reloj inestables o ruido eléctrico.
- Sus salidas entregan poca corriente, por lo que normalmente se usan transistores si se quiere controlar algo más potente.
- Es un chip CMOS, por lo que puede dañarse con electricidad estática.

![imagen 2](./imagenes/chip4015.jpg)

- Vcc: alimentación positiva.
- Gnd: tierra.
- Clock: entrada de reloj.
- Data Input: entrada de datos.
- Outputs (Q): salidas de cada etapa.

**Alimentación**

El 4015 puede funcionar aproximadamente entre: 3v y 15v

## Funcionamiento como secuenciador

El chip recibe una señal de datos y una señal del clock. Cada vez que llega un pulso del clock el dato se desplaza una posición interna.

Como secuenciador al conectarle LEDs a las salidas la señal avanzará paso a paso con cada pulso, por ejemplo:

- Pulso 1 salida Q1
- Pulso 2 salida Q2
- Pulso 3 salida Q3
- Pulso 4 salida Q4

### Alimentación

- Pin: 16 VDD
- Pin: 8 GND

### Primer registro de 4 etapas

- Pin 1 Clock
- Pin 7 Data Input

### Salidas

- Pin 2 Q1
- Pin 3 Q2
- Pin 4 Q3
- Pin 5 Q4

## Segundo registro de 4 etapas

### Entradas

- Pin 9 Clock
- Pin 15 Data Input

### Salidas

- Pin 10 Q1
- Pin 11 Q2
- Pin 12 Q3
- Pin 13 Q4
