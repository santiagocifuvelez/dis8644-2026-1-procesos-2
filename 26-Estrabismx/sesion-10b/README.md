# sesion-10b

## Dudas ##

1. ¿Como amplifica la corriente el transistor?


- Trabajo grupal

- Pruebas 4040 + clock

  - 4040 sin vco + amp = mal
 
- Organización de trabajo

## Trabajo en casa ##

 
### CD4040 ###

#### Opción 1 ####

En base a lo comentado por Aaron reliace el circuito en _Falstad_, para poder visualizar como el voltaje variaba antes y despues de pasar por el IC. Podría aprovechar para revisar el uso de transistores al momento de elevar el voltaje de salida y así poder incluir los led en el secuenciador final.

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

```

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

```

</details>
