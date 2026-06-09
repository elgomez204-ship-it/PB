# Grupos de capas en SVG con elemento `<g>`

## Introducción

SVG (Scalable Vector Graphics) es un formato de gráficos vectoriales utilizado en la web para crear imágenes escalables sin pérdida de calidad. Una de sus características más importantes es la posibilidad de agrupar elementos mediante el uso de la etiqueta `<g>`, lo que permite organizar y manipular varios objetos como si fueran uno solo.

En esta actividad se trabaja la creación de un grupo de capas con un elemento `path`, incluyendo interacción mediante eventos.

---

## Aspectos técnicos

* **Tecnología utilizada:** SVG (Scalable Vector Graphics)
* **Lenguaje:** HTML + SVG
* **Elementos principales:**

  * `<svg>` → contenedor principal
  * `<g>` → grupo de elementos (capas)
  * `<path>` → dibujo vectorial mediante coordenadas
* **Interacción:** evento `onclick` en SVG
* **Estilo CSS inline en SVG:**

  * `fill` → color de relleno
  * `stroke` → color del borde
  * `stroke-width` → grosor de línea
  * `stroke-linecap` → extremos de línea
  * `stroke-linejoin` → unión de líneas

---

## Ejemplo práctico

### Archivo: `grupo.svg`

```html id="svg_001"
<!DOCTYPE html>
<html>
<body>

<svg xmlns="http://www.w3.org/2000/svg" width="512" height="512">

    <!-- Grupo de capas -->
    <g id="layer1">

        <!-- Forma vectorial -->
        <path
            id="figura"
            d="M 124.97523,66.697113 A 56.594322,56.594322 0 0 1 81.916198,121.64903 56.594322,56.594322 0 0 1 18.260878,92.982092 56.594322,56.594322 0 0 1 30.871855,24.318009 56.594322,56.594322 0 0 1 100.55935,20.141068 L 68.380905,66.697113 Z"
            style="fill:#00ff00;stroke:#0000ff;stroke-width:12;stroke-linecap:round;stroke-linejoin:round;stroke-dasharray:none"
            onclick="this.style.fill='red'"
        />

    </g>

</svg>

</body>
</html>
```

---

## Explicación del ejemplo

* Se crea un archivo SVG con tamaño **512x512 px**.
* Se define un grupo de capas con `<g id="layer1">`.
* Dentro del grupo se dibuja una figura con `<path>` utilizando coordenadas complejas.
* El estilo define color verde de relleno y borde azul.
* Se añade interacción: al hacer clic, el color de relleno cambia a rojo.

---

## ¿Para qué sirve?

El uso de grupos en SVG sirve para:

* Organizar elementos gráficos complejos.
* Aplicar transformaciones a varios elementos a la vez.
* Crear interfaces gráficas interactivas.
* Diseñar iconos, mapas o ilustraciones vectoriales.
* Añadir interactividad en páginas web.

---

## Conclusión

El uso del elemento `<g>` en SVG permite estructurar y organizar gráficos vectoriales de forma eficiente. Combinado con `<path>` y eventos como `onclick`, se pueden crear gráficos interactivos dentro de páginas web. Esta técnica es fundamental en el desarrollo de interfaces modernas, visualización de datos y diseño gráfico web.
