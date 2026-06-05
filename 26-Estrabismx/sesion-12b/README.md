# sesion-12b


## BACKUP

<details>
<summary> Código de texto </summary>

```text

# proyecto-02

## Grupo

Número de grupo: 02

Tema del grupo: Secuenciador 

Integrantes:

- Isidora Alvarez / 
- Dayana Pañitrur / dayanapanitrur
- Camila Ramirez / Estrabismx
- Angel Sabogal / angel-udp
- Tomas Catrileo / tomascatri
  
## Circuito 1: Contador binario

### Descripción general/conceptual 1

Este circuito es un compás, es decir que le da ritmo a lo que pueda sonar, ya que esté no define ninguna nota, simplemente el ritmo y en este caso uno donde tenemos 6 compases, cada uno a un ritmo diferente

Es bastante autónomo, solamente debes indicarle que _partitura_ va a interpretar cada compás y solito hará su trabajo

<br>

### Descripción de funcionamiento 1

Ahora se van a definir algunos conceptos claves:

Podemos categorizarlo como un secuenciador, es decir que genera corrientes eléctricas en un patrón repetitivo y ordenado. Un ejemplo de esto es un semáforo, ya que se va a prender siempre en el mismo orden:

_VERDE > AMARILLO > ROJO > VERDE > AMARILLO > ROJO > ..._

![Semáforo](./imagenes/semaforov2.gif)

<br>

Ya definimos que este sistema es un secuenciador, pero algo importante es como está configurada la duración de cada _activación_. Tal como en los semáforos no todos los colores duran lo mismo, en este circuito cada _señal_ tiene una duración única. ¿A que se refiere "duración unica"? En que cada _señal_ está asociada a un número, desde el 0 al 12 y mientras menor sea el número asociado, más rapido se va a _activar_. A continuación se puede observar una representación de este patrón

![Secuencia](./imagenes/11.png)

> De izquierda a derecha: Avance del tiempo
>
> De arriba a abajo: Q1, Q2, Q3, Q4 y Q5 = Canales

<br>

Esta es una secuencia binaria y de las cosas más notorias es que cada _canal_ tiene la misma duración prendido y apagado, es decir, el Q3 funciona con 4 _señales apagadas_ y 4 _señales prendidas_. Otro punto interesante es como esta duración tambien sigue un patrón

| Canal / Step | Duración   |
| ------------ | ---------- |
| Q1           | 1 tiempo   |
| Q2           | 2 tiempos  |
| Q3           | 4 tiempos  |
| Q4           | 8 tiempos  |
| Q5           | 16 tiempos |

<br>

Ahora que entendemos como funciona su secuencia, vamos a profundizar más en como este circuito logra generar este proceso. Anteriormente se mencionó (y tmabien se ejemplificó en la imagen) que en cada _"tiempo"_ se van _activando_ las señales correspondientes, estos "_tiempos_" son corrientes eléctricas, es decir, que se necesita una señal intermitente y constante para activar el proceso de conteo. Esto es conocido como **reloj** o **clock**, entonces la velocidad con la que alterne este circuito afectará en como nuestro secuenciador realice su conteo.

Para una mayor compresión se utilizará la siguiente analogía: Tenemos una especie de corazón (Reloj) que cada vez que late (emitir un pulso eléctrico) un semáforo prende sus luces (se activan las salidas del secuenciador)

Otro ejemplo que nos puede ayudar a entender como funciona es que cada Q es un corredor en una carrera con saltos.

El corredor del carril Q0 va a correr un metro y debe saltar un metro, luego correr un metro y volver a saltar otro, asi sucesivamente. El del carril Q1 debera correr por 2 metros y sus saltos tambien deberán ser de 2 metros. Quien tenga la mala suerte de correr en el Q2, tendrá que hacerlo por 4 metros y saltar tambien 4 de ellos.

Todos ellos van a iniciar al mismo tiempo, eventualmente veremos que sus saltos se coordinan cada ciertos metros

>Clickear imagen para reproducir video

[![Ejemplo circuito 4040](./imagenes/sc41.png)](https://youtube.com/shorts/x3a4tAwtNEM?feature=share)


#### Explicación más técnica

Ahora con otro tipo de explicación, debemos entender que el cerebro detrás de todo este sistema es un chip CD4040, el cual recibe un **input** intermitente (en nuestro caso de prueba un reloj en base a un CD555 Astable), cada vez que se reciba una señal el contador iniciará. Recordemos que acá no se cuenta con otro número que no sea 0 y 1. Al cambiar el conteo se van a producir 2 cosas importantes:

1. Se prenderá un led corresponiente al conteo

2. Se activará el **output** que corresponda

Por lo que cada vez que se envie una señal en cada paso, se prenderá un respectivo led, ya que todo es más facil de entender cuando vemos (además nos puede ayudar a identificar donde puede haber un problema). El como se prende este led es simple, utilizamos un transistor del tipo NPN, más especificamente un 2N2222, este funciona como un interruptor, cada vez que el IC manda una señal este transistor permite el paso de la corriente del led. Profundizando esto hay que entender que el led está conectado a VCC (con su respectiva resistencia), luego se conecta al colector del 2N2222 y el emisor a Ground, por lo que cuando la base de este reciba señal va a permitir que se cierre el circuito del led. En resumen, este transistor no es más que un switch inteligente.

Algo importante a mencionar es la alimentación de este IC, este recibe 5v gracias al regulador de voltaje (L7805)

### Proceso

Para el proyecto tuvimos diferentes etapas: iniciamos con un proceso de investigación individual para obtener variadas opciones de chips o formas de lograr un secuenciador y compararlas de manera grupal. Viendo entre varias opciones que nos dio internet, existían algunas que nos llamaban más la atención que otras. Como grupo vimos hasta la posibilidad de no usar chip, pero creímos que sería un desafío mucho mayor sin aún comprender muy bien cómo funcionaban los transistores, además de que, si bien pueden lograr hacer cosas similares a los circuitos integrados, ya que estos básicamente están compuestos por una gran cantidad de transistores y muchos componentes más pero de una forma más compacta, podría resultar más inestable, se requeriría un espacio muchísimo mayor para colocar una gran cantidad de componentes y por último y como ya se mencionó, un chip hace lo mismo en un espacio, tiempo y trabajo menor. Después de mucha indecisión y de ver cuál de estas opciones eran viables e interesantes, llegamos a la conclusión de usar los circuitos integrados CD4040 y CD4015, ya que estos nos permiten generar secuencias de manera distinta, igual nos aventuramos en elegir estos chips ya que nunca lo habíamos visto y eran circuitos que encontramos en internet y no sabíamos si lograriamos hacerlo, aceptamos el desafío y fui a san diego por suministros de chips.

Empezamos hacer las primeras pruebas utilizamos el CD555, que se encarga de generar los pulsos que controlan la manera en cómo avanza el secuenciador, durante esta etapa surgieron distintos problemas, tuvimos fallas con conexiones, errores de cableado y componentes defectuosos, íbamos registrando y corrigiendo en el acto para no perdernos, esto nos permitió mejorar el funcionamiento, generar hipótesis de los posibles errores y adelantarnos a posibles fallas.

Con el CD4040 hicimos varias pruebas para ver que funcionara bien el contador binario es decir un contador de pulsos o pasos cada vez que recibe una señal,  permitiendo generar secuencias y patrones de activación, también podemos imaginarlo como si fuera las luces de un árbol de navidad, algunas luces se prenden, otras se apagan y van formando distintos dibujos,  es decir cada vez que el circuito recibe una señal cambia el patrón de luces, creando nuevas combinaciones. Comenzamos utilizando pocas salidas y a medida que veíamos que iba funcionando le íbamos agregando más leds, para poder observar mejor la secuencia que se generaba, tuvimos fallas con la batería, conexiones a negativo (tierra) que no habíamos puesto, se nos quemaron algunos leds para variar. Cuando logramos hacer que todo esté bien conectado y arreglar todos los problemas, logramos que funcionara de manera estable, vimos cómo se comportaba y funcionaba el chip, y como son los pulsos que tiene el chip.
Hicimos pruebas conectando el CD4040 a un amplificador LM386 para ver como se escuchaba los pulsos que obtuvimos, aunque el resultado no nos pareció muy bien osea funcionaba correctamente pero el sonido era raro, nos hizo sentir bien el haber logrado que el secuenciador funciona y qué se diferencian los pasos, el tema del sonido se solucionara cuando lo conectemos con los osciladores correspondientes.

Una vez entendimos que funcionaba bien pasamos a instalar transistores, no solo por temas esteticos, sino por funcionalidad. Para lograr esto analizamos como lo hizo el grupo de Luisa Toro en el proyecto anterior, además de buscar como funcionan los transistores, luego de mucha busqueda se proboó su funcionamiento en Falstad


![Captura de Pantalla](./imagenes/sc39.png)

- Abajo se puede apreciar el gráfico que relaciona el periodo de _"activación"_ de cada led

[Circuito Falstad](https://www.falstad.com/circuit/circuitjs.html?ctz=DwYwlgTgBAZgvAIgKwKgFwM6IAwDpsEEpRgiICMSuALAOwBMtAbLQJy3nkAcT52rqEACNESAVAAOIhNQDMqAG4RRqALaZRAUwC0nBAD4AUFCig00AB6J6SJlCbUojeveqp4CbKiFgK9VAAWCojiYAB2iDAAhgA2GJpqAPY4irIhirTpUAqsWQp8eZyF9IVpCAIA9EYmwADmUFYI2qx29FxcUM12sthusClVxqYA7g2I2vTYHfT0jrqsLjN9Hl6DNaONE7ZOs52T07PuA9UjY037rntTO8vHQ8CW4+R2DlcdDkeeqMoIfIQIa1Om2eUHIC06II+-S+gOAGyedjBLm0ryRn1WJzhZxRjhanVRTC80Ix93hTXIbSgeJxVKY6IBmIAKmBVJpHuTwRSOrpmKC2p86dkkDh8EQkPwxEhGLIuKwuLJyAz7gB5M542bYUGEpzUIkrVAYMgwzEAJWxNjs1LaHRa9Kgw31UFUUQswV+JPW5u21K5tPpsPZW1auyDfuJ3wohH+sPqmwtUFkkz221kskF+thIC9rW2ocTepSUCNsh0tFQYDdeAIiqgGB+RIUABNRLgkHxyNQmPRU9QbGXYWTQ-H5otbP7MYP40tkzn03cahBByCkTrNVwC199LomAAaJEAbg1e4Wh91O-XwAqi8xi7OGqg66c2yh+v0R-Xp+wO4ch9s3+ol7Xvct6NAwmrUI+8bUM89L6GBO4Qdgv67ohyEIc8gHDJiAAyACiAAiZyyFKCYkYhpH+OGTrJAgjaaNEACuMRoNoMSaI2gg-DWIC1IWwiFqoQhGlWiqwnhhGNMRLgyo45EyXaqg0XRjHMax7GcRQgi8V8RbSESgnCfgok4QRRFkSC5HQXOOmKYgylRExLFsRxRZcVpfF6WoQkitgxnAWclkgrY4EwVRXHRjeAWPjJUDBQmXC3Dp4UEEqC5RZqUmxdqUl2slHqmLGojalZ9jXHIlEZpihXINlCWlR0uobvldRnHFmWEh0aZcOO9zVW1SYdQmaY9WljRyUm-VNRG7opWJpmSSR+ZQONU3UXZ9EOapzkab87k6fxNneZ4RmpaYIGIO1jhgct66wVJ-77vBP7wYhmEmRJF0kdaN2ataClKRtjlqS5IBuUW2lEgd+lHSJp3AOJZmjnY5EWv960qU56muZp4MeQJMMnXNH0IJl04o4cVG2bRgNbVjoM4zxeOHYZvlwwjC0uCu5FopTAMY8DO3cRDgieU6BOs0TiNauBj7PKtVP2UD23Y7tuP7aLBk+X5NTs59nOUtz-K8+jm2YyDYOM+r+Ms9rpi6yTJF4uRtrG9T-PK-TquW5DGvi7bDzpU47RZb97S5ZGs2RWNkHbHFqNhRHzXsuTjhxxTjp5XDyey+CcU8xnidZ4Hcsh9L4czUnxeUnnRsFxXRfR5qeJxS7dd-M1fXat9g09IlHetV3z7XM4I0FQPv27INGqjy1jR5+CU9TDPneaiXg3kMwy-j3y7zXB2fdwyvtL1aCFIz4kUCaBECBGxgEiIC+iAWLq8iSCkJw1BI2SFoaPmEMw9BWCyFYNQJACobCnU-t-EmBobYQNhBURImIL5X2sMQO+D9ErP2wK-e+u0P6mC-pWWBkZIGEOga-X+x1fLwMxIg5Bl9r4Uwwe6dOT8X6oDwf4AhwAiE-yNPQVsZDeEUJIdQikKAEFIPuFERsAArS+hZNC+BgYwxAABiKAiQYBQAAEJgEwGoa+NZVCNBrBgNAGitE6P0YYwYl5wAQCMEAA)

<details>
<summary> Código de texto </summary>

```text
<cir f="5" ts="0.000005" ic="15.472767971186109" cb="59" pb="43" vr="5" mts="5e-11">
  <ctr x="256 64 272 64" f="0" bi="12" hv="9" in="false" mo="0" v4="9" v5="9" v6="9" v7="9" v8="9" v13="9"/>
  <g x="-96 288 -96 304" f="0"/>
  <w x="-208 224 -192 224" f="0"/>
  <w x="-256 224 -208 224" f="0"/>
  <w x="-208 64 -208 224" f="0"/>
  <r x="-16 64 -208 64" f="0" r="10000"/>
  <w x="-16 192 -16 64" f="0"/>
  <w x="-16 192 -64 192" f="0"/>
  <w x="-64 96 -64 160" f="0"/>
  <w x="-128 96 -64 96" f="0"/>
  <Timer x="-192 128 -176 128" f="6" v5="0.000662106051647335"/>
  <O x="96 240 160 240" f="0" sc="0"/>
  <R x="-256 96 -288 96" f="0" wf="0" maxv="10"/>
  <w x="-256 96 -128 96" f="0"/>
  <r x="-256 224 -256 96" f="0" r="1000000"/>
  <g x="-256 320 -256 336" f="0"/>
  <c x="-256 256 -256 320" f="0" c="3e-7" iv="0.001" sr="0" vd="6.621722622524998"/>
  <w x="-256 256 -192 256" f="0"/>
  <w x="-256 224 -256 256" f="0"/>
  <rw x="-16 192 240 80" f="0">-16,192;240,192;240,80</rw>
  <rw x="240 80 256 64" f="0">240,80;240,64;256,64</rw>
  <rw x="720 480 256 416" f="0">720,480;256,480;256,416</rw>
  <LED x="352 352 480 352" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <LED x="352 384 480 384" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <LED x="352 416 480 416" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <r x="480 416 560 416" f="0" r="1000"/>
  <r x="480 384 560 384" f="0" r="1000"/>
  <r x="480 352 560 352" f="0" r="1000"/>
  <g x="560 416 608 432" f="0"/>
  <g x="560 384 608 400" f="0"/>
  <g x="560 352 608 368" f="0"/>
  <g x="560 320 608 336" f="0"/>
  <r x="480 320 560 320" f="0" r="1000"/>
  <LED x="352 320 480 320" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <rw x="352 64 720 480" f="0">352,64;720,64;720,480</rw>
  <LED x="352 288 480 288" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <LED x="352 256 480 256" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <LED x="352 224 480 224" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <LED x="352 192 480 192" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <LED x="352 160 480 160" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <LED x="352 128 480 128" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <LED x="352 96 480 96" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <r x="480 288 560 288" f="0" r="1000"/>
  <r x="480 256 560 256" f="0" r="1000"/>
  <r x="480 224 560 224" f="0" r="1000"/>
  <r x="480 192 560 192" f="0" r="1000"/>
  <r x="480 160 560 160" f="0" r="1000"/>
  <r x="480 128 560 128" f="0" r="1000"/>
  <r x="480 96 560 96" f="0" r="1000"/>
  <g x="560 288 608 304" f="0"/>
  <g x="560 256 608 272" f="0"/>
  <g x="560 224 608 240" f="0"/>
  <g x="560 192 608 208" f="0"/>
  <g x="560 160 608 176" f="0"/>
  <g x="560 128 608 144" f="0"/>
  <g x="560 96 608 112" f="0"/>
  <o en="28" sp="64" f="x403" p="0">
    <p v="0" sc="0.0000762939453125"/>
    <p v="3" sc="0.0125"/>
  </o>
  <o en="25" sp="64" f="x403" p="1">
    <p v="0" sc="10"/>
    <p v="3" sc="0.0125"/>
  </o>
  <o en="24" sp="64" f="x403" p="2">
    <p v="0" sc="2.5"/>
    <p v="3" sc="0.0125"/>
  </o>
  <adj e="0" ei="3" en="# of Bits" mn="1" mx="1" st="# of Bits"/>
