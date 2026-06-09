# Tipos de Bases de Datos No Relacionales (NoSQL) con Ejemplos Elaborados

## Introducción

Las bases de datos NoSQL permiten almacenar información de forma flexible, sin estructuras rígidas como las tablas relacionales. Existen distintos tipos de bases de datos NoSQL, cada uno diseñado para resolver problemas específicos como el manejo de grandes volúmenes de datos, relaciones complejas o alta velocidad de acceso.

A continuación se presentan los principales tipos con ejemplos más detallados y realistas.

---

## 1. Bases de Datos Clave - Valor

Este modelo almacena la información en pares de **clave → valor**, donde la clave es única y permite acceder directamente al dato.

### Ejemplo real: Sistema de sesiones de usuarios en una tienda online

```text id="kv_001"
session:usuario_1001 → {
    "nombre": "Carlos Pérez",
    "carrito": ["Teclado", "Ratón", "Monitor"],
    "total": 215.50,
    "logeado": true,
    "ultima_actividad": "2026-06-10 10:35"
}
```

```text id="kv_002"
session:usuario_1002 → {
    "nombre": "Laura Gómez",
    "carrito": ["Laptop"],
    "total": 850.00,
    "logeado": true,
    "ultima_actividad": "2026-06-10 10:40"
}
```

### Explicación

Cada usuario tiene una clave única de sesión. El acceso es inmediato sin necesidad de búsquedas complejas, lo que hace este modelo ideal para sistemas de autenticación o caché.

---

## 2. Bases de Datos Documentales

Almacenan datos en documentos tipo JSON, donde cada registro puede tener una estructura diferente.

### Ejemplo real: Sistema de catálogo de productos en una tienda online

```json id="doc_001"
{
  "producto_id": 1,
  "nombre": "Laptop Gamer",
  "marca": "ASUS",
  "precio": 1200.00,
  "stock": 15,
  "especificaciones": {
    "procesador": "Intel i7",
    "ram": "16 GB",
    "gpu": "RTX 4060"
  },
  "categorias": ["Tecnología", "Gaming"],
  "envio_gratis": true
}
```

```json id="doc_002"
{
  "producto_id": 2,
  "nombre": "Smartphone",
  "marca": "Samsung",
  "precio": 799.99,
  "stock": 30,
  "especificaciones": {
    "pantalla": "6.5 pulgadas",
    "almacenamiento": "256 GB",
    "bateria": "5000 mAh"
  },
  "categorias": ["Móviles", "Tecnología"],
  "colores_disponibles": ["Negro", "Azul", "Blanco"]
}
```

### Explicación

Cada producto puede tener atributos distintos sin necesidad de seguir una estructura fija, lo que permite gran flexibilidad para catálogos dinámicos.

---

## 3. Bases de Datos en Columnas

Organizan los datos por columnas en lugar de filas, lo que permite un procesamiento eficiente de grandes volúmenes de información.

### Ejemplo real: Sistema de análisis de ventas por año

```text id="col_001"
Columna: producto
→ Laptop, Monitor, Teclado, Impresora

Columna: 2024
→ 1200, 900, 1500, 700

Columna: 2025
→ 1400, 1100, 1700, 800

Columna: 2026
→ 1600, 1300, 2000, 950
```

### Explicación

En lugar de consultar fila por fila, el sistema puede analizar directamente una columna completa, lo que lo hace muy eficiente para estadísticas y Big Data.

---

## 4. Bases de Datos de Grafos

Modelan los datos como **nodos (entidades)** y **relaciones (conexiones)**, ideales para representar redes complejas.

### Ejemplo real: Red social de usuarios

```text id="graph_001"
(Usuario: Ana)
    ├── AMIGA_DE → (Usuario: Carlos)
    ├── SIGUE → (Usuario: Laura)
    └── LE_GUSTA → (Página: Tecnología)

(Usuario: Carlos)
    ├── AMIGA_DE → (Usuario: Ana)
    ├── TRABAJA_CON → (Usuario: Pedro)
    └── SIGUE → (Página: Gaming)

(Usuario: Laura)
    ├── AMIGA_DE → (Usuario: Pedro)
    └── LE_GUSTA → (Página: Diseño)
```

### Explicación

Cada usuario es un nodo y las relaciones permiten consultas como:

* “¿Quién es amigo de quién?”
* “¿Qué usuarios siguen una página?”
* “Recomendaciones de amigos en común”

---

## Conclusión

Los diferentes tipos de bases de datos NoSQL permiten resolver problemas específicos de manera eficiente. Los modelos clave-valor destacan por su velocidad, los documentales por su flexibilidad, los orientados a columnas por su capacidad de análisis masivo y los de grafos por su potencia en relaciones complejas. Gracias a esta variedad, NoSQL se ha convertido en una pieza clave en sistemas modernos como redes sociales, e-commerce y Big Data.
