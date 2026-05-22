# sesion-10a
12 de mayo del 2026 

¡Hola profe Aaron, Misa y Emi!, volvimos del holiday break, y es momento de refrescar y retomar lo ya aprendido en clase. 
La clase de hoy fue un repaso + un agregado de súper valor…, Así que veamos que tenemos para hoy:

> Primeramente, siempre partimos con estos pasos en orden:  
> 1.	Dibujar esquemático (.Kicad_sch)
> 2.	Asociar huella a símbolos 
> 3.	Abrir PCB new (para crear la PCB), interprete del esquemático
> 4.	Definir tamaño de las pistas 
> 5.	Repartir componentes físicamente 
> 6.	Rutear componentes
> 7.	Ornamentar y exportar fabricación.

Ya con estos pasos en cuenta, continuemos con la clase:  
1.	Como abrir archivos de trabajo. 
2.	Atajos de teclado.
3.	La pcb (nuestra placa real)
4.	Encargo para la siguiente clase.

## 1.	Como abrir archivos de trabajo. 
Cuando un archivo ya está creado y guardado, se abre desde la extensión:   
`.Kicad_pro`, ya que es todo el proyecto:

![kicadpreee](https://github.com/santiagocifuvelez/dis8644-2026-1-procesos-2/blob/main/08-santiagocifuvelez/sesion-10a/imagenes/img1.png)

## 2.	Atajos de teclado.

|Tecla (atajo)|Lo que hace|
|-------------|-----------|
|**`A`**|Abrir tabla para agregar componentes |
| *Puedes buscar los símbolos que solemos usar +, así:* | `R = Resistors`  |
|                     |`C = Unpolarized capacitor`|  
|                     |`Gnd = Ground (tierra)`|  
|                     |`Vcc = Voltaje corriente continuo (Cielo)`|  
|                     |`NE555P = Chip 555` | 
|                     |`R_pot = Potenciómetro`|  
|                     |`Led = Led`|  
|                     |`Battery_cell = Batería`|   
|                     |`Speaker = parlante`  
|**`ESC (escape)`**| Para deseleccionar todo, y tener el cursor libre para seleccionar u hacer otras cosas.|
|**`R`**| Rotar componente 360. |
|**`X`**| Mirror componente en el eje X. |
|**`Y`**| Mirror componente en el eje y. |
|**`M (move)`**| Mover solo componentes sin cables (igualmente te aparecerá un warning cuando esto suceda). |
|**`G (grab) `**| Mover todo lo seleccionado con el mouse; aquí si se mueve todo lo que selecciones; cables, textos, etc. |
|**`E`**| Editamos el valor, y varias propiedades de un componente. | 
|**`V`**| Podemos escribir/cambiar los valores a los componentes. | 
|**`Ctrl + S`**| **Save (SIEMPRE HACER CTRL + S).** | 
|**`Ctrl + D`**| Duplicar | 
**`Ctrl + Z`**| Volver atrás  | 

> *Antes de pasar a la placa PCB, debemos dejar en claro las “Huellas” (footprints); pues estas son prácticamente el sentido de vida de nuestras placas, ya que ellas son el estado físico, real, y tangible de nuestros componentes en la vida real.*

> *Entonces, primeramente, siempre asegurarnos de las medidas de nuestros componentes y ponerlos en coherencia con el que corresponda.*

## 3.	La pcb (nuestra placa real)

**Primeramente, know your grids (grillas), vamos a usar 5mm para nuestras placas, ya que es un grosor perfecto.**
![img2](https://github.com/santiagocifuvelez/dis8644-2026-1-procesos-2/blob/main/08-santiagocifuvelez/sesion-10a/imagenes/img2.png)

 **Además, siempre se debe hacer los contornos de las placas, en la capa de edges.cuts:**
![img3](https://github.com/santiagocifuvelez/dis8644-2026-1-procesos-2/blob/main/08-santiagocifuvelez/sesion-10a/imagenes/img3.png)

**Listo, ahora que ya hicimos el contorno de nuestra placa, sigue definir los caminos de conexiones (las pistas):**
![img4](https://github.com/santiagocifuvelez/dis8644-2026-1-procesos-2/blob/main/08-santiagocifuvelez/sesion-10a/imagenes/img4.png)

En Kicad, puedes escoger el tamaño de las pistas para que fluya más o menos energía por ciertos caminos.  
Antes de continuar, quiero hacer mención de que hay posibilidades muy específicas con las que podemos trabajar: Por ejemplo, la capacidad mínima de pista, es de 0.10mm / 0.10mm (4 / 4 mil). En kicad se puede hacer de menos, pero al momento de esta ser realizada en china, no la van a leer.

También existe un espaciado mínimo entre pistas, para que no se toquen las unas con las otras.
(En cualquier caso, más de 0.3mm es lo mejor).

**Para hacer las pistas, las encontramos aquí:**
![img5](https://github.com/santiagocifuvelez/dis8644-2026-1-procesos-2/blob/main/08-santiagocifuvelez/sesion-10a/imagenes/img5.png)

**Luego se nos despliega esto, y aquí podemos poner las anchuras de nuestras pistas. Ya luego de eso, nos van a aparecer como “pinceles”, con las anchuras que hicimos.**
![img6](https://github.com/santiagocifuvelez/dis8644-2026-1-procesos-2/blob/main/08-santiagocifuvelez/sesion-10a/imagenes/img6.png)

**Y primero, comenzamos a organizar los componentes en el contorno que creamos:**
![img7](https://github.com/santiagocifuvelez/dis8644-2026-1-procesos-2/blob/main/08-santiagocifuvelez/sesion-10a/imagenes/img7.png)

**Luego de haber organizado los componentes en la placa, podemos hacer nuestras pistas, en estas dos capas: `F.cu` (front). y `B.cu` (back)**
![img8](https://github.com/santiagocifuvelez/dis8644-2026-1-procesos-2/blob/main/08-santiagocifuvelez/sesion-10a/imagenes/img8.png)

**Luego le hundimos enrutar pista única (o podemos oprimir la letra x):** 
![img9](https://github.com/santiagocifuvelez/dis8644-2026-1-procesos-2/blob/main/08-santiagocifuvelez/sesion-10a/imagenes/img9.png)

**Luego, cuando le hundimos nos aparecen todos los lugares donde debería ir conectado ciertas pistas:**
![img10]()

## 4.	Encargo para la siguiente clase.
