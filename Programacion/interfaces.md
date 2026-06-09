# Practicar la modificación de colores en imágenes con PIL

## Introducción

El procesamiento de imágenes es una parte fundamental en la programación, especialmente en áreas como edición de imágenes, visión por computadora y aplicaciones multimedia. En esta actividad se utiliza la biblioteca **PIL (Python Imaging Library)** para modificar los colores de una imagen aplicando el efecto negativo, lo que transforma visualmente la imagen invirtiendo sus colores.

Este tipo de ejercicios también se relaciona con actividades cotidianas como el trabajo creativo y el uso de imágenes en proyectos personales o de entretenimiento, como ver películas o editar contenido visual.

---

## Aspectos técnicos

* **Lenguaje utilizado:** Python
* **Biblioteca utilizada:** PIL (Pillow)
* **Conceptos clave:**

  * Manipulación de píxeles
  * Modelo de color RGB
  * Inversión de colores (efecto negativo)
* **Funciones principales:**

  * `Image.open()` → abrir imagen
  * `putpixel()` → modificar píxeles
  * `save()` → guardar imagen

---

## Ejemplo práctico

### 1. Código en Python

```python id="pil_001"
from PIL import Image

# Abrir la imagen
imagen = Image.open("imagen.jpg")

# Obtener dimensiones
ancho, alto = imagen.size

# Recorrer cada píxel
for x in range(ancho):
    for y in range(alto):

        r, g, b = imagen.getpixel((x, y))

        # Invertir colores (efecto negativo)
        nuevo_color = (255 - r, 255 - g, 255 - b)

        # Aplicar el nuevo color
        imagen.putpixel((x, y), nuevo_color)

# Guardar la imagen modificada
imagen.save("modificado.jpg")

print("Imagen procesada correctamente")
```

---

## Ejemplo de funcionamiento

* Se abre una imagen original.
* Se recorre píxel por píxel.
* Cada color RGB se invierte:

  * 255 → 0
  * 0 → 255
* Se genera una nueva imagen con efecto negativo.

---

## ¿Para qué sirve?

Este tipo de procesamiento sirve para:

* Editar imágenes automáticamente.
* Crear filtros visuales.
* Desarrollar aplicaciones de diseño gráfico.
* Trabajar en visión por computadora.
* Aprender manipulación de datos a nivel de píxeles.

---

## Conclusión

La modificación de imágenes con PIL permite comprender cómo se representan los colores a nivel de píxel. Aplicar un efecto negativo ayuda a reforzar conceptos de manipulación de datos y procesamiento de imágenes, habilidades muy útiles en el desarrollo de software multimedia, inteligencia artificial y diseño digital.



echo "# PB" >> README.md
git init
git add README.md
git commit -m "1"
git branch -M main
git remote add origin https://github.com/elgomez204-ship-it/PB.git
git push -u origin main