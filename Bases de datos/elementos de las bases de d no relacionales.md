# Elementos de las Bases de Datos No Relacionales (NoSQL)

## Introducción

Las bases de datos no relacionales o NoSQL están diseñadas para almacenar información de manera flexible y escalable. A diferencia del modelo relacional, no dependen de tablas rígidas, sino de diferentes estructuras de datos. Para comprender cómo funcionan, es importante conocer sus elementos principales, que varían según el tipo de base de datos, pero comparten conceptos fundamentales.

---

## Elementos de las Bases de Datos NoSQL

### 1. Colecciones (Collections)

Las colecciones son el equivalente a las tablas en bases de datos relacionales, pero sin una estructura fija.

* Agrupan documentos o registros relacionados.
* No requieren un esquema rígido.

**Ejemplo: colección "productos"**

```json id="col_001"
[
  {
    "nombre": "Teclado",
    "precio": 25.50
  },
  {
    "nombre": "Monitor",
    "precio": 180.00
  }
]
```

---

### 2. Documentos

Son la unidad principal de almacenamiento en bases de datos documentales como MongoDB.

* Representan un registro completo.
* Se almacenan en formato JSON o BSON.
* Pueden tener campos diferentes entre sí.

**Ejemplo de documento:**

```json id="doc_001"
{
  "id": 1,
  "nombre": "Laptop",
  "marca": "HP",
  "especificaciones": {
    "ram": "16GB",
    "procesador": "Intel i7"
  },
  "precio": 950.00
}
```

---

### 3. Claves (Keys)

Son identificadores únicos que permiten acceder rápidamente a un dato.

* En bases clave-valor, cada elemento tiene una clave única.
* Evitan duplicados.

**Ejemplo:**

```text id="key_001"
usuario:1001 → "Carlos Pérez"
usuario:1002 → "Laura Gómez"
```

---

### 4. Valores (Values)

Son los datos almacenados asociados a una clave.

* Pueden ser texto, números, listas o incluso objetos completos.

**Ejemplo:**

```json id="value_001"
{
  "nombre": "Carlos Pérez",
  "edad": 25,
  "compras": ["Laptop", "Mouse", "Teclado"]
}
```

---

### 5. Nodos (Nodes)

Se utilizan en bases de datos de grafos para representar entidades.

* Cada nodo es un objeto o entidad.
* Puede tener propiedades.

**Ejemplo:**

```text id="node_001"
(Usuario: Ana)
{
  "edad": 22,
  "ciudad": "Valencia"
}
```

---

### 6. Relaciones (Edges)

Conectan los nodos entre sí en bases de datos de grafos.

* Representan cómo se relacionan los datos.
* Pueden tener dirección y tipo.

**Ejemplo:**

```text id="edge_001"
(Ana) ---- AMIGA_DE ----> (Carlos)
(Carlos) ---- SIGUE ----> (Laura)
```

---

### 7. Columnas (Column Families)

En bases de datos orientadas a columnas, los datos se organizan por columnas en lugar de filas.

* Permiten análisis eficiente de grandes volúmenes de datos.
* Cada columna puede crecer de forma independiente.

**Ejemplo:**

```text id="column_001"
Producto | 2024 | 2025 | 2026
--------------------------------
Laptop   | 1200 | 1400 | 1600
Monitor  |  900 | 1100 | 1300
Teclado  | 1500 | 1700 | 2000
```

---

## ¿Para qué sirven estos elementos?

Los elementos de las bases de datos NoSQL permiten:

* Organizar datos de forma flexible.
* Manejar grandes volúmenes de información.
* Representar relaciones complejas.
* Adaptarse a distintos tipos de aplicaciones.
* Mejorar el rendimiento en sistemas modernos.

---

## Conclusión

Los elementos de las bases de datos NoSQL son fundamentales para entender su funcionamiento. Colecciones, documentos, claves, valores, nodos, relaciones y columnas forman la base de estos sistemas. Gracias a su flexibilidad, permiten almacenar y gestionar datos de manera eficiente en aplicaciones modernas como redes sociales, sistemas en la nube y plataformas de comercio electrónico.