</cir>

``` borrar

</details>

<br>

### Opción 2:  Con transistores ###

Se utiliza un transistor NPN (probar con un 2N2222), el cual se conecta desde la _base_ a la salida de cada _step_ y utilizando el _colector_ como conexión al _step_ correspondiente del VCO

![Captura de Pantalla](./imagenes/sc40.png)

- Se lográ que en el _colector_ hayan 9v de salida

[Circuito Falstad](https://www.falstad.com/circuit/circuitjs.html?ctz=DwYwlgTgBAZgvAIgKwKgFwM6IAwDpsEEpRgiICMuSAbACwBM1AzOQByu1uvkDs9qIAEaIktVAAdhCWk1QA3CCNQBbTCICmAWnLkEAPgBQUKKDTQAHolqso5AJz0odWw9TwE2VILAV+UABZyiHaoYAB2iDAAhgA2GOoqAPY48uTYwankGVBy5PTZuUwZAPSGxsAA5lCWCJp21FD07FB1DUzYYrAppUYmAO7ViJr02Db09LQt9o7jne6ePeUDNcM0jRMtI2MTbt1l-YO1W06Tw6Prc3u9wBZD5A3OZzZ0ux6oighphAiLByv3Lkc2gelzev2AyzuDWmLWc01eC32EMOmmc9Vhk3uni6YKRkNqeRs6NRk3qCJ+SIAKmBlOpbgSHLYmlMeNCmq9qPIkMFcHY+UxWXZaHZCExqKwKdcAPKHeh8JzyphihV+eaoDBkXHXABKKPoa2JTSJnJx2L6aqgyii5iCn0R13xqwaxMJUDJpsl5XpToumwNJotHy+hHt5SqK31bRGfraYvJ4JAerWkZjUCYI3JUE1TC0PFCtrwBF0UAwH2xcgAJogmLhWexqNQ7EhGHw6ChwY6UyntIzI-G8UmGrNU32PeCII6ATDrIDyXpgQAaaYAbmsS4cwGKE6RABkAKIAEUO5Fok2s2EatAv58zymSCAr6miAFcYmhNDF1BWBEGBBUUlmUjYsogiaoWujgvuR41CekxIHkl4XvBqoAXeiCPi+b4fl+P4UH+AFCKhoE4PgEFIvSExIQh6ZUShbxQEG3zjrKV5QOeabRjeHoMRQTHkSx14zjRbHWJmjEEJ6JjhtWHBQMhaayTQ2JqpBh7HqeIljKxp4StxaEPk+USvu+n7flmv5Zv+9GEfRIFgaRkk3PisFOM0LmiKCnh6LBC7iqwy4+R5m7btc9IuX5vp+WJvESeOzkaZwDQ8LJiVzj5iXLsltALolwV9OR+JZWxAIXjwHRzllOX3JlHALqw6bLkwtX1fQy7YHVDXtWVtB5QVhwzh5UCleVHp6GuHltQuE1dR0vXXGgsobBFcqOFF3HiBEnxeOoMVJOhhnGfIgg7Qg9C4NQ9gNjpSBKjweSiFoaRHZqlDYAKPAONgPCnnYrAXeQOZ1I50nSAC7GJXJ7JjkiIM6Zp8PCgGVxevicNw8JOlzjpOXWI1Iw46wc0o-1YOsBeGNk1j9w5WTePteeRMmFB6lwRplFyaet73hhRlYaZuFbZZBFASoxEeA5zE1Ozg3CR50V2rFMOHEwzYc5MKuOEgrjQw6yvRjLqtyzrSx67RClwXk-a61LS3NMO3VW+UiRQOom1yuq4jVnR5hXrIUCe28+zlOIOQARqvGScHocIH74fiyGdisjQ+qOcUiRIs7rsUMWGAB7p7g+29Eh4UHJghwW6ovaGJhpxnLubU1Hte68hd+wH-Cl8A5dh1Xkdl9Hsf2dg92p+n1yZ27fi583OKt8XMf6L0UcVyWve-Mv1aVyRw8p+Ctfj-XiA7CWAfpi3vvz2Infd-RcdPev-e2oP28j3vY9O4f0hT6f3sX-7SjX2jtiO+1cN4L1XtvQgidqDJ3bEifeH8s6nV0tPO0x8C5-wDpyQBK846FkIKyegdgmBChuq-HBm8IHxygUnagu94HvxMFECsAArF2AF1A+HAUggAxFARIMAoAACEwCYBUJtYsygYLqjQIgPhAjhGiIwJKTc4AICGCAA)

<details>
<summary> Código de texto </summary>

```text
<cir f="5" ts="0.000005" ic="1.5642631884188172" cb="54" pb="43" vr="5" mts="5e-11">
  <ctr x="48 192 64 192" f="0" bi="12" hv="9" in="false" mo="0" v10="9" v11="9"/>
  <g x="-96 288 -96 304" f="0"/>
  <w x="-208 224 -192 224" f="0"/>
  <w x="-256 224 -208 224" f="0"/>
  <w x="-208 64 -208 224" f="0"/>
  <r x="-16 64 -208 64" f="0" r="10000"/>
  <w x="-16 192 -16 64" f="0"/>
  <w x="-16 192 -64 192" f="0"/>
  <w x="-64 96 -64 160" f="0"/>
  <w x="-128 96 -64 96" f="0"/>
  <Timer x="-192 128 -176 128" f="6" v5="0.0003551002479499385"/>
  <O x="272 672 336 672" f="0" sc="0"/>
  <R x="-256 96 -288 96" f="0" wf="0" maxv="10"/>
  <w x="-256 96 -128 96" f="0"/>
  <r x="-256 224 -256 96" f="0" r="1000000"/>
  <g x="-256 320 -256 336" f="0"/>
  <c x="-256 256 -256 320" f="0" c="3e-7" iv="0.001" sr="0" vd="3.5513575797473345"/>
  <w x="-256 256 -192 256" f="0"/>
  <w x="-256 224 -256 256" f="0"/>
  <rw x="-16 192 48 192" f="0">-16,192;48,192</rw>
  <LED x="144 480 240 480" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <LED x="144 512 240 512" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <r x="240 512 320 512" f="0" r="1000"/>
  <r x="240 480 320 480" f="0" r="1000"/>
  <r x="240 448 320 448" f="0" r="1000"/>
  <g x="384 512 384 560" f="0"/>
  <LED x="144 448 240 448" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <rw x="144 688 144 544" f="0">144,688;144,544</rw>
  <r x="144 688 224 688" f="0" r="1000"/>
  <rw x="144 416 784 416" f="0">144,416;784,416</rw>
  <rw x="784 416 0 704" f="0">784,416;784,832;384,832;0,832;0,704</rw>
  <rw x="48 544 0 704" f="0">48,544;0,544;0,704</rw>
  <t x="224 688 272 688" f="0" pn="1" be="100" mo="default" vbe="-2.0552826250364284e-98" vbc="0"/>
  <g x="416 480 416 528" f="0"/>
  <g x="448 448 448 496" f="0"/>
  <rw x="448 448 320 448" f="0">448,448;320,448</rw>
  <rw x="416 480 320 480" f="0">416,480;320,480</rw>
  <LED x="144 544 240 544" f="0" mo="default-led" cr="1" cg="0" cb="0" mbc="0.01"/>
  <r x="240 544 320 544" f="0" r="1000"/>
  <g x="352 544 352 592" f="0"/>
  <w x="320 544 352 544" f="0"/>
  <w x="320 512 384 512" f="0"/>
  <w x="224 688 224 704" f="0"/>
  <o en="27" sp="32" f="x403" p="0">
    <p v="0" sc="10"/>
    <p v="3" sc="0.00009765625"/>
  </o>
  <o en="11" sp="8" f="x403" p="1">
    <p v="0" sc="10"/>
  </o>
  <o en="38" sp="32" f="x403" p="2">
    <p v="0" sc="10"/>
    <p v="3" sc="0.0125"/>
  </o>
  <o en="22" sp="32" f="x403" p="3">
    <p v="0" sc="10"/>
    <p v="3" sc="0.0125"/>
  </o>
  <o en="24" sp="32" f="x403" p="4">
    <p v="0" sc="10"/>
    <p v="3" sc="0.0125"/>
  </o>
  <o en="42" sp="32" f="x403" p="5">
    <p v="0" sc="10"/>
    <p v="3" sc="0.00009765625"/>
  </o>
  <o en="28" sp="1024" f="x403" p="6">
    <p v="0" sc="0.0000762939453125"/>
    <p v="3" sc="0.00009765625"/>
  </o>
  <adj e="0" ei="3" en="# of Bits" mn="1" mx="1" st="# of Bits"/>
