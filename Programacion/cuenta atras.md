# Temporizador con diferentes formatos y estilos en JavaScript

## Introducción

Un temporizador es una herramienta fundamental en el desarrollo web que permite medir el tiempo de forma progresiva o regresiva. En este ejercicio se implementa un temporizador regresivo utilizando JavaScript, el cual cuenta hacia atrás desde 10 minutos. Este tipo de funcionalidad es común en aplicaciones como exámenes en línea, juegos, sistemas de control de tiempo y procesos automatizados.

---

## Aspectos técnicos

* **Tecnologías utilizadas:**

  * HTML (estructura)
  * CSS (estilo visual del temporizador)
  * JavaScript (lógica del temporizador)
* **Funciones principales:**

  * `setTimeout()` → ejecuta una función después de un tiempo determinado
  * `clearTimeout()` → detiene la ejecución del temporizador
  * `textContent` → actualiza el contenido visual en pantalla
* **Variables principales:**

  * `tiempo` → almacena el tiempo restante en segundos
  * `temporizador` → controla la ejecución del bucle

---

## Ejemplo práctico

### Archivo: `temporizador.html`

```html id="timer_001"
<!DOCTYPE html>
<html>
<head>
    <title>Temporizador regresivo</title>

    <style>
        body {
            font-family: Arial;
            text-align: center;
            margin-top: 100px;
            background: #f4f4f4;
        }

        #tiempo {
            font-size: 60px;
            font-weight: bold;
            color: #ff3b3b;
            margin: 20px;
        }

        button {
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
        }
    </style>
</head>

<body>

<h1>Temporizador Regresivo</h1>

<div id="tiempo">10:00</div>

<button id="boton">Iniciar</button>

<script>

// Tiempo en segundos (10 minutos = 600 segundos)
let tiempo = 600;
let temporizador;

const boton = document.querySelector("#boton");

boton.onclick = function () {
    temporizador = setTimeout(bucle, 1000);
};

function bucle() {

    tiempo--; // Restar un segundo

    let minutos = Math.floor(tiempo / 60);
    let segundos = tiempo % 60;

    // Formato 00:00
    document.querySelector("#tiempo").textContent =
        String(minutos).padStart(2, "0") + ":" + String(segundos).padStart(2, "0");

    clearTimeout(temporizador);
    temporizador = setTimeout(bucle, 1000);
}

</script>

</body>
</html>
```

---

## Explicación del funcionamiento

* El temporizador inicia en **10 minutos (600 segundos)**.
* Al pulsar el botón, se activa la función `bucle()`.
* Cada segundo se resta 1 unidad al tiempo.
* Se convierte el tiempo en formato **minutos:segundos**.
* Se actualiza el contenido del HTML en pantalla.
* Se usa `setTimeout()` para repetir el proceso continuamente.

---

## ¿Para qué sirve?

Este tipo de temporizador se utiliza en:

* Exámenes online con límite de tiempo.
* Juegos con cuenta regresiva.
* Sistemas de control de procesos.
* Aplicaciones de productividad.
* Alarmas o recordatorios web.

---

## Conclusión

El desarrollo de un temporizador con JavaScript permite comprender el manejo del tiempo en aplicaciones web. El uso de funciones como `setTimeout()` y la manipulación del DOM hacen posible crear herramientas dinámicas e interactivas. Este tipo de ejercicios es fundamental para fortalecer habilidades en programación web y desarrollo de interfaces funcionales.
