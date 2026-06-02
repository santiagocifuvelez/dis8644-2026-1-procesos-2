# sesion-09b
## Referencias
- Tega Brain  
- Everest Pipkin

En esta clase vimos diferentes dudas, entre todos nos ayudamos y se resulvieron muchas que yo también tenía:) a si que esta clase fue de mucha ayuda!!!!!!!!!


##  Conceptos de PCBs
- Las PCBs se conectan de diferentes maneras a la electricidad.  
- Se pueden unir circuitos en una misma placa, pero **Aaron recomendó hacerlo por separado**, ya que cada una actúa sola.  

---

##  chips
- **Dual In-Line Package (DIP)**  
- **SOIC Package**  
- El **DIP 7.62 mm (longpads)** es el más típico y el que usaremos.  

---

## edición de símbolos en KiCad
- Seleccionar chip → tecla **E** → *Edit Symbol*.  
- Cambiar orden del chip, letra, nombre de pines.  
- Mover con tecla **M**.  
- Guardar con **Ctrl+S**.  

---

## Botones 
- **Temporales**: pulsadores, timbres, pushbuttons.  
- **Tipos**:  
  - NO (Normally Open / Abierto).  
  - NC (Normally Closed / Conectado).

 ![nonc](./imagenes/nonc.png)
 
- **Interruptores**:  
  - SPST → 2 patitas  
  - SPDT → 3 patitas  
  - DPST → 4 patitas  
  - DPDT → 6 patitas  
- **Toggle**: palanca / switch.  
- Para encontrarlos: buscar **SW_SPST** o **SW_SPDT**.  
- Asignar huella: `[Button_Switch_THT:SW_PUSH_6mm]`.  


## Bibliotecas de símbolos
- Crear carpeta propia en **Symbol Editor** dentro del proyecto `.pro`.  
- Menú: **View → Panels → Library Tree**.  
- Activar bibliotecas → **File → New Library** → guardar.  
- Copiar componente → pegar en carpeta → editar → guardar.  


## Etiquetas
- Conectar sin cableado en esquemático: tecla **L** (Label).  
- Evita error de pin no conectado.  
- Desde batería: usar etiqueta **PWG_FLAG**.  

- Cambiar de cara componentes: seleccionar → tecla **F**.  


## 3D
- Seleccionar huella en `.pcb` → tecla **E** → menú **3D Models** → cargar modelos descargados.  
- Exportar placa completa: **File → Export → STEP/STL/etc.**


## Cap 2 y 3

muestran que la fotografía no es un espejo del mundo, sino un lenguaje límitado por máquinas y sistemas industriales. En donde el fotógrafo es un quien explora las posibilidades que estan  en el programa (camara), no es totalmente libre que decide todo. La verdadera libertad estaría en subvertir el aparato, usar la cámara de una forma que no estaba previsto, romper las reglas.

Flusser dice que las imaagenes técnicas no son lo mismo que las imágenes tradicionales. Las tradicionales son prehistóricas, porque existieron antes de la escritura, y son abstracciones directas del mundo. En cambio, las técnicas son poshistóricas, porque nacen de los textos científicos aplicados. Son abstracciones: primero del mundo, luego de las imágenes, luego de los textos, y finalmente de los aparatos que producen esas imágenes. Es como una cadena: una foto es una imagen de una imagen de una imagen.

Creemos que la foto es objetiva, que muestra “la verdad”, pero en realidad es un símbolo, una construcción. La cámara es una caja negra: vemos lo que entra (la luz) y lo que sale (la foto), pero no entendemos ni controlamos la maquina, lo que pasa dentro.

Bueno,  en las cámaras de los celulares, todo esto funciona tal cual lo describe Flusser: los modos automáticos ya traen inscrito un “saber” sobre cómo debe verse la realidad, este enfoca solo, tinene modos, etc. El fotógrafo juega dentro de esas reglas, pero no completamnete libreee.
