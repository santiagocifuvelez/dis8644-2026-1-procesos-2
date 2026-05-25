# sesion-10b

Trabajo. trabajo y trabajo! (｡- ω -)

Para esta clase, lo importante era la planeación de las cosas

- ¿Cual de todos los ejemplos vamos a hacer?
- ¿Como los vamos a modificar?
- ¿Está a nuestro alcance para poder hacer un prototipo con las cosas que hay en Chile?
- ¿Es realizable?

Entre todos esos parametros se realizó el siguiente percutor:

<https://hackaday.com/2015/03/25/logic-noise-filters-and-drums/>

![badumss](./imagenes/drums.png)

Al no tener en primer lugar los chips (Mayormente por el feriado del jueves) se nos ocurrío simular el circuito para ver si era realizable

Esté lo hice yo!

♡＼(￣▽￣)／♡ ya que me encanta hacer los esquematicos por alguna razón...peeeeeeeeeeero

Pensamos hacerlo en TinkerCad pero este no contenía los chips a utilizar: 

- 4019
- 4069

Por lo que fuí a la otra pagina que nos recomendó Missa:

www.falstad.com 

![pagina que no es tinkercad](./imagenes/falstad.png)

Este es el link

[Simulación en Falstad](https://www.falstad.com/circuit/circuitjs.html?ctz=DwYwlgTgBAZgvAIgIwKgFwM6IAwDpsHZICsAbAEzGpgg64AcAzAOzn0CczALPfUua1KlUIAEaIkzVAAdxCYtlQA3CIipQAtpjUBTALRIUAPgBQUKMGlooADwlcuUUo6TtyURuVTxkqDQEMJQgIZAHs6dhJ6YJiCFCgMABtEACUdDDAMNH8AOxAdBAB6U3NQW0RnKCQHJxdmYVgcEToY+LAlFqJUDFUERSglABMJXGZIgWZsXl5GQy4pYrMLEHKERmwXfg9id0MvRr7m5HxY06J9KSh2zviepoHh+VwSea52UnZGHlIidiKSixWVaMUj0Kr1KBcAhQcjkLjeCR+QLIGJhOjqJKpdKZbJ5AqLUorOwIAS7CHrOoNHz9WjHDYXagdPonW69fpDRDkXBsdjYYjEByUL5cRj-JZlYkismkSGVSRU+60pAnM6tBlXJl4OLdNnKR56PAvbjvT7fX5i0pA4lw7Aw3h2sGUBW+TTIpCoqDScLMnacVXahLJBBpDJZXL5C2A6ySzwOyHRGFkBEugJBYJon3dIMhnHh-EAiWIEGO+3Fjzkfo+fa0rnkdXXZkBu6HB6c55IXjvJCkZi9kUOSPAACSq1hjgcYIpkJ4yf6mMzUAAFmA1IOR8TGPRHMQtlxKjv9tSs+jUMvVwSLABzVaVCtg29Q2eD6AbjbTydb99PqC9d3pi-AC+iBQraPCgQmYHfr+qIAUSwHdpCsZ7uOnjfkq+j0IyNw6vcHIIAauCzMQnCUPQpBIOszAKH8AEAO43pStQwlMT50QxVQ1HK-CsQW9HElx7iVM4PHinxiDvFUMrypJImlGJJKsFUWxTnsskWPJd5MaStRqcA8ndraexVG4SmHk0bHEtJsbSd2un6RCCGabZByKBZRY7KZHigqZdnAt5RllvKvmvoxgX1MFwHWeS-nhS5g7ych4IygeSURQgbwymwYIpVlaUpdJOW8GliVOpCElOsV5VkGVmVFXFblrN5WWIe4uX1bxwJvs1ZZtUeDXaaVU4Ve1omdY4g1dXVfUddainSWOqUjXJo5wnGC0TnlWzNSlxabe4ZYpSBe2QtCU5HUt6ljSdtpnTOF16cCn47Z+G33QlCFSh4L2oW9j0oftL13dNo2Svuu4JgexUQdDtqQ79oP-fGoE-cDy2ShBSEw7p14bk1UJeY6Sb3TjRbeYwIIE9sZmHA1ZaeDdZMgmlNpratvXmTNwEQ1sxAQnDqOXbNgnjYp0TM6Lhk-FAYvwxIUsJgZPmy+l0KaSBMKPsr6ssz1msC8A-ihAArtGah81sziw9xcVQIMRuIgkyLRCEUCJG68WrNUmy7FLqnKwtzULUFWvQmB11fiHoE8F945AxzIPiVJMpys6rmcwgKdMcJ91DjkSg6BAaBgDkl4AMogIuGhgGgpsZ97HHe9+SRsrg6iJGgIxCKgJtFoRoqu6EOSrgPMD67n+eF8XZcV1XNeeyZRnaX7R6Bi3bcd8cXdQD3ax96giSD8PB+j-HpShFAOhDyStzSBU8IHDY-e34cAKWgM9wYLSVAXm-TL95-nQCCcFIGQSgg5CihALOfS+wFLgYGfu6OEyZH4yERK-QE78WwAPkJGX+RZui0i1IQYBoDv4FggaYYAhRwAQFMEAA)

(Si el link es extremadamente largo en el codigo base es porque la pagina, aún dando la opción de hacer una URL más corta, está rota...por lo que bueno, se vera un poco relleno por debajo de la alfombra)

---

Mientras esto sucedía, el equipo vió cuales condensadores ceramicos eran los necesarios 

![condensadores ceramicos](./imagenes/ceramico.png)

- Siendo los 103, los 104 y los 224

| Código | Valor en pF | Valor en nF | Valor en µF |
|----------|------------|------------|------------|
| 101 | 100 pF | 0,1 nF | 0,0001 µF |
| 102 | 1.000 pF | 1 nF | 0,001 µF |
| 103 | 10.000 pF | 10 nF | 0,01 µF |
| 104 | 100.000 pF | 100 nF | 0,1 µF |
| 222 | 2.200 pF | 2,2 nF | 0,0022 µF |
| 224 | 220.000 pF | 220 nF | 0,22 µF |

---

Con ello listo, se armó un pequeño prototipo con la ayuda de Claude para cambiar ciertos componentes: 

<https://claude.ai/share/8e046c83-2591-44ab-91de-587412d54970>

Y como era de esperarse...no funcionó. Pero de eso se trata este taller 	(￣ヘ￣)

---

Entonces viene mi segunda parte favorita! HACER MÁS ESQUEMATICOS JIJIJIJIJI.

Me ofrecí a hacerlo porque me agrada...me gusta y me fascina

*Arriba en el documento esta subida la versión v1 y saben que otra cosa es v1?*

![vee](./imagenes/vee-v1.gif)

Pero al caso:

![orden total](./imagenes/esquematico.png)

Aquí presento la primera versión que tiene pequeñas anotaciones para cambios futuros que ire actualizando tanto para el grupo como para mi mismo 

![primeros cambios](./imagenes/uno.png)

![exito](./imagenes/pasos.png)

Y esto ultimo son los pasos a seguir en cada modelo que vamos a ocupar...eso por el momento. <3
