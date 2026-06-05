# sesion-11b

# Apuntes 29/05

Cuando llegué a la sala Aarón me contó que estábamos limpiando la sala ya que desde inicios de semestre hay residuos de materiales de los cuales nadie se ha hecho cargo, pero como llegué un poco justo a la hora de inicio de clases solo alcancé a dejar en el reciclaje unos cartones por lo que no hice mucho aporte, pero me alegró ver que todos estaban ayudando!!

Una vez ya partimos la clase, nos dedicamos a seguir revisando el circuito de la alternativa 02 (el que la clase pasada no funcionó), pero como no lográbamos entender cuál era el problema le tuvimos que pedir ayuda a Misa. Cuando Misa nos revisó el esquemático, se dio cuenta de que había cosas extrañas, por lo que pidió que le enviemos el archivo de KiCad por discord y nos respondió lo siguiente:

![Respuestas de Misa por ds](./imagenes/respuesta-misa-1.png)

![Respuestas de Misa por ds](./imagenes/respuesta-misa-2.png)

Gracias a esto, pudimos arreglar el esquemático del piezo 02 pero de igual manera Misa nos recomendó seguir el esquemático original de Hybrida para evitar errores.

Mientras mis compañeros trabajaban en la protoboard siguiendo el esquemático para el piezo 02, con bruno estuvimos aplicando el regulador de voltaje que nos entregaron en la clase anterior al circuito del piezo 01 en la protoboard, el cual tiene el siguiente esquemático:

[Esquemático regulador de voltaje estándar](./imagenes/regulador-voltaje.png)

Gracias a tener este circuito armado, podíamos controlar cuándo se encendía el circuito entero del piezo. Luego de armar esto, terminó la clase y cada uno tenía cosas que hacer por lo que no nos pudimos quedar a trabajar durante el resto del día en taller, así que decidimos reunirnos como grupo el lunes en la mañana para poder avanzar con los circuitos.

Cuando llegamos el lunes al LID, estuvimos intentando lograr hacer que el piezo del circuito 01 fuera más sensible a las vibraciones para poder lograr controlarlo con nuestra garganta, ya que la idea principal era que éste fuese un collar tipo choker para poder interactuar con el piezo mediante las vibraciones que uno provoca en la garganta cuando habla, por lo que estuvimos tratando de aumentar su sensibilidad mediante amplificadores los cuales dos de ellos nos arruinaron el circuito y dejó de funcionar XD.

Al final, logramos aumentar la sensibilidad utilizando el siguiente esquemático que encontró bruno en el siguiente link: <https://electronics.stackexchange.com/questions/348898/need-some-help-building-a-tl072-preamp-circuit>

![Esquemático pre-amp](./imagenes/preamp.png)
