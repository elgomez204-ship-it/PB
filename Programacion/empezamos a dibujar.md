# Dibujando formas en HTML5 Canvas

## Introducción

El elemento **Canvas** de HTML5 permite crear gráficos dinámicos mediante JavaScript, utilizando un lienzo virtual dentro de una página web. En esta actividad se trabaja la creación de formas básicas, como rectángulos, lo cual es fundamental para el desarrollo de gráficos, videojuegos, interfaces interactivas y visualización de datos.

---

## Aspectos técnicos

* **Tecnologías utilizadas:**

  * HTML5 (estructura)
  * JavaScript (lógica de dibujo)
* **Elemento principal:** `<canvas>`
* **Contexto gráfico:** `getContext("2d")`
* **Funciones principales:**

  * `fillRect()` → dibujar rectángulos rellenos
  * `fillStyle` → color de relleno
  * `strokeStyle` → color del borde
* **Dimensiones del lienzo:** 512x512 px

---

## Ejemplo práctico

### Archivo: `forma.html`

```html id="canvas_001"
<!DOCTYPE html>
<html>
<head>
    <title>Dibujo en Canvas</title>
</head>
<body>

<canvas id="lienzo" width="512" height="512"></canvas>

<script>

// Obtener el canvas
const canvas = document.getElementById("lienzo");

// Obtener el contexto 2D
const contexto = canvas.getContext("2d");

// Estilos
contexto.fillStyle = "skyblue";
contexto.strokeStyle = "black";

// Dibujar rectángulo (x, y, ancho, alto)
contexto.fillRect(40, 40, 60, 60);

// Dibujar borde del rectángulo
contexto.strokeRect(40, 40, 60, 60);

</script>

</body>
</html>
```

---

## Explicación del ejemplo

* Se crea un lienzo de **512x512 píxeles**.
* Se obtiene el contexto 2D para poder dibujar.
* Se define un color de relleno (`skyblue`) y un borde negro.
* Se dibuja un rectángulo en la posición **(40,40)** con tamaño **60x60 píxeles**.
* Se añade un borde para mejorar la visualización de la forma.

---

## ¿Para qué sirve?

El uso de Canvas para dibujar formas sirve para:

* Crear gráficos interactivos en páginas web.
* Desarrollar videojuegos 2D.
* Visualizar datos de forma gráfica.
* Diseñar interfaces personalizadas.
* Aprender conceptos básicos de gráficos por computadora.

---

## Conclusión

La práctica de dibujo en Canvas permite comprender cómo funcionan los gráficos en HTML5 mediante JavaScript. El uso de funciones como `fillRect()` y propiedades como `fillStyle` facilita la creación de formas básicas que sirven como base para proyectos más avanzados como animaciones, juegos o visualización de datos en tiempo real.
