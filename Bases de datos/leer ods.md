# Lectura de Archivos ODS (OpenDocument Spreadsheet) con Python

## Introducción

Los archivos ODS (OpenDocument Spreadsheet) son hojas de cálculo utilizadas principalmente por LibreOffice Calc y Apache OpenOffice. Estos archivos permiten almacenar y organizar información en tablas, facilitando el manejo de datos. Python ofrece herramientas que permiten leer archivos ODS de forma sencilla para procesar, analizar o importar información hacia otros sistemas.

## Aspectos Técnicos

* **Lenguaje de programación:** Python.
* **Formato de archivo:** ODS (OpenDocument Spreadsheet).
* **Biblioteca utilizada:** pandas junto con odfpy.
* **Funciones principales:**

  * Abrir archivos ODS.
  * Leer filas y columnas.
  * Mostrar o procesar datos.
  * Exportar información a otros formatos.
* **Instalación de dependencias:**

```bash
pip install pandas odfpy
```

### Ejemplo básico en Python

```python
import pandas as pd

# Leer archivo ODS
datos = pd.read_excel(
    "productos.ods",
    engine="odf"
)

# Mostrar contenido
print(datos)

# Mostrar las primeras 5 filas
print(datos.head())
```

### Ejemplo de salida

```text
   ID     Producto    Precio
0   1      Teclado     25.50
1   2         Ratón    15.00
2   3      Monitor   180.00
3   4      Impresora 120.00
```

## ¿Para qué sirve?

La lectura de archivos ODS permite importar información almacenada en hojas de cálculo sin necesidad de introducir los datos manualmente. Es útil para gestionar inventarios, listas de estudiantes, registros de ventas, reportes financieros y cualquier conjunto de datos que se encuentre en formato de hoja de cálculo. Además, facilita el análisis y procesamiento automático de grandes volúmenes de información.

## Conclusión

La lectura de archivos ODS con Python es una solución práctica y eficiente para trabajar con datos provenientes de hojas de cálculo. Gracias a bibliotecas como pandas y odfpy, es posible acceder, analizar y manipular información de forma sencilla, mejorando la automatización de procesos y la integración de datos en diferentes aplicaciones.
