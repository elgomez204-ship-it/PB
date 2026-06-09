# Crear y eliminar archivos con Python

## Introducción

En el desarrollo de software es común trabajar con archivos para almacenar información de forma permanente. En este ejercicio se simula un entorno de trabajo empresarial donde es necesario crear y eliminar archivos de texto que contienen tareas pendientes de proyectos.

Python permite realizar estas operaciones de forma sencilla utilizando funciones del sistema de archivos, lo cual es esencial para la gestión de información en aplicaciones reales.

---

## Aspectos técnicos

* **Lenguaje utilizado:** Python
* **Módulo utilizado:** `os`
* **Operaciones principales:**

  * Creación de archivos con `open()`
  * Escritura de texto con `write()`
  * Eliminación de archivos con `os.remove()`
* **Conceptos clave:**

  * Manejo de archivos
  * Persistencia de datos
  * Gestión del sistema de archivos

---

## Ejemplo práctico

### 1. Crear el archivo y escribir tareas

```python id="file_001"
# Crear y escribir en el archivo
with open("tareas_pendientes.txt", "w", encoding="utf-8") as archivo:
    archivo.write("Tarea 1: Revisar informes\n")
    archivo.write("Tarea 2: Programar reuniones\n")
    archivo.write("Tarea 3: Generar reporte financiero\n")

print("Archivo creado correctamente")
```

---

### 2. Eliminar el archivo

```python id="file_002"
import os

# Eliminar el archivo
if os.path.exists("tareas_pendientes.txt"):
    os.remove("tareas_pendientes.txt")
    print("Archivo eliminado correctamente")
else:
    print("El archivo no existe")
```

---

## Ejemplo de ejecución

```text id="file_003"
Archivo creado correctamente
Archivo eliminado correctamente
```

---

## ¿Para qué sirve?

Este tipo de operaciones sirve para:

* Gestionar archivos en sistemas informáticos.
* Crear registros temporales o permanentes.
* Administrar tareas en aplicaciones empresariales.
* Automatizar procesos de almacenamiento.
* Controlar información en proyectos de software.

---

## Conclusión

El manejo de archivos en Python es una habilidad fundamental en la programación. Permite crear, modificar y eliminar información de manera eficiente, lo cual es esencial en entornos profesionales. Este ejercicio muestra cómo gestionar tareas mediante archivos de texto, una práctica común en sistemas de gestión empresarial y aplicaciones reales.
