# sesion-12a

Martes 2 de junio

En esta clase nos dividimos para avanzar mejor. Una parte del grupo trabajó en mejorar el piezo 01, mientras que otros nos enfocamos en hacer funcionar el piezo 02. Para esto, agregamos el condensador cerámico 105 que habíamos comprado con Benjamín el día anterior, y así logramos que por fin funcionara.

Aun así, seguían los problemas, el LED se encendía, pero poco a poco se iba apagando. Entonces nos recomendó Misa y Kiki que fuéramos probando con condensadores polarizados diferentes, y eso lo solucionó (1 µF por 100 µF). El LED dejó de apagarse y ahora se ilumina más cuando golpeamos el piezo.

![foto](./imagenes/olagif.gif)

(gif compartido por Bruno)

Después armamos un amplificador para probar todo el sistema. El parlante sonaba constantemente y solo cambiaba un poco al golpear el piezo. Nos dijeron que al final habíamos hecho un oscilador Σ(°ロ°) y en verdad estabamos todos perdidos con este circuito, no supimos qué pasaba ya que seguimos el esquemático dado y aún era un flop, por lo que nos enfocamos en avanzar en las PCB y en los esquemáticos finales del proyecto en lo poco que quedaba de clase.

En el piezo 01, se trabajó en mejorar su sensibilidad utilizando un circuito amplificador, con el objetivo de que pudiera activarse sin necesidad de tocarlo directamente. Para esto, se siguió el esquema del amp de PimPom.

![foto](./imagenes/preamp.png)

Nuestros compañeros le preguntaron a Misa qué componentes podíamos cambiar para que el piezo detectara mejor las vibraciones. Les comentó que podíamos jugar con los valores de las resistencias R4 y R5, ya que mientras más diferencia haya entre ellas, mayor sensibilidad tendrá el circuito.

Se reemplazó R4 por una resistencia de 47 Ω y mantuvimos R5 en 100K Ω.

Con estos cambios, el piezo logró detectar golpes incluso a varios centímetros de distancia cuando estaba adherido a una mesa o pared. Además, también fue capaz de percibir vibraciones en el cuello de las personas ৻(  •̀ ᗜ •́  ৻) muy prooooo

![foto](./imagenes/01piezo.gif)

![foto](./imagenes/voz.jpg)

(gif e imagen compartido por Bruno y Nico hablando en dirección al piezo)
