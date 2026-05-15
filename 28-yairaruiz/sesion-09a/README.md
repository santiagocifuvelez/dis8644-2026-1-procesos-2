# sesion-09a

Apuntes de clase online — Diseño PCB en KiCad

Recordatorios:

+ Alt + 3: abrir visor 3D.
+ La capa Edge.Cuts: contorno de la PCB.
+ Se utilizarán 7 capas:
+ 1 capa de contorno: Edge.Cuts
+ 2 capas de cobre: F.Cu (frontal) y B.Cu (trasera)
+ 2 capas de silkscreen
+ 2 capas de mask
+ La parte frontal de la PCB se enfoca más en la estética, mientras que la parte trasera se relaciona más con el funcionamiento.
+ Click derecho → alinear.
+ El terminal block se utiliza para conectar la batería a la PCB.

+ Terminal block:   es un componente modular con un marco aislado que une de forma segura y ordenada dos o más cables eléctricos. Se utilizan para fijar, conectar y distribuir conductores en tableros eléctricos y dispositivos industriales. 

imagen 

## Contorno PBC

La clase comenzó con la creación del contorno de la PCB. Esto se realiza en la capa Edge.Cuts, utilizando la herramienta de rectángulo. Luego, se hace doble click sobre el rectángulo para ajustar sus dimensiones y redondear las esquinas.
El siguiente paso fue acomodar los componentes dentro del contorno creado. La idea de esta etapa es ordenar los componentes de manera estética y funcional, por lo que se recomienda ir revisando constantemente el visor 3D para observar cómo se verá la PCB físicamente.

imagen 

## Pistas 
Después comenzamos a trabajar con las pistas, que son líneas de cobre dentro de la PCB y funcionan como “cables planos”. Estas se trabajan principalmente en la capa F.Cu, que corresponde a la parte frontal, mientras que B.Cu corresponde a la parte trasera de la PCB.

imagen 

Se recomienda trabajar con dos medidas de pistas:

- 0.4 mm
- 0.5 mm

Para enrutar pistas se utiliza la herramienta de trazado de pistas, donde también se puede configurar el grosor.
Primero aprendimos a realizar las conexiones positivas utilizando pistas de 0.8 mm. Luego, usamos pistas de 0.4 mm para las conexiones entre componentes.
Cuando las conexiones se cruzan, las pistas no pueden pasar una encima de otra en la misma capa. Para solucionar esto, se puede cambiar a la capa trasera de la PCB o también utilizando una vía.

Una vía es una conexión que une la capa frontal (F.Cu) con la capa trasera (B.Cu). Mientras se está trazando una pista, si esta se cruza con otra, se puede crear una vía para continuar el recorrido por la parte trasera y así evitar cruces. Con la tecla V se puede cambiar entre la capa frontal y la trasera durante el trazado.
Si hacemos click en una vía, también es posible modificar su tamaño. 
