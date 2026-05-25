# sesion-09b


Everest pipkin:

<https://everest-pipkin.com/#games/roblox.html> 

HIZO UN FAKIN (escrito a drede) JUEGO DE ROBLOX WTH. que epico 	♡ (⇀ 3 ↼)

Manifiesto cyborg

---

*OK, me salte la ultima parte del tutorial...eso significa que el cableado podía ser menos caotico HEHEHEHEHEHEHEHHE que silly de mi parte*

Para poner los chips debe buscarse como: "dip"   el de la medida 7.62 (es el más comun) y LongPad

Botones: Temporary - Pulsadores - PushButtons

NO: abierto

NC: conectado

Por otro lado están las palancas, que son más utiles para generar estados como Minecraft *Woaos*-

Palancas SPDT para prender nuestras maquinas

Cabe aclarar que esta clase fue de responder dudas concretas, por lo que mayormente son apuntes pequeños que podre ir complementando con la grabación de está misma.

---

## Comprobación DRC

La herramienta DRC se encuentra en el ícono con forma de checklist ubicado en la parte superior derecha. 
Es recomendable ejecutarla antes de enviar la placa a fabricación, porque  detecta errores de conexión y del diseño de la placa.

## Agregar agujeros de montaje en la placa

Dentro del esquemático de KiCad se debe añadir el componente *MountingHole*. Una vez agregado, se posiciona en la PCB con normalidad


## Plano de cobre para el GND

En lugar de unir el ground mediante pistas individuales, se configura toda la superficie de la placa como un plano de cobre conectado a GND en ambas caras. 
Después, para rellenar el plano, se utiliza la *tecla B*


## Importación de gráficos (DXF / SVG / Dibujitos)

Para importar gráficos se debe ir a Archivo → Importar → Gráficos

*Es importante colocarlos en una capa de serigrafía (Silkscreen) y no en una capa de cobre*

---

| Tecla / Atajo | Función |
|---|---|
| `A` | Agregar símbolo |
| `ESC` | Herramienta de selección |
| `M` | Mover componentes |
| `G` | Mover junto con todo el entramado |
| `V` | Asignar valor |
| `CTRL + S`| Guardar |
| `E` | Editar |
| `F` | Asignar footprint |
| `CTRL + D` | Duplicar |
| `R` | Rotar |
| `X` | Reflejar en eje X |
| `Y` | Reflejar en eje Y |
| `ALT + 3` | Abrir visor 3D |
| `F8` | Actualizar espaciado / rellenar plano |

| Término | Descripción |
|---|---|
| **Ground Plane** | Capa completa utilizada como ground |
| **Ground Zone** | Zona vasta de la capa utilizada como ground |
| **Header** | Conector eléctrico, de una o más filas espaciadas por 2.54 mm (0.1”) |
| **IC** | Circuito integrado. Alta cantidad de componentes encapsulados en una pequeña pieza |
| **Layer** | Capa de una PCB |
| **Library** | Biblioteca de componentes donde se almacenan los dibujos de los símbolos y huellas |
| **mil** | Milésima parte de una pulgada, equivalente a 0.0254 mm |
| **PCB** | *Printed Circuit Board*. Placa de circuito impreso; puede ser encargada y serializada en una fábrica o hecha a mano |
| **Package** | Encapsulado. Contenedor de componentes electrónicos; forma física de los elementos |
| **Pad** | Porción de metal expuesto donde va soldado el componente |
| **Placa perforada** | Placa de baquelita con agujeros rodeados de cobre para prototipar. Requiere soldado. Existen las *perfboard* y las *stripboard*, entre otras |

---

## Encargo: Investigar sobre 2 circuitos de percusión hechos con chips.

<https://www.incb.com.mx/index.php/articulos/9-articulos-tecnicos-y-proyectos/9910-generadores-de-percusion-art858s>

Por mi lado encontre esta pagina que explica con diferentes variables como hacer un percutor con el chip CI1 741 y explicado en español.

<https://newtoncbraga.com.mx/articulos/9-articulos-tecnicos-y-proyectos/31055-generador-de-percusion-para-ritmos-musicales-art1596s>

