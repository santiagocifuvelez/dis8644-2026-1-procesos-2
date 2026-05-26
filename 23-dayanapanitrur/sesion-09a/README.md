# sesion-09a

Esta clase fue online por el incendio ocurrido en el edificio contiguo a la facultad.

Me di cuenta de lo mucho que extrañé y necesité una sala de clases, aunque las sillas sean incómodas. Estuve demasiado distraída esta clase, por lo que pude tomar apuntes vagamente y terminé valorando aún más el encuentro en el espacio físico.

---

Seguimos con los pasos pendientes, anteriormente vimos del 1 al 3. Hoy del 4 al 7:

## **4. Definir contornos y tamaño de pistas**

Para tener consideración con la manipulación de nuestras pcbs hay una recomendación por parte de Misaa, que es el redondear las puntas de los bordes. Al momento de crear este rectángulo en Edge.cuts se le puede dar la propiedad de redondear bordes.

Entre más pequeñas y comprimidas sean nuestra PCBs, más baratas serán de producir. 

Las pistas son estos caminos de cobre que pueden estar tanto por el frente como por detrás de la placa. Podemos darle diferente grosor a estas pistas dependiendo de cuanta energía queramos dar a ciertos elementos. Entre más grande las pistas, más energía es la que pasa. El rango de estas pistas desde la más delgada hasta la más gruesa está entre 4mm-8mm.

Espaciado 5mm.

## **5. Repartir componentes físicamente**

Está en nuestro criterio qué elementos queremos dejar accesibles y consideramos importante establecer en ciertos lugares específicos de la PCB.
Las líneas aéreas nos indican las conexiones que tienen estos componentes, lo cual nos sirve para guiarnos al momento de realizar las pistas.

En propiedades (E) nuevamente podemos ver detalles de nuestros componentes y de qué posición queremos darle a estos. Por ejemplo X e Y son la posición y en Orientación podemos ajustar en cuantos grados puede estar el componente.

La F.cu es la capa de cobre frontal(Front) y la B.cu es la capa de cobre trasera(Back).

## **6. Rutear**

Las pistas por supuesto no se pueden cruzar entre sí, por lo menos no desde la misma cara. Para esto existen las vías (V) al momento de rutear nuestras pistas. Es la forma en la que una pista cambia desde una cara hacia la contraria para no cruzarse con otra, Misaa lo describe como "ir tejiendo la placa", lo cual es muy bonito.

Lo último que queda es la conexión a Ground. Esto finalmente lo podemos hacer con la herramienta *Dibujar zonas rellenas*, en la cual debemos indicar qué vamos a rellenar (F.cu y B.cu) y con qué red: en este caso GND, lo cual nos generará un espacio inmenso de tierra en todos estos lugares vaciós de la placa (con **B** lo cerramos).

Se generaron unas pequeñas patitas hacia los componentes que se conectan a GND. Estas pequeñas conexiones se llaman alivios térmicos.

## **7. Ornamentar**

Una desición de diseño clave es el pensar en cómo será la sujeción de la placa a una carcasa o a lo que sea que la va a contener. Para esto, desde el esquemático podemos colocar como componente un orificio: **Mounting Hole**. Y colocar uno en cada esquina para colocar un perno 3m por ejemplo, uno de los más estándar y más fáciles de encontrar en el mercado. En **asociar huellas** le damos el valor al orificio.

En la capa .Silkscreen se pueden colocar dibujos y textos para ornamentar nuestras placas. Todo mientras sea vectorial y se pueda exportar en svg o dxf.
