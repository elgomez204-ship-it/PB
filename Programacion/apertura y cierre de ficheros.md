# Lectura y escritura de datos con archivos binarios (pickle) en Python

## Introducción

En la programación es fundamental poder guardar información de forma persistente para poder reutilizarla posteriormente. En este ejercicio se trabaja con archivos binarios utilizando el módulo **pickle** de Python, el cual permite almacenar objetos complejos como listas o clases.

Este tipo de técnicas es muy útil en aplicaciones reales como sistemas de gestión de clientes, inventarios o usuarios.

---

## Aspectos técnicos

* **Lenguaje utilizado:** Python
* **Módulo principal:** `pickle`
* **Tipo de archivo:** Binario (`.bin`)
* **Conceptos clave:**

  * Serialización de objetos
  * Deserialización de objetos
  * Persistencia de datos
* **Operaciones principales:**

  * `pickle.dump()` → guardar datos en archivo
  * `pickle.load()` → recuperar datos desde archivo

---

## Ejemplo práctico

### 1. Creación de la clase Cliente

```python id="pickle_001"
class Cliente:
    def __init__(self, nombre, email):
        self.nombre = nombre
        self.email = email
```

---

### 2. Guardar clientes en archivo binario

```python id="pickle_002"
import pickle

# Crear lista de clientes
clientes = [
    Cliente("Juan Pérez", "juan@email.com"),
    Cliente("Ana López", "ana@email.com"),
    Cliente("Carlos Ruiz", "carlos@email.com")
]

# Guardar en archivo binario
archivo = open("clientes.bin", "wb")
pickle.dump(clientes, archivo)
archivo.close()
```

---

### 3. Recuperar clientes desde el archivo binario

```python id="pickle_003"
import pickle

# Abrir archivo en modo lectura binaria
archivo = open("clientes.bin", "rb")

# Cargar datos
clientes_cargados = pickle.load(archivo)

archivo.close()

# Mostrar información
for cliente in clientes_cargados:
    print("Nombre:", cliente.nombre)
    print("Email:", cliente.email)
    print("------------------------")
```

---

## Ejemplo de salida en consola

```text id="pickle_004"
Nombre: Juan Pérez
Email: juan@email.com
------------------------
Nombre: Ana López
Email: ana@email.com
------------------------
Nombre: Carlos Ruiz
Email: carlos@email.com
------------------------
```

---

## ¿Para qué sirve?

El uso de archivos binarios con `pickle` sirve para:

* Guardar objetos complejos en archivos.
* Mantener datos persistentes entre ejecuciones.
* Crear sistemas de gestión de información.
* Almacenar listas, clases y estructuras completas.
* Desarrollar aplicaciones más avanzadas sin base de datos.

---

## Conclusión

El manejo de archivos binarios con `pickle` permite almacenar y recuperar objetos de Python de forma sencilla. Esta técnica es muy útil en el desarrollo de aplicaciones que requieren persistencia de datos, como sistemas de clientes o inventarios. Comprender este proceso es clave para avanzar en la programación y construir sistemas más completos y funcionales.
