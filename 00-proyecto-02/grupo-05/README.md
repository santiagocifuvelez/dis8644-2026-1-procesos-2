# proyecto-02

## Grupo

Número de grupo: 5

Tema del grupo: Filtro

Integrantes:

- Antonia Améstica / antoniaamc
- Catalina Balboa / Catabalboa
- Sebastian Guevara / sebastianguevaralarotta
- Catalina Jeria / catalinajeria
- Luisa Toro / Luisaatoro9


# ALO HOUSTON — Módulo de Filtro Activo

> *"Houston, hemos tenido un problema."*
> — Jack Swigert, misión Apolo 13, 13 de abril de 1970

<p align="center">
  <img width="700" height="200" alt="apollo 13 GIF" src="https://github.com/user-attachments/assets/efd344f0-f41c-4498-9bfb-454a93b9224d" />
</p>

### El nombre del proyecto

**ALO HOUSTON** nació de dos ideas que se fusionaron durante el proceso de trabajo.

Por un lado, "ALO" es la palabra con la que se establece comunicación es el primer sonido que sale cuando alguien contesta, el acto de decir "aquí estoy, te escucho". Es exactamente lo que hace un filtro de audio: recibe una señal y la procesa para que pueda ser escuchada correctamente.

Por otro lado, al manipular los potenciómetros del filtro en busca de la frecuencia correcta, el proceso se asemejó inevitablemente a una escena que muchos conocen: la de los astronautas del **Apolo 13** en 1970, girando perillas y ajustando frecuencias de radio para mantener comunicación con la Tierra tras la explosión de un tanque de oxígeno a 322.000 km de distancia. El astronauta Jack Swigert se comunicó por radio con el centro de control con la frase que pasaría a la historia: *"Houston, tenemos un problema"* una línea que se volvió símbolo universal de buscar solución en medio del caos.

Ese gesto de ajustar una frecuencia para encontrar conexión es exactamente lo que sentimos al trabajar con este filtro. Cada potenciómetro es una búsqueda. Cada ajuste, una tentativa de encontrar la frecuencia correcta.

---

### Descripción general

Este módulo forma parte de un proyecto modular de síntesis de audio en el que cada grupo desarrolló un bloque independiente (oscilador, secuenciador, filtro, percusión) con el requisito de que todos fueran compatibles entre sí bajo un estándar de alimentación de **5V**.

Nuestro módulo es un **filtro activo de audio** con dos propuestas de diseño: una con chip LM324 (filtro activo con tres etapas de op-amp) y una pasiva (solo resistencias y condensadores, sin chip). Ambas reciben señal desde una fuente externa vía jack 3.5mm y entregan la señal filtrada hacia los demás módulos del sistema.

---

### Investigación y Referencias

El proceso comenzó mucho antes de tocar la protoboard. Antes de comprar cualquier componente, nos dedicamos a estudiar la teoría de filtros en libros técnicos de electrónica para entender conceptos como frecuencia de corte, ganancia, impedancia y la diferencia entre filtros pasivos y activos.

Paralelamente, buscamos inspiración en el mundo del audio real, específicamente en páginas especializadas en diseño de **pedales de guitarra**. Analizar cómo esos circuitos filtran la señal de las pastillas para modificar el timbre (brillo, cuerpo, distorsión) nos dio una perspectiva práctica muy útil: no solo cómo funciona un filtro en papel, sino por qué suena de una manera u otra dependiendo de los componentes elegidos. Esa investigación fue la base para decidir qué tipo de controles queríamos implementar.

<div align="center">

| | |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/502f04e9-8ab0-48ec-9585-bbdf7aaffca4" height="350"/> | <img src="https://github.com/user-attachments/assets/c2b0dbfa-fde5-40b7-b633-d36660b19d41" height="350"/> |
| <img src="https://github.com/user-attachments/assets/50866751-5d7e-468c-9154-bd5385bc1041" height="350"/> | <img src="https://github.com/user-attachments/assets/981587c5-1169-45f7-8380-93bef7ff11ab" height="350"/> |

*Imágenes de referencia*

</div>

---

### Organización y Selección de Materiales

 Antes de comprar, evaluamos tres opciones para la generación de señal:

