# Lectura y procesamiento de información desde un archivo JSON en Python

## Introducción

En la vida diaria es común interactuar con información almacenada en archivos digitales, como JSON, especialmente en aplicaciones web o sistemas automatizados. Este ejercicio se relaciona con actividades cotidianas como escribir artículos de blog o ver películas, donde la organización de la información es clave para poder consultarla fácilmente después.

En este caso, se simula la automatización de la lectura de artículos de un blog personal utilizando Python.

---

## Aspectos técnicos

* **Lenguaje utilizado:** Python
* **Formato de archivo:** JSON (`blog.json`)
* **Librerías utilizadas:** `json` (incluida en Python)
* **Funciones principales:**

  * `open()` → abrir el archivo
  * `json.load()` → cargar datos del JSON
  * `for` → recorrer los artículos
* **Estructura de datos:** lista de diccionarios

---

## Ejemplo práctico

### 1. Código en Python

```python id="json_001"
import json

# Abrir el archivo
archivo = open("blog.json", "r", encoding="utf-8")

# Cargar el contenido del archivo JSON
articulos = json.load(archivo)

# Recorrer los artículos
for articulo in articulos:

    print("Título:", articulo["titulo"])
    print("Fecha:", articulo["fecha"])
    print("Autor:", articulo["autor"])
    print("Contenido:", articulo["contenido"])
    print("-----------------------------------")

# Cerrar el archivo
archivo.close()
```

---

## Ejemplo de archivo `blog.json`

```json id="json_002"
[
    {
        "titulo": "Mi primer artículo",
        "fecha": "2026-06-10",
        "autor": "Juan Pérez",
        "contenido": "Este es el contenido de mi primer artículo de blog."
    },
    {
        "titulo": "Aprendiendo Python",
        "fecha": "2026-06-09",
        "autor": "Ana López",
        "contenido": "Hoy aprendí a trabajar con archivos JSON en Python."
    }
]
```

---

## Ejemplo de salida en consola

```text id="json_003"
Título: Mi primer artículo
Fecha: 2026-06-10
Autor: Juan Pérez
Contenido: Este es el contenido de mi primer artículo de blog.
-----------------------------------
Título: Aprendiendo Python
Fecha: 2026-06-09
Autor: Ana López
Contenido: Hoy aprendí a trabajar con archivos JSON en Python.
-----------------------------------
```

---

## ¿Para qué sirve?

Este tipo de ejercicio sirve para:

* Automatizar la lectura de datos estructurados.
* Procesar información de blogs, noticias o sistemas web.
* Mostrar contenido dinámico en aplicaciones.
* Mejorar la gestión de datos en proyectos reales.
* Preparar información para interfaces web o móviles.

En un entorno profesional, este proceso sería equivalente a leer artículos desde una base de datos o API para mostrarlos en una página web.

---

## Conclusión

La lectura de archivos JSON en Python es una habilidad fundamental en el desarrollo de software moderno. Permite automatizar el procesamiento de información y facilita la integración de datos en aplicaciones web. Este ejercicio demuestra cómo se puede transformar un archivo estructurado en información útil, lo cual es esencial en tareas como la gestión de blogs, sistemas de contenido o asistentes digitales.