</cir>

``` borrar

</details>

<br>

Este último nos sirvio para entender la base, lastimosamente esta versión no funcionaba en la realidad.

Hablando con Misa y revisando a otros grupos, nos dimos cuenta del error y se corrigio a posterior (Se explica en funcionamiento)

<br>

### Features

1. 01-v01: En la primera versión del secuenciador con el chip CD4040 se hicieron las conexiones junto al chip 555 para que el clock dictara los pulsos que iban a haber y nos mostrara el funcionamiento de los primeros 4 LEDs que probamos.

  Conectamos todo lo necesario del chip 555 como:

- Potenciómetro de 100k

- Resistencias de 10k y 1k

- Condensadores polarizado de 100n, 10n y condensadores de 100uF

- Un LED

Esto lo conectamos al clock del CD4040 en donde tenemos:

- 4 LEDs

- 4 resistencias de 1k

- BT1 9v

Todo esto cableado con jumpers a sus respectivos steps


2. 01-v02: luego al actualizar la versión colocamos todos los elementos que los profesores nos pidieron como requerimiento para estandarizar todos los proyectos y además les pusimos transistores antes de cada led lo que daría como resultado estos componentes más los que ya estaban mencionados anteriormente:
   
- Fuentes entre 7 y 12v centro positivo, y todos los chips deben ser alimentados con 5v.

- Diodo 1n4007

- Conector DC

- Conector Audio

- Conector Alimentación

- Switch Spdt

- Regulador L7805


3. 01-v03: Para esta versión se corrigieron detalles en la orientación de los leds y resistencias con estas últimas saliendo hacia VCC, ya que anteriormente iban hacia GND, manteniendo todos los componentes que ya estaban y a la pata emisora (1) de los transistores las llevamos hacia GND.

<br>


### Esquemático v01


![esquemático circuito](./imagenes/esquematico-1.png)


### PCB 01 v01


![pcb front](./imagenes/pcb-front-1.png)



![pcb back](./imagenes/pcb-back-1.png)

---
<br>

### Esquemático 01 v02


![esquemático circuito](./imagenes/esquematico-1-02.png)


### PCB 01 v02


![pcb front](./imagenes/pcb-front-1-02.png)



![pcb back](./imagenes/pcb-back-1-02.png)

---
<br>

### Esquemático 01 v03


![esquemático circuito](./imagenes/esquematico-1-03.png)


### PCB 01 v03


![pcb front](./imagenes/pcb-front-1-03.png)



![pcb back](./imagenes/pcb-back-1-03.png)



### Documentación audiovisual funcionamiento protoboard 1

Clickear imagenes para reproducir video

[![Ejemplo circuito 4040](./imagenes/sc42.png)](https://youtu.be/7QSAAqquWV8)

[![Ejemplo circuito 4040](./imagenes/sc43.png)](https://youtu.be/X4rYO5dJ6EY)

[![Ejemplo circuito 4040](./imagenes/sc44.png)](https://youtu.be/25J13NA67AE)

[![Ejemplo circuito 4040](./imagenes/sc49.png)](https://www.youtube.com/shorts/X2s2UjBy3x8)

[![Ejemplo circuito 4040](./imagenes/sc50.png)](https://www.youtube.com/shorts/nYjTRhHY4o8)


<br>

## Circuito 2: registro de desplazamiento estático

### Descripción general/conceptual 2

¿Qué hace el circuito? Intentar explicarlo para gente que no sabe electrónica. Ejemplo: escucha los impactos sobre sí mismo y lo convierte en señales de aviso para otras cosas

Pensemos en este como una ola humana, donde varias personas se van parando y sentando. Solo en algunos momentos hay una sola persona de pie, así mismo funciona este circuito.

Al igual que el anterior esto nos dicta un compás o ritmo a nuestra melodía sintética 

![Ejemplo circuito 4015](./imagenes/registro01.jpeg)


<br>


### Descripción de funcionamiento 2


Este circuito también se categoriza como un secuenciador, es decir, que genera corrientes eléctricas en un patrón repetitivo y ordenado. Podemos tomar el mismo ejemplo del semáforo mencionado en el circuito anterior, donde este funciona encendiendo un LED detrás del otro sucesivamente hasta que se repite el ciclo.

Adicionalmente funciona con el mismo corazón, es decir un reloj que alimenta a este secuenciador. Este nos va a definir la velocidad con la que avanza la ola. Este secuenciador entrega distintas salidas o compases en el orden ya mencionado. El como ocurre esto es muy llamativo, ya que el cerebro detrás de todo esto, realmente son 2, los que se comunican entre ellos para poder generar el efecto ola o cascada.

A continuación, una representación gráfica de su funcionamiento:

![Ejemplo circuito 4015](./imagenes/12.png)

<br>

Tal como se ve, cada salida tiene una duración fija que se repite pero con cierto desfase


#### Explicación más técnica


Ahora bien, desde un punto de vista más técnico, este secuenciador consta de un chip CD4015 el cual está alimentado por el mismo regulador anterior, por lo que se alimenta de 5V. Además de recibir su velocidad de activación de un reloj en base a un CD555 Astable, importante mencionar que este es únicamente para pruebas,  ya que este input puede variar en base a como uno quiera configurarlo, la única condición es que reciba señales de manera periodica (por lo que una manera podría ser pulsar un switch cada cierto tiempo)

Una vez que este IC es alimentado, tanto de energía como de un reloj, comienza funcionar cada uno de sus módulos, ya que consta de 4 de Flip-Flop (en resumen, celdas que poseen una memoría muy pequeña) en cada módulo. Esto significa que cada vez que se recibe una señal, esta es almacenada en una memoria, mientras se activa la siguiente señal, la cual tambien se guarda hasta pasado un corto periodo, donde luego se apagan en el mismo orden de encendido

Estas señales al igual que en contador bínario tambien alimentan unos transistores que encienden Leds. Todas estas señales se pueden conectar a un oscilador para poder generar sonido, ya que un secuenciador no lo logra (además relés, motores o cualquier circuito que necesite activarse siguiendo una secuencia automática.)


### Proceso

Posteriormente empezamos con la investigación del CD4015, que es un chip de registro de desplazamiento que nos permite mover una señal a través de distintas etapas siguiendo los pulsos del reloj. Una forma más fácil de explicar esto es imaginarnos que un grupo de personas está jugando a pasarse la pelota una a otra, cada vez que recibe la señal, la pelota avanza un puesto más. La forma de desplazamiento nos resultó interesante porque nos deja ver como avanza la secuencia paso a paso. Debido a que este chip no estaba en tinkercad ni falstad tuvimos que recurrir a proyectos similares y referencias externas para poder entender mejor cómo funciona y realizamos pruebas en la protoboard.

Las pruebas en la protoboard del CD4015 nos presentaron distintos inconvenientes, como errores de alimentación entre placas nuevamente, malas conexiones, leds quemadas y problemas con la velocidad del reloj, después de corregir esto, cambiamos los valores en las resistencias del reloj 555, logramos que funcionara más estable el circuito, esto nos ayudó mucho para poder observar cómo funciona el desplazamiento de la señal .


### Features

1. 02-v01: En esta segunda versión del secuenciador utilizamos el chip CD4015 junto con un chip 555 encargado de generar los pulsos de clock para su funcionamiento. A diferencia de la prueba anterior, en este caso conectamos directamente 8 LEDs a las salidas del CD4015 para observar de mejor manera la secuencia generada, comprobando cómo cada pulso enciende los LEDs de forma ordenada y repetitiva.

 Conectamos todo lo necesario del chip 555 como:

  - Potenciómetro de 100k

  - Resistencias de 10k y 1k
  
  - Condensadores polarizado de 100n, 10n y condensadores de 100uF
  
  - Un LED


Esto lo conectamos al clock del CD4015 en donde tenemos:
    
  - 8 Resistencias de 220

  - 8 LEDs
  
  - 1 Transistor BC548
 
  - 1 resistencia de 1k

Todo esto cableado con jumpers a sus respectivos steps

<br>

2. 02-v02: Luego, al actualizar la versión del circuito, pusimos todos los elementos solicitados por los profesores para estandarizar los proyectos. Además, agregamos un transistor antes de cada LED entre medio de dos resistencias, mejorando así el control de las salidas. Como resultado, el circuito quedó conformado por estos nuevos componentes, además de los ya mencionados anteriormente, manteniendo como base, solo el secuenciador generado por el chip CD4015:

Fuentes entre 7 y 12v centro positivo, y todos los chips deben ser alimentados con 5v.

- 8 resistencias de 1k

- 8 transistores PN2222A

- Diodo 1n4007

- Conector DC

- 8 Conector Audio

- Conector Alimentación

- Switch Spdt

- Regulador L7805


3. 02-v03: Para esta versión se realizaron modificaciones en la etapa de salida del circuito para adaptar correctamente las conexiones al funcionamiento del CD4015. Los transistores se re organizaron de manera que su pata emisora (1) quedara conectada a GND, mientras que los LEDs pasaron a conectarse al terminal colector (3) de cada transistor. Además, las resistencias asociadas a los LEDs se conectaron hacia VCC, manteniendo el resto de los componentes y conexiones anteriores.

<br>


### Esquemático 2 v01


![esquemático circuito](./imagenes/esquematico-2.png)


### PCB 02 v01


![pcb front](./imagenes/pcb-front-2-01.png)



![pcb back](./imagenes/pcb-back-2-01.png)

---
<br>

### Esquemático 02 v02


![esquemático circuito](./imagenes/esquematico-2-02.png)


### PCB 02 v02


![pcb front](./imagenes/pcb-front-2-02.png)



![pcb back](./imagenes/pcb-back-2-02.png)

---
<br>

### Esquemático 02 v03


![esquemático circuito](./imagenes/esquematico-2-03.png)


### PCB 02 v03


![pcb front](./imagenes/pcb-front-2-03.png)



![pcb back](./imagenes/pcb-back-2-03.png)


<br>

### Documentación audiovisual funcionamiento protoboard 2

Incluir enlace a video en youtube (puede estar en Oculto) con protoboard funcionando

![Funcionamiento circuito 2](./imagenes/circuito2v01.gif)

[![Ejemplo](./imagenes/sc.45.png)](https://www.youtube.com/shorts/Avq0Pz7RgVc)

[![Ejemplo](./imagenes/sc46.png)](https://www.youtube.com/shorts/9iWUSzQ8m6s)

[![Ejemplo](./imagenes/47.png)](https://www.youtube.com/shorts/gLU3cue3pys)

[![Ejemplo](./imagenes/47.png)](https://www.youtube.com/shorts/UzTAtNhPJdo)

<br>

## Otros circuitos

¿Usaron otro circuito temporal para activar algunas cosas? ¿para probar inputs-outputs? Detallar cuales

## Colaboración con otros grupos

### ¿Cómo ayudé a otro grupo?

Parte fundamental de la ayuda con otros grupos fue la de revisión preliminar para observar errores, el tener una mirada externa para identficar cables desconectados es fundamental.

Además se ayudo en le uso de KiCad, el como implementar el módulo de alimentación, huellas, o el como subir los archivos a GitHub fueron parte de las ayudas prestadas por el grupo

### ¿Cómo me ayudó otro grupo?

Recibimos constante ayuda en general en relación al como iban a interactuar con las otras secciones del sintetizador, por ejemplo, con el equipo Piezo se logró entender como ellos influirian en ek secuenciador o como el oscilador debería recibir nuestran señal.

Esto fue fundamental para entender el Circuito, además del como se articulaban las PCB, es decir, pensar en el diseño de la interfaz

No solo queda en aspectos técnicos, ya que todas las bitácoras grupales fueron muy útiles para entender como articular el texto de la nuestra. Queremos hacer mención especial al grupo 06 por que su repo fue el que más nos aclaró como redactar esto

Muchas gracias a todo el curso, al igual que al equipo docente. Logramos algo que hace 2 meses veiamos imposible de lograr como estudiantes de diseño <3

## Bibliografía

Build Electronic Circuits. (s. f.). IC 4015 shift register. https://www.build-electronic-circuits.com/4000-series-integrated-circuits/ic-4015/

IBM Community. (s. f.). What is the difference between BC547 transistor vs 2N2222 transistor? https://community.ibm.com/community/user/discussion/what-is-the-difference-between-bc547-transistor-vs-2n2222-transistor

Lorre Mill. (2024, 29 de abril). Cycling24. https://lorre-mill.com/2024/04/29/Cycling24.html

Proveedora Cano. (s. f.). Transistor 2N2222. https://proveedoracano.com/blog/transistor-2n2222_012/

Roden, M. (s. f.). Transistor. HyperPhysics. Georgia State University. http://hyperphysics.phy-astr.gsu.edu/hbasees/Solids/trans.html

YouTube. (s. f.). Video sobre electrónica [Video]. https://www.youtube.com/watch?v=jHPMg0YVU5w

YouTube. (s. f.). Video sobre electrónica [Video]. https://www.youtube.com/watch?v=SbdzP9XvCiE

YouTube. (s. f.). Video sobre electrónica [Video]. https://www.youtube.com/watch?v=UFtW6kHt54g


```
