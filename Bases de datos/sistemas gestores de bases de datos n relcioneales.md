# Sistemas Gestores de Bases de Datos No Relacionales (NoSQL)

## Introducción

Los Sistemas Gestores de Bases de Datos No Relacionales (NoSQL DBMS) son herramientas diseñadas para almacenar, organizar y gestionar grandes volúmenes de datos sin utilizar el modelo tradicional de tablas relacionales. Estos sistemas son ampliamente utilizados en aplicaciones modernas como redes sociales, comercio electrónico, análisis de Big Data e ինտernet de las cosas (IoT), debido a su alta escalabilidad, flexibilidad y rendimiento.

---

## Principales Sistemas NoSQL con Ejemplos Elaborados

## 1. MongoDB (Base de datos documental)

MongoDB almacena los datos en documentos JSON/BSON, lo que permite estructuras flexibles y dinámicas.

### Ejemplo real: Sistema de tienda online

```json id="mongo_001"
{
  "cliente_id": 101,
  "nombre": "Carlos Pérez",
  "email": "carlos@email.com",
  "carrito": [
    {
      "producto": "Laptop Gamer",
      "precio": 1200,
      "cantidad": 1
    },
    {
      "producto": "Mouse Gaming",
      "precio": 45,
      "cantidad": 2
    }
  ],
  "direccion_envio": {
    "ciudad": "Valencia",
    "codigo_postal": "46001"
  },
  "total_compra": 1290,
  "estado": "pendiente"
}
```

### Uso

* Catálogos de productos.
* Sistemas de e-commerce.
* Aplicaciones web dinámicas.

---

## 2. Redis (Clave - Valor)

Redis almacena datos en memoria como pares clave-valor, lo que lo hace extremadamente rápido.

### Ejemplo real: Sistema de sesiones de usuarios

```text id="redis_001"
session:1001 → {
  "usuario": "Ana",
  "estado": "activa",
  "ultima_conexion": "2026-06-10 11:00",
  "rol": "admin"
}

session:1002 → {
  "usuario": "Luis",
  "estado": "activa",
  "ultima_conexion": "2026-06-10 11:05",
  "rol": "cliente"
}
```

### Uso

* Caché de aplicaciones.
* Sesiones de usuarios.
* Sistemas en tiempo real.

---

## 3. Cassandra (Orientada a columnas)

Apache Cassandra organiza los datos por columnas y está diseñada para manejar grandes volúmenes de información distribuida.

### Ejemplo real: Registro de ventas globales

```text id="cass_001"
Tabla: ventas_por_año

Producto | 2023 | 2024 | 2025 | 2026
--------------------------------------
Laptop   | 1200 | 1500 | 1800 | 2100
Monitor  |  800 | 1000 | 1300 | 1600
Teclado  | 2000 | 2300 | 2600 | 3000
```

### Uso

* Big Data.
* Análisis de métricas.
* Sistemas bancarios y financieros.

---

## 4. Neo4j (Base de datos de grafos)

Neo4j está diseñado para manejar datos altamente conectados mediante nodos y relaciones.

### Ejemplo real: Red social

```text id="neo4j_001"
(Ana:Usuario)
  ├── AMIGA_DE → (Carlos:Usuario)
  ├── SIGUE → (Empresa:TechNews)
  └── LE_GUSTA → (Página:Programación)

(Carlos:Usuario)
  ├── AMIGA_DE → (Pedro:Usuario)
  ├── TRABAJA_EN → (Empresa:Google)
  └── SIGUE → (Ana:Usuario)
```

### Uso

* Redes sociales.
* Motores de recomendación.
* Análisis de relaciones complejas.

---

## 5. Amazon DynamoDB (Clave - Valor / Documental híbrido)

DynamoDB combina modelo clave-valor y documentos, siendo altamente escalable en la nube.

### Ejemplo real: Sistema de pedidos

```json id="dynamo_001"
{
  "pedido_id": "ORD1001",
  "cliente": "María López",
  "productos": [
    "Tablet",
    "Funda protectora"
  ],
  "total": 320.50,
  "estado": "enviado",
  "fecha": "2026-06-10"
}
```

### Uso

* Aplicaciones en la nube.
* Sistemas de alto tráfico.
* Plataformas globales.

---

## Conclusión

Los sistemas gestores de bases de datos NoSQL como MongoDB, Redis, Cassandra, Neo4j y DynamoDB ofrecen soluciones especializadas para distintos tipos de problemas. Su principal ventaja es la flexibilidad, escalabilidad y alto rendimiento, lo que los hace ideales para aplicaciones modernas que manejan grandes cantidades de datos y requieren respuestas rápidas. La elección del sistema adecuado depende del tipo de datos, la estructura del proyecto y las necesidades de rendimiento.