<div align="center">

| Chip | Tipo | Función |
|:---:|:---:|:---:|
| **CD4046** | VCO (oscilador controlado por voltaje) | Genera una frecuencia base ajustable con potenciómetro o voltaje externo |
| **CD4040** | Divisor de frecuencia binario de 12 bits | Divide la frecuencia de entrada en sub-octavas (÷2, ÷4, ÷8...) |
| **CD4017** | Contador de décadas / secuenciador | Activa 10 salidas en secuencia, útil para ritmos y melodías automáticas |

| Chips 4046 | Chips 4040 | Chips 4017 |
|:---:|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/4a539834-51f9-418b-a29d-5f891a722f6f" height="200"/> | <img src="https://github.com/user-attachments/assets/b313f909-e76d-4339-a375-bfa88e63fc44" height="200"/> | <img src="https://github.com/user-attachments/assets/4b8cc9f8-bff0-49de-9071-38b3cb2c8e7b" height="200"/> |

</div>

### Decisión final

Optamos por usar el **CD4046, el TL072 y el LM386 en conjunto**. El CD4046 actúa como oscilador base generando una señal de frecuencia controlable mediante potenciómetros, el TL072 se encarga del filtrado activo de esa señal, y el LM386 amplifica la salida para poder escucharla directamente en un parlante de 8Ω.

Esta combinación nos permitió tener en un solo módulo generación de señal, filtrado y amplificación, todo funcionando bajo el estándar de **5V** del proyecto modular.

<div align="center">
  
| Chips 4046 | Chips TL072 | Chips LM386 |
|:---:|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/4a539834-51f9-418b-a29d-5f891a722f6f" height="200"/> | <img src="https://github.com/user-attachments/assets/fc1f602d-0903-4c2c-956a-c842d7734174" height="200"/> | <img src="https://github.com/user-attachments/assets/5805a492-bd54-49dc-8818-950b4af8435d" height="200"/> |

</div>

---

### Proceso de Prototipado y Trial & Error

### Primera prueba: el oscilador funcionando

El primer circuito que armamos fue el oscilador con el **CD4046 + TL072 + LM386 + parlante de 8Ω**. El objetivo era simple: que sonara algo. Una vez confirmado que el oscilador generaba señal audible, expandimos el circuito incorporando **4 potenciómetros** para tener control manual sobre distintos parámetros:

<div align="center">

| | |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/1ccf9e63-bc41-4a95-98b3-7d7474b36bcc" height="280"/> | <img src="https://github.com/user-attachments/assets/b0e1b06a-4588-49b7-89d3-08f77dbe818c" height="280"/> |
| <img src="https://github.com/user-attachments/assets/d3497306-6bd5-4e97-8e39-767de32a82c1" height="280"/> | <img src="https://github.com/user-attachments/assets/babed4ab-e58d-473c-a968-e6cf1b5b310b" height="280"/> |

| |
|:---:|
| <img src="https://github.com/user-attachments/assets/db8f67c7-cd93-438c-827b-2fa271f89d7f" height="280"/> |

*Imágenes del proceso*

</div>

- **Potenciómetro de volumen** conectado al LM386 
- **Dos potenciómetros en el CD4046**: uno controlando el rango de frecuencia y otro ajustando la "dulzura" o armonía de la onda (conectados a los pines 9, 11 y 12 del chip)
- **Un potenciómetro en el TL072**

<div align="center">

<img  width="1100" height="700" alt="image" src="https://github.com/user-attachments/assets/a7a6d7a1-bbf2-447c-969a-9f55f170da4a" height="400"/>

*Imagen del proceso*

</div>

### El gran error del Pin 4

Uno de los errores más importantes y que nos costó bastante tiempo fue conectar un potenciómetro al **pin 4 del CD4046** esperando que controlara algo. El potenciómetro no hacía absolutamente nada.

Revisamos las resistencias, probamos distintas conexiones, descartamos problemas de cableado... hasta que finalmente releímos el datasheet con más detalle y descubrimos que el **pin 4 es una salida de voltaje (VCO out), no una entrada de control**. Conectar un potenciómetro ahí no tiene ningún efecto porque el pin no recibe señal, la emite.

