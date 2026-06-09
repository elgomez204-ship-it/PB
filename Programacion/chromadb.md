# Práctica: Búsqueda semántica en ChromaDB

## Introducción

La búsqueda semántica es una técnica utilizada en Inteligencia Artificial que permite encontrar resultados relacionados por significado, no solo por coincidencia de palabras. En esta práctica se utiliza **ChromaDB**, una base de datos vectorial, junto con **embeddings**, que transforman palabras en representaciones numéricas para medir su similitud.

El objetivo es construir un pequeño sistema capaz de devolver palabras relacionadas con una consulta en español.

---

## Aspectos técnicos

* **Tecnología principal:** ChromaDB (base de datos vectorial).
* **Lenguaje:** Python.
* **Conceptos clave:**

  * Embeddings (representación numérica del significado de palabras).
  * Similaridad semántica (comparación de vectores).
  * Colecciones en ChromaDB.
* **Colección utilizada:** `diccionario_es`.
* **Flujo del sistema:**

  1. Crear colección en ChromaDB.
  2. Insertar palabras en forma de embeddings.
  3. Realizar consultas semánticas.
  4. Obtener resultados relacionados por significado.

---

## Ejemplo de implementación

### 1. Creación de la colección

```python id="chroma_001"
import chromadb

client = chromadb.PersistentClient(path="./chroma_db")

collection = client.get_or_create_collection(name="diccionario_es")
```

---

### 2. Inserción de palabras

```python id="chroma_002"
words = [
    "perro",
    "gato",
    "caballo",
    "automóvil",
    "bicicleta",
    "avión",
    "manzana",
    "plátano"
]

collection.add(
    documents=words,
    ids=[str(i) for i in range(len(words))]
)
```

---

### 3. Búsqueda semántica

```python id="chroma_003"
query = "animal doméstico"

resultados = collection.query(
    query_texts=[query],
    n_results=3
)

print(resultados["documents"])
```

---

### 4. Ejemplo de resultado esperado

```text id="chroma_004"
Consulta: "animal doméstico"

Resultados:
- perro
- gato
- caballo
```

---

## ¿Para qué sirve?

La búsqueda semántica en ChromaDB sirve para encontrar información basada en el significado de las palabras, no solo en coincidencias exactas. Esto es útil en:

* Motores de búsqueda inteligentes.
* Chatbots y asistentes virtuales.
* Sistemas de recomendación.
* Análisis de texto.
* Aplicaciones de Inteligencia Artificial.

Permite mejorar la calidad de los resultados al entender la intención del usuario.

---

## Conclusión

La práctica con ChromaDB y embeddings permite comprender cómo funcionan los sistemas de búsqueda semántica modernos. A través de la transformación de palabras en vectores, es posible encontrar relaciones de significado entre términos. Este tipo de tecnología es fundamental en la Inteligencia Artificial actual, especialmente en sistemas de búsqueda avanzada y procesamiento del lenguaje natural.
