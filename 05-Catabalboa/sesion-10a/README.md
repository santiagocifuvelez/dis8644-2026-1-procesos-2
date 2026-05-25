# sesion-10a
Clase martes 12 de mayo (Clase online por el suceso del incendio)

en esta clase partimos haciendo un repaso de lo que habiamos visto la clase pasada sobre kicad y tambien resolviendo dudas que nos pudieron haber quedado. 

## Atajos de teclado

| Atajo | Qué hace |
|-------|----------|
| A | Agregar componente |
| R | Rotar componente |
| G | *Grab* — mueve el componente arrastrando los cables conectados |
| M | Mover (sin arrastrar cables). Primero **Esc** para volver al modo selección, clic en el componente y luego **M** |
| E | Editar propiedades |
| V | Asignar valor a un componente/cambiar de capa cobre frontal a la de atrás (en PCB) |
| X | Reflejar en eje X |
| I | Reflejar en eje Y |
| Esc | Herramienta de selección |
| Ctrl + D | Duplicar componente |
| Ctrl + Z | Deshacer |
| Alt + 3 | Abrir visor 3D |

Repasamos el tema de los componentes y algo que rescate de este repaso fue: 

* Se puede buscar por nombre, por ejemplo, LED, VCC, GND, ect.
* Si algo queda sin conectar hay que ponerle si o si la X de no conexión.

tambien repasamos algunas cosas sobre las huellas:

* Son el estado fisico del componente, esto quiere decir que es como va a quedar en la placa
* Si algo esta mal por consiguiente todo estará mal
* Nombre sigue formato: Tipo de componente/variante especifíca)

## PCB y diseño de placa

Para una configuración inicial es recomendado una grilla de **5 mm** y para dibujar en la placa siempre en la capa llamada **Edge.cuts**, es importante no dibujarlo en otra capa. Luego para un contorno, es decir, las esquinas redondeadas, tenemos dos caminos en el cual uno es la herramienta de arco en la que primero se marca el centro y luego el inicioy termino del arco, como segundo camino podemos dibujar un réctangulo, luego seleccionarlo y presionar **E**, activar la opcion ''rectandulo redondeado'' y poner **5 mm** de radio.

ahora pasemos a hablar de las pistas que serian los caminos de cobre, estos son los ''cables'' de la placa y pueden ir en cualquier lado según nuestro críterio, el grosor de las pistas dependerá de cuánta corriente necesitará pasar, esto quiere que decir que para VCC tendría que ser más grueso, de **8 mm** o más. En las señales pueden ser más delgadas **4 mm**

> como criterio de diseño tener en cuenta el positivo hacia arriba, orientación de componentes

Pasamos a hablar ya de las vías, estas permiten conectar ambos lados de la placa, esto en caso de que no nos deje pasar una pista sobre otra, para esto sirve las vías. Esto se hace dibujando una pista y luego de aprieta el atajo de **V** para cambiar de lado y asi dejar una via en ese punto que queramos. 
También es importante mencionar que el GND en el plano de cobre no conectamos pista a pista; es decir que seleccionamos ambas caras de la placa y hacemos que toda la placa sea GND como plano de cobre, y posteriormente para que se rellene ocupamos **B** de Bold.
Nuestra placa también neceitas agujeros de montaje, y esto se hace desde el esquemático en donde debemos agregar el componente **MountingHole**, luego ubicarlo en la placa como cualquier otro componente

> para importar gráficos DXF o SVG hay que ir a archivo > importar > Gráficos. Es importante que los coloquemos o estén en una capa de serigrafia, es decir **Silkscreen** y no en la de cobre