Este ultimo de aca son 3 partes de como construir el percutor con un programa que simula una bateria:

<https://www.youtube.com/watch?v=D80Y_D6E_r8>

A veces en los foros se dan estos experimentos, pero se confunden con los secuenciadores por lo tanto es un poco dificil diferenciar entre ambos circuitos.

<https://www.reddit.com/r/synthdiy/comments/1nuerjm/most_drum_sequencers_need_16_buttons_and_a/>

Otro ejemplo de una pagina que da los pasos a seguir:

<https://www.instructables.com/The-Doof-Machine-Arduino-Drum-Sequencer-Simple-Cus/>


En mi grupo para el lunes consiguieron diferentes videos de otros percutores con pruebas del uso:

<https://www.youtube.com/watch?v=zbBY7JL9nnQ>

<https://www.youtube.com/watch?v=zbBY7JL9nnQ>

## Encargo 2: Lectura time del capitulo 2 y 3!

La imagen tecnica es producida por un aparato

*¿Que es un aparato? -> en el siguiente cap se explica...pequeño spoiler que me hice Xp*

Y como en la parte anterior, estos aparatos son creados en base a los textos científicos (aquello que mató por completo las imágenes según el mismo texto), por lo tanto, las imágenes técnicas son pequeños derivadas de los textos técnicos, siendo mil veces más abstractas por venir de los conceptos (aquellos que destruyen trabajos de diseño ヽ( `д´*)ノ). Y aunque pareciera que quieren mostrar la realidad de una forma objetiva, al final todo queda a libre interpretación, porque ya de por sí las imágenes tradicionales tienen sus interpretaciones en base al autor, pero con las técnicas, aunque pareciera que hay algo... todo es ilusión de quien la interpreta.

El problema es que las personas suelen percibir estas imágenes como una “ventana al mundo” y confían en ellas sin cuestionarlas. Sin embargo, entre la realidad y la imagen existe una especie de “caja negra” (como lo hablamos en clase woaos) cuyo proceso permanece oculto. Estas imágenes no muestran el mundo directamente, sino conceptos transformados, comprimidos y alterados.

Se supone que las imágenes técnicas surgieron para unir arte, ciencia y sociedad mediante un lenguaje común. Sin embargo, no cumplieron ese objetivo: reemplazaron imágenes y textos por una nueva forma de magia basada en medios y programas, transformando los acontecimientos en elementos repetibles dentro de una cultura dominada por imágenes.


*Las imagenes tradicionales son fenómenos y las tecnicas son conceptos*

## ¡Y ahora la parte 3!

Finalmente se explica qué son los aparatos.

Con el ejemplo de la cámara de fotos, donde está (como en general los aparatos), no buscan transformar el mundo mediante lo físico (como lo puede ser el arte, con las esculturas o las pinturas), sino manipular los símbolos e información mediante el acecho.

Cabe aclarar que los aparatos son parte de nuestra cultura y son identificados como: objetos culturales en donde podemos ver cultura, y con ello tenemos 2 tipos:

- los buenos para el consumo: Bienes de consumo
- los buenos para la producción: Herramientas

"Las herramientas como tales son objetos que extraen de la naturaleza otros objetos para ponerlos donde estamos, a fin de producirlos".

Para el hombre terminar rodeado de herramientas que se convirtieron en máquinas... dando así Una revolución, como lo que pasó en La Revolución Industrial.
Pero muchas de estas máquinas, incluso a día de hoy, son aquellas cajas negras que se mencionan de antes. Sabemos qué sucede por fuera, pero no por dentro. Podemos manipularlo hasta cierto punto, pero nos condiciona; por ello se entiende el ejemplo de la cámara.
*Podemos configurar ajustes de zoom, tonalidades, filtros y el almacenamiento. Pero todo hasta un punto finito.*

Al final, el conocimiento es el poder. Si somos capaces de saber cómo funcionan las cajas negras de la actualidad, podemos crear tantas cosas sin limitaciones... sería mágico.

---

*PD: encontre un foro sobre percusiones de gameboy para recrear la musica con los canales de la consola:* 

<https://www.reddit.com/r/chiptunes/comments/wlucf8/help_needed_gameboy_percussion/>
