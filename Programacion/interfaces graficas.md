# Calculadora básica con Tkinter en Python

## Introducción

Las interfaces gráficas de usuario (GUI) permiten interactuar con programas de forma visual mediante ventanas, botones y campos de texto. En esta actividad se utiliza la biblioteca **Tkinter** de Python para crear una calculadora básica que suma dos números introducidos por el usuario.

Este tipo de ejercicios ayuda a comprender cómo funcionan las aplicaciones de escritorio y la interacción entre el usuario y el programa.

---

## Aspectos técnicos

* **Lenguaje utilizado:** Python
* **Biblioteca:** Tkinter
* **Componentes utilizados:**

  * `Tk()` → ventana principal
  * `Entry` → campos de entrada
  * `Button` → botón de acción
  * `Label` → mostrar resultados
* **Eventos:**

  * Función asociada al botón para realizar la suma
* **Conceptos clave:**

  * Interfaz gráfica
  * Eventos y funciones
  * Captura de datos del usuario

---

## Ejemplo práctico

### 1. Código completo de la calculadora

```python id="tkinter_001"
import tkinter as tk

# Crear ventana principal
ventana = tk.Tk()
ventana.title("Calculadora básica")

# Entradas de texto
entrada1 = tk.Entry(ventana)
entrada1.pack()

entrada2 = tk.Entry(ventana)
entrada2.pack()

# Etiqueta de resultado
resultado = tk.Label(ventana, text="Resultado: ")
resultado.pack()

# Función para sumar
def calcular():
    try:
        num1 = float(entrada1.get())
        num2 = float(entrada2.get())
        suma = num1 + num2
        resultado.config(text="Resultado: " + str(suma))
    except:
        resultado.config(text="Error: introduce números válidos")

# Botón
boton = tk.Button(ventana, text="Calcular!", command=calcular)
boton.pack()

# Ejecutar ventana
ventana.mainloop()
```

---

## Ejemplo de funcionamiento

* El usuario introduce dos números en los campos de texto.
* Pulsa el botón **"Calcular!"**.
* El programa suma los valores.
* El resultado se muestra en la etiqueta.

**Ejemplo:**

```text id="tkinter_002"
Entrada 1: 5
Entrada 2: 3

Resultado: 8
```

---

## ¿Para qué sirve?

Este tipo de aplicación sirve para:

* Aprender a crear interfaces gráficas.
* Desarrollar aplicaciones de escritorio básicas.
* Practicar eventos y funciones en Python.
* Mejorar la interacción usuario-programa.
* Crear herramientas simples como calculadoras o formularios.

---

## Conclusión

El uso de Tkinter permite desarrollar interfaces gráficas de manera sencilla en Python. En esta actividad se ha creado una calculadora básica que demuestra cómo interactúan los elementos de la interfaz con la lógica del programa. Este conocimiento es fundamental para el desarrollo de aplicaciones de escritorio más complejas.