Fue un error de no leer bien la hoja de datos antes de conectar. Aprendimos que revisar el datasheet pin por pin antes de armar el circuito ahorra horas de diagnóstico.


### Estabilización y limpieza de señal

Al tener cables largos y múltiples conexiones en la protoboard, comenzamos a notar ruido e inestabilidad en la señal. Para resolverlo instalamos:

- **Capacitores electrolíticos** al inicio y al final de la protoboard para estabilizar la alimentación y reducir el ripple
- **Capacitores cerámicos ("lenteja")** cerca de cada chip para filtrar ruidos de alta frecuencia que los integrados generan internamente

Esto es una práctica estándar en diseño de circuitos (desacoplamiento de alimentación) que en la protoboard se nota especialmente porque los cables largos actúan como antenas.

### Video de demostración · prueba CD4046, TL072 y LM386

▶️ [Ver video - Demostración prueba CD4046, TL072 y LM386](https://www.youtube.com/shorts/DG93RWHXpzA?feature=share)

---

### Propuesta 1 — Filtro Activo con LM324

#### Descripción general

Imagina que estás en una fiesta con mucho ruido y solo quieres escuchar la conversación de la persona que tienes al frente. Tu cerebro filtra automáticamente los sonidos que no te interesan y deja pasar solo lo que quieres oír. Este circuito hace exactamente eso con señales de audio: recibe toda la música o sonido que le mandes, elimina las frecuencias que no quieres y deja pasar solo las que te interesan, con el volumen que tú elijas.

#### Descripción de funcionamiento

**¿Qué inputs recibe?**
Recibe una señal de audio analógica por un jack 3.5mm, que puede venir de un celular, un PC, o de otro módulo del sistema como el oscilador CD4046. También recibe alimentación de 9V desde una pila, que el LM7805 regula a 5V estables.

**¿Qué outputs entrega?**
Entrega la misma señal de audio pero filtrada, es decir con ciertas frecuencias atenuadas o eliminadas, por otro jack 3.5mm. La señal de salida cumple el estándar de 5V del sistema modular, por lo que puede conectarse directamente a los otros módulos del proyecto.

**¿Cómo administra los flujos de input a output internamente?**
La señal pasa por tres etapas en cadena. Primero entra al buffer que la protege y la estabiliza. Luego pasa por el filtro pasa-bajos donde el potenciómetro RV1 decide qué frecuencias dejar pasar. Finalmente pasa por una segunda etapa de filtrado que refina el resultado. En cada etapa el LM324 amplifica la señal para compensar las pérdidas del filtro.

**¿Cuál es el corazón/cerebro del circuito?**
El LM324. Es un chip que tiene cuatro amplificadores operacionales dentro, y usamos tres de ellos. Sin el LM324 el circuito no puede amplificar, no puede filtrar activamente y no puede mantener la señal al nivel que necesitan los otros módulos.

**¿Qué truco descubrimos en el camino?**
Que el LED conectado a la salida del op-amp funciona como un indicador visual de la señal: cuando hay más señal, el LED brilla más fuerte; cuando el filtro corta las frecuencias, el LED se apaga o baja. Es una forma de ver el comportamiento del filtro sin necesitar un osciloscopio. Lo descubrimos después de quemar un chip por conectarlo mal, pero una vez que lo hicimos bien fue una de las cosas más útiles del circuito.

**¿Qué se podría conectar a este módulo en el futuro?**
A la entrada se podría conectar el módulo oscilador de otro grupo para filtrar las frecuencias que genera. A la salida se podría conectar un amplificador de potencia como el LM386 para escuchar el resultado en un parlante, o conectarlo al módulo de percusión para que el ritmo pase por el filtro antes de sonar. También se podría agregar un segundo potenciómetro para controlar la frecuencia de corte de forma independiente al volumen.

---

Este circuito usa tres etapas de op-amp del **LM324** en cascada para lograr filtrado, control de ganancia y buffer de salida. Tiene alimentación dual derivada desde 12V con regulación a 5V mediante el **LM7805**.

#### Pines del LM324 que usamos

El LM324 es un chip DIP-14 que contiene **4 amplificadores operacionales independientes** (op-amps) dentro de un solo encapsulado, numerados internamente como A, B, C y D. Todos comparten la misma alimentación pero operan de forma completamente independiente entre sí.

Los pines que usamos y su función:

<p align="center">
  <img width="750" height="450" alt="Removed Background-0(2)" src="https://github.com/user-attachments/assets/4c28a324-6d43-4acf-8802-20edb779a4b0" />
  <img width="750" alt="image" src="https://github.com/user-attachments/assets/ff3aef47-5c0a-4d32-8a86-dc2395f2d94b" />
  <br/>
  <em>Configuración de Pines (LM324)</em>
</p>

<div align="center">
  
| Pin | Nombre | Función en nuestro circuito |
|-----|--------|-----------------------------|
| **4** | V+ | Alimentación positiva (+5V desde el LM7805) |
| **11** | GND | Alimentación negativa (GND, referencia del sistema) |
| **3** | IN+ (op-amp A) | Entrada no inversora del buffer — recibe la señal de audio del jack |
| **2** | IN− (op-amp A) | Entrada inversora del buffer — conectada a la retroalimentación con R8 |
| **1** | OUT (op-amp A) | Salida del buffer — señal limpia lista para entrar al filtro |
| **6** | IN+ (op-amp B) | Entrada no inversora del filtro pasa-bajos — recibe la salida del buffer |
| **5** | IN− (op-amp B) | Entrada inversora — conectada a la red RC (R4 + C2) y al potenciómetro RV1 |
| **7** | OUT (op-amp B) | Salida del filtro — señal con frecuencias altas atenuadas |
| **9** | IN+ (op-amp C) | Entrada no inversora de la segunda etapa de filtrado |
| **10** | IN− (op-amp C) | Entrada inversora — conectada a la segunda red RC (R7 + C3) |
| **8** | OUT (op-amp C) | Salida final filtrada — va al LED indicador y al jack de salida |

</div>

<p align="center">
  <img width="1100" height="600" alt="Esquemático circuito activo LM324" src="https://github.com/user-attachments/assets/67f33c1f-4c70-42df-b8d4-6b760d996db5" />
 
  <br/>
  <em>Esquemático — Filtro Activo LM324</em>
  </p>



**Descripción del esquemático:**

<!-- ALIMENTACIÓN -->
<table><tr><td style="background:#E6F1FB; border-left:4px solid #378ADD; border-radius:6px; padding:10px 14px">
<strong style="color:#0C447C">🔵 Alimentación</strong><br>
<span style="color:#185FA5">Entrada por dos conectores Barrel Jack (J2, J3) con diodo 1N4007 (D1) de protección contra inversión de polaridad. El LM7805 (U8) regula de +12V a +5V estables. Condensadores C5 (100µF), C6 (10µF) y C7 (100nF) filtran el ripple en distintas frecuencias. Un LED (D8) con resistencia de 1kΩ (R9) indica visualmente que hay alimentación activa.</span>
</td></tr></table>

<!-- ETAPA 1 -->
<table><tr><td style="background:#EAF3DE; border-left:4px solid #639922; border-radius:6px; padding:10px 14px">
<strong style="color:#27500A">🟢 Etapa 1 — Buffer de entrada (U1A, LM324)</strong><br>
<span style="color:#3B6D11">La señal de audio entra por el jack J4, pasa por un capacitor de acople C1 (1µF) que bloquea la componente DC, y llega a la entrada no inversora (+) del primer op-amp. La resistencia R1 (22kΩ) fija el punto de polarización. La resistencia R8 (10kΩ) en el lazo de retroalimentación le da ganancia unitaria al buffer, cuya función es aislar la fuente de la etapa de filtrado sin cargarla.</span>
</td></tr></table>

<!-- ETAPA 2 -->
<table><tr><td style="background:#FAEEDA; border-left:4px solid #BA7517; border-radius:6px; padding:10px 14px">
<strong style="color:#633806">🟡 Etapa 2 — Filtro pasa-bajos activo (U1B, LM324)</strong><br>
<span style="color:#854F0B">Formado por la red RC con R4 (100kΩ) y C2 (33nF), que define la frecuencia de corte. El potenciómetro RV1 (100kΩ) ajusta la retroalimentación del op-amp, permitiendo variar la ganancia y la "pendiente" del filtro en tiempo real. R2 (10kΩ) y R3 (10kΩ) fijan la polarización de la entrada inversora a la referencia de voltaje medio.</span>
</td></tr></table>

<!-- ETAPA 3 -->
<table><tr><td style="background:#EEEDFE; border-left:4px solid #7F77DD; border-radius:6px; padding:10px 14px">
<strong style="color:#26215C">🟣 Etapa 3 — Segunda celda de filtrado (U1C, LM324)</strong><br>
<span style="color:#3C3489">Una segunda etapa RC con R7 (220kΩ) y C3 (10nF) filtra las frecuencias más altas que pasan la primera etapa. R5 (100kΩ) y R6 (100kΩ) configuran la ganancia de esta etapa. La salida pasa por un LED indicador (D9) con R10 (1kΩ), que parpadea o varía su brillo visualmente según la amplitud de la señal filtrada, útil para diagnóstico sin osciloscopio.</span>
</td></tr></table>

<!-- SALIDA -->
<table><tr><td style="background:#E1F5EE; border-left:4px solid #1D9E75; border-radius:6px; padding:10px 14px">
<strong style="color:#04342C">🩵 Salida</strong><br>
<span style="color:#0F6E56">La señal filtrada sale por el jack J4 (AudioJack2_SwitchT) etiquetado como INPUTS/OUTPUTS, compatible con el estándar de 5V del sistema modular.</span>
</td></tr></table>

<!-- DIFICULTADES -->
<table><tr><td style="background:#FCEBEB; border-left:4px solid #E24B4A; border-radius:6px; padding:10px 14px">
<strong style="color:#501313">🔴 Dificultades encontradas</strong><br>
<span style="color:#A32D2D">También tuvimos problemas de sonido "gangoso" y muy atenuado al principio, causado por usar un divisor resistivo de dos 10kΩ para generar la referencia de voltaje en lugar de un regulador real. El divisor no entrega suficiente corriente cuando el circuito lo carga, haciendo que la referencia caiga. La solución fue el LM7805.</span>
</td></tr></table>

### PCB 1

<p align="center">
  <img width="1100" height="600" alt="image" src="https://github.com/user-attachments/assets/43d6dd07-d854-47e5-ac8d-131c7bd17016" />
  <br/>
  <em>pcb front</em>
</p>


<p align="center">
  <img width="1100" height="600" <img width="1163" height="917" alt="image" src="https://github.com/user-attachments/assets/170e3f27-bd0e-417d-92cc-1abb855920a2" />
  <br/>
  <em>pcb back</em>
</p>


### Documentación audiovisual funcionamiento protoboard 1

▶️ [Ver video - Protoboard funcionando](https://youtube.com/shorts/8Vxiub88sy0?feature=share)

---

### Propuesta 2 — Filtro Pasivo RC

***RC son las iniciales de los dos componentes que forman el filtro***

R = Resistencia (en inglés Resistor)
C = Condensador (en inglés Capacitor)

#### Descripción general

Imagina que tienes una manguera de agua con varios filtros de distintos tamaños puestos uno después del otro: los primeros dejan pasar partículas grandes, los siguientes solo las pequeñas. Este circuito hace algo similar pero con sonido: la señal de audio entra por un lado y los condensadores y resistencias actúan como filtros físicos que dejan pasar unas frecuencias y bloquean otras, sin necesitar ninguna fuente de energía externa para hacerlo.

#### Descripción de funcionamiento

**¿Qué inputs recibe?**
Recibe una señal de audio analógica por un jack 3.5mm. No necesita alimentación externa porque no tiene chips activos, solo componentes pasivos.

**¿Qué outputs entrega?**
Entrega la señal de audio filtrada por otro jack 3.5mm. La señal de salida siempre es más débil que la entrada porque los filtros pasivos no pueden amplificar, solo atenuar.

**¿Cómo administra los flujos de input a output internamente?**
La señal entra y pasa por dos redes RC en serie. Cada red tiene un potenciómetro que al girarlo cambia la resistencia y por lo tanto qué tan fuerte pasan las distintas frecuencias. Entre las dos redes hay una resistencia que las separa para que no se interfieran entre sí. El condensador de entrada bloquea cualquier componente de corriente continua que pueda venir de la fuente.

**¿Cuál es el corazón/cerebro del circuito?**
Los potenciómetros RV1 y RV2. Son los únicos componentes que el usuario puede controlar en tiempo real. Al girarlos cambian la frecuencia de corte de cada etapa, lo que determina el carácter del sonido que sale.

**¿Qué truco descubrimos en el camino?**
Que usar condensadores de distintos valores en paralelo dentro de una misma etapa (como C2 de 33nF y C3 de 330nF juntos) crea una respuesta de frecuencia más suave y gradual que un solo condensador. Cada uno filtra un rango distinto y el resultado combinado suena más natural que un corte abrupto.

**¿Qué se podría conectar a este módulo en el futuro?**
Al ser completamente pasivo y no requerir alimentación, es el módulo más fácil de encadenar con cualquier otra cosa. A la entrada podría conectarse directamente cualquier instrumento o fuente de audio. A la salida se podría poner un amplificador activo como el filtro con LM324 de nuestra propuesta 1, o directamente el LM386 para escucharlo. También sería interesante conectarle un medidor de nivel o un visualizador de frecuencias para ver en tiempo real qué está filtrando.

---

Esta segunda propuesta prescinde completamente de chips activos. Usa únicamente resistencias, condensadores y potenciómetros, por lo que no requiere alimentación externa para funcionar.

<p align="center">
   <img width="1100" height="600" alt="Esquemático filtro pasivo RC" src="https://github.com/user-attachments/assets/e624c2d4-7068-44cf-9a1d-68b92d12affa" />
  <br/>
  <em>Esquemático — Filtro Pasivo RC</em>
</p>

**Descripción del esquemático:**

<!-- ENTRADA -->
<table><tr><td style="background:#E6F1FB; border-left:4px solid #378ADD; border-radius:6px; padding:10px 14px">
<strong style="color:#0C447C">🔵 Entrada</strong><br>
<span style="color:#185FA5">Jack 3.5mm (J5) con capacitor de acople C1 (1µF) para bloquear DC.</span>
</td></tr></table>

<!-- PRIMERA RED -->
<table><tr><td style="background:#EAF3DE; border-left:4px solid #639922; border-radius:6px; padding:10px 14px">
<strong style="color:#27500A">🟢 Primera red de filtrado</strong><br>
<span style="color:#3B6D11">El potenciómetro RV1 (100kΩ) en combinación con C2 (33nF) y C3 (330nF) forman un filtro de primer orden ajustable. Al girar RV1 se modifica la impedancia del divisor y por lo tanto la frecuencia de corte efectiva. R1 (10kΩ) y R2 (1kΩ) fijan los límites del rango de ajuste para evitar cortocircuitar la señal en los extremos del potenciómetro.</span>
</td></tr></table>

<!-- INTER-ETAPAS -->
<table><tr><td style="background:#FAEEDA; border-left:4px solid #BA7517; border-radius:6px; padding:10px 14px">
<strong style="color:#633806">🟡 Resistencia de acople inter-etapas</strong><br>
<span style="color:#854F0B">R3 (10kΩ) conecta la primera red con la segunda, aislando parcialmente ambas etapas para que no se carguen mutuamente y alteren la frecuencia de corte de forma no controlada.</span>
</td></tr></table>

<!-- SEGUNDA RED -->
<table><tr><td style="background:#EEEDFE; border-left:4px solid #7F77DD; border-radius:6px; padding:10px 14px">
<strong style="color:#26215C">🟣 Segunda red de filtrado</strong><br>
<span style="color:#3C3489">Simétrica a la primera, con RV2 (100kΩ), C4 (153nF) y C5 (154nF). R4 (10kΩ) y R5 (1kΩ) cumplen el mismo rol de limitar el rango del potenciómetro.</span>
</td></tr></table>

<!-- SALIDA -->
<table><tr><td style="background:#E1F5EE; border-left:4px solid #1D9E75; border-radius:6px; padding:10px 14px">
<strong style="color:#04342C">🩵 Salida</strong><br>
<span style="color:#0F6E56">Jack 3.5mm (J4) etiquetado como INPUTS/OUTPUTS.</span>
</td></tr></table>

<!-- VENTAJAS Y LIMITACIONES -->
<table><tr><td style="background:#F1EFE8; border-left:4px solid #888780; border-radius:6px; padding:10px 14px">
<strong style="color:#2C2C2A">⚪ Ventajas y limitaciones</strong><br>
<span style="color:#5F5E5A">Al ser pasivo, este filtro no consume energía y no puede quemar ningún chip. Sin embargo, tiene atenuación inherente (la señal de salida siempre es más baja que la de entrada) y no tiene ganancia. Fue útil como referencia comparativa para entender qué aporta el op-amp en el circuito activo.</span>
</td></tr></table>


### PCB 1

<p align="center">
  <img width="1100" height="700" <img width="1087" height="871" alt="image" src="https://github.com/user-attachments/assets/45b18f21-d21c-4bae-bf7c-a5853d143a90" />
  <br/>
  <em>pcb front</em>
</p>


<p align="center">
  <img width="1100" height="700" <img width="1322" height="968" alt="image" src="https://github.com/user-attachments/assets/d7c02758-59ac-4a53-ae15-0d47ba032fcb" />
  <br/>
  <em>pcb back</em>
</p>

### Documentación audiovisual funcionamiento protoboard 2

▶️ [Ver video - Protoboard funcionando](https://www.youtube.com/shorts/B4kGonyN404?feature=share)

---

### Diseño de las PCBs

Concepto de diseño — ***La onda como forma***

Buscamos que la forma física de la placa representara visualmente el concepto del proyecto: **una onda de audio**.

Una onda de audio, cuando se visualiza en un osciloscopio o en software de análisis de frecuencias, genera formas orgánicas, curvas concéntricas y patrones circulares que se expanden desde un centro. Esa imagen fue la inspiración directa para el diseño del contorno de una de las placas.

La placa con forma de **silueta de cabeza con ondas concéntricas** representa precisamente eso: frecuencias que irradian desde un punto, capas de sonido expandiéndose, la visualización física de lo que el circuito hace eléctricamente. Las pistas que recorren la placa en espiral refuerzan esa idea de señal en movimiento.

La segunda placa, de forma rectangular estándar, fue una decisión práctica para alojar los componentes de alimentación y el chip principal con más orden y espacio, priorizando la funcionalidad sobre la forma.

### Referencia al tocadiscos

El diseño circular con pistas en espiral también evoca inevitablemente un **tocadiscos de vinilo**: un objeto analógico que lee frecuencias grabadas físicamente en una superficie, exactamente como nuestro circuito lee y procesa frecuencias eléctricas. El vinilo almacena el sonido como variaciones físicas en un surco en espiral; nuestra PCB procesa esas mismas frecuencias como señales eléctricas. La analogía es directa y coherente con el concepto del proyecto.

<div align="center">

| | |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/fe7f012e-a31d-46f9-b3a8-5b09eb01b15b" width="350"/> | <img src="https://github.com/user-attachments/assets/014f23e1-f7e0-408f-b490-6ed1fdd20734" width="350"/> |
| <img src="https://github.com/user-attachments/assets/4c688697-0b09-42ca-9e69-bf76899091bd" width="350"/> | <img src="https://github.com/user-attachments/assets/a94dd754-1089-4d16-9ece-a148b16ff973" width="350"/> |

*Imágenes de referencia*

</div>

---

### Video proceso grupal - Documentación 

▶️ [Ver video](https://youtube.com/shorts/fhd25QpTn6s?feature=share)

### Aprendizajes clave

- Siempre leer el **datasheet completo** antes de conectar, el error del pin 4 del CD4046 nos costó horas
- Los **capacitores de desacoplamiento** son obligatorios en cualquier circuito con integrados
- Un **divisor resistivo no reemplaza un regulador** cuando el circuito demanda corriente
- Conectar un LED directamente a un pin de op-amp sin resistencia limitadora **quema el chip**
- El filtro pasivo, aunque más simple, permite entender qué rol cumple exactamente el op-amp en el activo
- El diseño de la PCB es parte del proyecto: la forma puede comunicar el concepto igual que el circuito
- Trabajo en equipo
- Organización
- Paciencia y actitud

---

### Componentes utilizados

| Componente | Valor / Modelo | Función |
|------------|---------------|---------|
| LM324 | DIP-14 | Filtro activo (op-amp x4) |
| LM7805CT | TO-220 | Regulador 9V → 5V |
| CD4046 | DIP-16 | Oscilador VCO (etapa de prueba) |
| LM386 | DIP-8 | Amplificador de audio (etapa de prueba) |
| 1N4007 | DO-41 | Diodo protección inversión de polaridad |
| Potenciómetros | 100kΩ, 250kΩ, 500kΩ, B1MΩ (pruebas) — 100kΩ (final) | Control de frecuencia y ganancia |
| Resistencias | 1kΩ, 10kΩ, 22kΩ, 100kΩ, 220kΩ | Red de filtrado y polarización |
| Condensadores electrolíticos | 1µF, 10µF, 100µF | Acople de señal y estabilización |
| Condensadores cerámicos | 103 (10nF), 104 (100nF), 33nF, 153nF, 154nF, 330nF | Filtrado RC y desacoplamiento |
| LEDs | — | Indicador de alimentación y señal de salida |
| Jack 3.5mm | Hembra AudioJack2_SwitchT | Entrada y salida de audio |
| Barrel Jack | — | Entrada de alimentación |
| Switch SPDT | SW3 | Selector de modo |
| Pila | 9V | Alimentación principal |

---

### Bibliografía

* Texas Instruments. LM324 Low-Power Quad Operational Amplifier Datasheet. Documento técnico utilizado para comprender el funcionamiento del amplificador operacional LM324 empleado en el filtro activo.
* Texas Instruments. LM741 Operational Amplifier Datasheet. Documento consultado para el diseño y análisis del filtro de frecuencias altas.
* Texas Instruments. TL072 Low-Noise JFET-Input Operational Amplifier Datasheet. Utilizado para estudiar el procesamiento de señales de audio y el funcionamiento de amplificadores operacionales de bajo ruido.
* Texas Instruments. LM386 Low Voltage Audio Power Amplifier Datasheet. Referencia utilizada para comprender la amplificación de señales de audio durante las pruebas del circuito.
* Texas Instruments. CD4046B Phase-Locked Loop Datasheet. Documento empleado para entender la generación y control de frecuencias mediante un PLL.
* Documentación oficial de KiCad. Utilizada para el diseño de esquemáticos electrónicos, asignación de huellas (footprints) y diseño de placas PCB.
* Material de clases, presentaciones y guías entregadas durante el curso.
* Horowitz, Paul y Hill, Winfield. The Art of Electronics. Cambridge University Press. Libro de referencia sobre diseño y análisis de circuitos electrónicos.
* Sedra, Adel S. y Smith, Kenneth C. Microelectronic Circuits. Oxford University Press. Texto utilizado como apoyo para comprender el funcionamiento de amplificadores operacionales y filtros activos.
* Floyd, Thomas L. Principios de Circuitos Eléctricos. Pearson Educación. Libro de consulta para conceptos fundamentales de electrónica y análisis de circuitos.
* Apuntes personales, registros de laboratorio y pruebas realizadas durante el desarrollo del proyecto.

**Datasheets de los componentes**

LM324 – Texas Instruments Datasheet
LM741 – Texas Instruments Datasheet
TL072 – Texas Instruments Datasheet
LM386 – Texas Instruments Datasheet
CD4046B – Texas Instruments Datasheet

**Software utilizado**

KiCad Documentation
KiCad Official Website
Bibliografía complementaria
The Art of Electronics (Cambridge University Press)
Microelectronic Circuits (Oxford University Press)
Pearson – Principios de Circuitos Eléctricos (Thomas L. Floyd)

**Otras fuentes utilizadas** 

Apuntes de clases del curso.
Guías de laboratorio y material entregado por los docentes.
Registros de pruebas, mediciones y experimentación realizados durante el desarrollo del proyecto.



