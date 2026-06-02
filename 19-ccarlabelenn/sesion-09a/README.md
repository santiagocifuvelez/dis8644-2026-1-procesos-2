# sesion-09a

12 de mayo (clase online porque o si no quedabamos ahumados bu)
---
> se hizo mención a Bonvallet, me dio demasiada risa porque ultimamente hago muchas tallas con elocuencias que decía este sujeto y le hago mucho retweet porque era muy relatable a veces. 
![imagenes](./imagenes/bonvallet.jpeg)

## repasar KiCad 
+ repasamos los primeros 7 pasos que vimos la clase antes del feriado y receso. KiCad tiene al menos dos softwares principales:
- **esquemático**: donde se diseña el circuito lógico
- **editor de placas (PCB)**: donde se diseña el componente físico

>  cada componente es un mundo, tienen un montón de propiedades. 

## repaso de atajos de teclado — esquemático

| tecla | acción |
|-------|--------|
| `a` | agregar un componente |
| `r` | rotar |
| `m` | mover |
| `g` | grab — mover con todo (mantiene conexiones) |
| `v` | valor — abre el menú que edita el cambio de valor |
| `e` | hoja de vida del componente (propiedades) |
| `ctrl + S` | guardar |

> - **tamaño lámina**: doble click para cambiar
> - **huella**: espacio físico que ocupa cada componente
> - **nunca asumir nada**: ctrl + s 

## flujo PCB — editor de Placas

### pasos para diseñar como componente físico:

1. abrir KiCad (siempre abrir **KiCad Pro**)
2. cambiar al **editor de placas**
3. click en **"traerme"** para importar el esquemático
4. presionar **F8** → *actualizar placa desde esquema*
5. **alt + 3** → visor 3D

## contorno de la placa (Edge.Cuts)

- la placa necesita un lugar físico. ese es nuestro **contorno**
- para dibujarlo hay que estar en la capa **`Edge.Cuts`**
- dibujar líneas para formar el contorno

### medidas de ejemplo:
| uso | tamaño |
|-----|--------|
| Contorno básico | 5x9 cm |
| Tarjeta de presentación | 90x40 mm |

### tips para el contorno:
- generar **arcos de 5mm de radio** en las esquinas
- usar la **herramienta arco**, encontrar punto
- tecla `E` en un rectángulo da opción de **redondear rectángulo** 

## PCB — capas y elementos

- **pista**: por donde viaja la señal eléctrica
- **via**: es un pequeño agujero metalizado que conecta eléctricamente dos capas distintas de la PCB.

> me perdí

## encargo 09a

