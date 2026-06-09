# Suma del tamaño de archivos en una carpeta con Python

## Introducción

En la gestión de sistemas informáticos es importante conocer cuánto espacio ocupan los archivos dentro de un directorio. Esto permite optimizar el almacenamiento, detectar archivos demasiado grandes y mejorar la organización del sistema.

En esta práctica se utiliza Python para recorrer carpetas del sistema y calcular el tamaño total de los archivos, además de identificar aquellos que superan 1 GB.

---

## Aspectos técnicos

* **Lenguaje utilizado:** Python
* **Módulos principales:**

  * `os`
* **Funciones utilizadas:**

  * `os.walk()` → recorrer carpetas y subcarpetas
  * `os.path.getsize()` → obtener tamaño de archivos
* **Conceptos clave:**

  * Sistemas de archivos
  * Recorrido de directorios
  * Cálculo de tamaño en bytes, MB y GB

---

## Ejemplo práctico

### 1. Código en Python

```python id="folder_001"
import os

# Pedir ruta al usuario
ruta = input("Introduce la ruta de la carpeta: ")

# Variables para almacenar resultados
tamano_total = 0
archivos_grandes = []

# Recorrer carpeta y subcarpetas
for carpeta, subcarpetas, archivos in os.walk(ruta):

    for archivo in archivos:
        ruta_archivo = os.path.join(carpeta, archivo)

        try:
            tamano = os.path.getsize(ruta_archivo)
            tamano_total += tamano

            # Identificar archivos mayores a 1 GB
            if tamano > 1 * 1024 * 1024 * 1024:
                archivos_grandes.append(ruta_archivo)

        except:
            print("No se pudo leer:", ruta_archivo)

# Convertir a MB
tamano_mb = tamano_total / (1024 * 1024)

print("\n--- RESULTADO ---")
print("Tamaño total:", round(tamano_mb, 2), "MB")

print("\nArchivos mayores de 1 GB:")
for archivo in archivos_grandes:
    print(archivo)
```

---

## Ejemplo de salida

```text id="folder_002"
Introduce la ruta de la carpeta: C:/Usuarios/Documentos

--- RESULTADO ---
Tamaño total: 1543.78 MB

Archivos mayores de 1 GB:
C:/Usuarios/Documentos/video1.mp4
C:/Usuarios/Documentos/backup.iso
```

---

## ¿Para qué sirve?

Este tipo de programa sirve para:

* Analizar el espacio ocupado en disco.
* Detectar archivos demasiado grandes.
* Optimizar el almacenamiento del sistema.
* Gestionar carpetas en servidores o PCs.
* Realizar mantenimiento de sistemas informáticos.

---

## Conclusión

El uso de Python para analizar el tamaño de archivos en una carpeta permite automatizar tareas de administración del sistema. Gracias a funciones como `os.walk()` y `os.path.getsize()`, es posible recorrer directorios completos y obtener información útil sobre el uso del almacenamiento, lo cual es esencial en la gestión eficiente de datos.
