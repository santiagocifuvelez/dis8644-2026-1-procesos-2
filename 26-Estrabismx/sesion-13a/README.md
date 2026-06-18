# sesion-13a

## Clase

### 30 Minutos iniciales

En esta sesión se mencionaron bastantes referentes, se enlistarán para tener un resgistro y en algún momento onvestigar más sobre ellos

1. Camilo Cantor / Exploratorio de Medellin

Camilo es la cabeza detras del centro que se especializa en la exploración creativa. El Exploratorio realiza talleres, investigaciones y acercamientos gratuitos al público general en Medellin. Un ejemplo de esto es la realización de talleres para la fabricación de rampas de SkateBoard, esto se logró gracias a la participación de carpinteros del centro, además de propios _skaters_.

Este centro lo veo como un referente, ya que me considero una persona amante del _open source_, y de practicas similares. En su momento ya hablé sobre la diversificación de conococimientos, y ahora lo reafirmo. Me animaron las palabras de los profes sobre la exisitencia de un lugar asi en Chile, veo un sueño realizar un espacio donde el conocimiento se comparta de manera libre, donde todxs puedan aprendar y lo más importante generar comunidad, algo que se va a necesitar mucho estos años 

<br>

2.  HECHIZOS, POR MIENTRAS PARA SIEMPRE

Este texto nos introduce sobre el concepto de lo _hechizo_, algo bastante común en la cultura latinoamericana y que en Chile se le conoce con ese nombre

Me gustaría darme el tiempo antes de la próxima sesión de leer esto porque para mi, el diseño como rol social es algo fundamental de entender y realizar.

<br>

3. Desobediencia tecnológica

Este libro se enfoca en el mismo principio anterior, me dejo como tarea buscarlo físico o digital (obviamente todo legal xd)

<br>

4. @no.si.si.no

   Nos mencionaron a esta artista y su perfil de GitHub, el que no alcance a leer

<br>

### De KiCad a JLCPCB

Lo primero es que esta manera funciona con JLCPCB. Desconozco si servirá con otro proveedor


1. El formato de archivo _gerber_ (.grb) es el estándar para la fabricación de PCB. Este se categoriza com un tipo de archivo ASCII vectorial.

Para poder fabricar y generar los archivos correspondientes, necesitamos mínimo 7 capas

| N° | Capa         | Descripción       |
| -- | ------------ | ----------------- |
| 1  | Cu F         | Cobre frontal     |
| 2  | Cu B         | Cobre trasero     |
| 3  | Edge Cut     | Corte contorno    |
| 4  | Mask F       | Negativo frontal  |
| 5  | Mask B       | Negativo trasero  |
| 6  | Silkscreen F | _Dibujos_ frontal |
| 7  | Silkscreen B | _Dibujos_ trasero |


2. Para poder exportar estos archivos, abriremos nuestro proyecto y luego el _.kicad_pcb_

3. Ahora en la pestaña de archivo, seleccionaremos _Trazar_ (_plot_, si lo tenemos en ingles)

![KICAD](./imagenes/sc54.png)



4. Debemos tener las capas seleccionados, según lo que necesitemos. En nuestro caso se realiza con las 7 ya mencionadas

![KICAD](./imagenes/sc55.png)



5. Posteriormente debemos definir la ruta de guardado de los archivos, para ello seleccionaremos el icono de carpeta y definimos donde queremos guardarlos

![KICAD](./imagenes/sc56.png)



6. Una vez ya definido la ubicación, procedemos a _**Trazar**_ y luego a _**Generar archivos de taladro**_

![KICAD](./imagenes/sc60.png)


7. Con nuestro archivos generados podemos ahora comprimirlos en **_.ZIP_**

![KICAD](./imagenes/sc57.png)

![KICAD](./imagenes/sc58.png)

![KICAD](./imagenes/sc59.png)



8. Ahora ingresamos  [JLCPCB](https://jlcpcb.com/) y seleccionamos **_Get Instant Quote_**

![JLCPCB](./imagenes/sc61.png)



9. Finalmente cargarmos nuestro _.zip_

![KICAD](./imagenes/sc62.png)


10. Podemos configurar aspectos como el color de las pcb, espesores y acabados en el apartado de **_PCB Specifications_**

![KICAD](./imagenes/sc63.png)


11. Finalmente, podemos pedir nuestras PCB a China

![KICAD](./imagenes/sc64.png)

<br>

### Nuevo Proyecto

Como la continuación del proyecto, ahora se debe realizar un sintetizador en base a los módulos genereados por el curso. Este debe venir acompañado de una carcasa, este encapsulado no tiene un límite, solo nuestra imaginación.

Antes de exponer mis ideas, debo mencionar elementos relevantes:

- Hammond: Son un estándar de _cajas_ para sintetizadores o pedales (no recuerdo cual de los 2)

- Interfaz de usuario: Ya se ha trabajado esto, pero es el como un elemento se relaciona con su usuario

#### Ideas

Creo que poseo una visión bastante industrial, pero estoy tratando de hacer un esfuerzo en salir de mi caja y ver más allá de lo literal. Por lo que tenía 2 ideas en mente

1. En base a la experiencia que he vivido con la electrónica, donde pareciera ser que todo funciona por su propía cuenta, pensaba en que el sintetizador funcionara únicamente por el ambiente, que nosotros como usuarios no podamos modificar activamente el sonido. Por lo mismo, la carcasa debe seguir esta lógica y pensaba en posibles salidas

 - Un material sólido y rígido como cemento o acero. Que además no permita manipular el sinte mediante potenciometros
  
     ![IMAGEN 1](./imagenes/idea01.jpg)

     ![IMAGEN 2](./imagenes/idea02.jpg)

     ![IMAGEN 3](./imagenes/idea03.jpg)


<br>

- Materiales organicos que se infiltren y camuflen con la naturaleza, como podría ser un tronco de madera en bruto o demás
    
     ![IMAGEN 1](./imagenes/idea04.jpg)

     ![IMAGEN 2](./imagenes/idea05.jpg)


     <br>

     En lo personal prefiero algo como la primera opción y esto se debe a la novedad de trabajar estos materiales, además de _resignificar_ estos

<br>

  2. Más que una opción de que quiero, es sobre lo que no me gustaría hacer.

Soy una persona apasionada por la impresión 3D y aún así siento que no es la tecnica adecuada. Esto por el momento no tiene una explicación, pero quería plasmarlo

<br>

## Yoko Ono - Grapefruit

Mi primera impresión del libro fue de sorpresa, no me esperaba tener que leer algo asi para taller y esto es en parte por lo conceptual del libro. 

Lo que si pude identficar en el primer capitulo fue una tendencia a acciones que se repiten en ciclos. Con esto me refiero a que se pueden realizar múltiples veces de manera indefinida, tal como un secuenciador 😛.

Algo que no me habia percatado y que luego de hablar con otras personas del libro fue darme cuenta que cada _poema_ son instrucciones que generan un resultado artistico, que a mi parecer son performance. Luego de darle más vueltas logré entender el porque de esta lectura, al solicitarnos hacer _partituras_, este libro nos indica una manera fuera de la norma de como se puede escirbir _sonido_

Otro punto importante, es que al leer y analizar este libro, me doy cuenta que mi visión y manera de entender las cosas es muy rígida, me cuesta salir de mi caja de pensamiento. Muchas veces pienso de maneras concretas, se que ningún extremo es bueno, por lo mismo espero que este ejercicio me sirva para pensar de manera más conceptual 
