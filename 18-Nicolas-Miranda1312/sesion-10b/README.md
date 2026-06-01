# sesion-10b

22-05-2026

## Trabajo en Clases – Proyecto 2

Continuamos trabajando con el referente compartido por Misa:

## Referente
**Logic Noise: Filters And Drums** – Elliot Williams  
<https://hackaday.com/2015/03/25/logic-noise-filters-and-drums/>

## Resumen

El artículo forma parte de la serie *Logic Noise* de Elliot Williams, publicada en Hackaday, y explora la creación de sintetizadores analógicos y generadores de sonido utilizando circuitos lógicos CMOS, especialmente chips de la serie 4000 como el **CD4069UB** y el **CD40106**.

El enfoque principal consiste en demostrar cómo es posible generar y moldear sonido a partir de componentes electrónicos simples, utilizando filtros para modificar las características de las señales producidas por estos circuitos.

## Esquemático y pruebas en protoboard

- Se intentó replicar el esquemático de referencia en protoboard.
- Debido a la falta de algunos componentes, se realizaron reemplazos con equivalentes disponibles.

![esquematico4069](./imagenes/esquematico4069.png)

### Componentes utilizados

- 10 μF
- 0,01 μF → capacitor marcado como **103** (10 nF).
- 0,1 μF → capacitor marcado como **104** (100 nF).
- 0,22 μF → capacitor marcado como **224** (220 nF).

### Sustitución de componentes

- El circuito original utiliza un **CD4069UB**.
- Se reemplazó por un **CD4069BE** debido a la falta del componente original.
- La implementación física en protoboard no funcionó como se esperaba.
- Carla realizó una simulación del circuito en Falstad utilizando el mismo esquema, obteniendo resultados funcionales.

![falslad4069](./imagenes/falslad4069.png)

### Observaciones

- Misa recomendó revisar los amplificadores operacionales **TL074** y **TL072**.
- Sin embargo, ambos requieren alimentación positiva y negativa para funcionar correctamente.
- Debido a la complejidad adicional que implica trabajar con fuentes simétricas, se recomendó no utilizarlos en esta etapa del proyecto.
