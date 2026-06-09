# Listado de modelos y práctica con IA (Ollama + PHP + HTML)

## Introducción

En esta práctica se trabaja con modelos de Inteligencia Artificial generativa, los cuales permiten crear texto, responder preguntas o analizar información. Se utiliza **Ollama**, una herramienta que permite ejecutar modelos de IA de forma local, como *Llama 3* o *Qwen2.5*, integrándolos en una página web mediante PHP y HTML. El objetivo es aprender cómo conectar una interfaz web con un modelo de IA real.

---

## Aspectos técnicos

* **Tecnologías utilizadas:**

  * HTML (estructura de la página)
  * PHP (conexión con la API)
  * CSS básico (estilo)
  * Ollama (servidor de modelos de IA)

* **Modelo de IA recomendado:**

  * `llama3:latest` o `qwen2.5:7b-instruct-q4_0`

* **API utilizada:**

  * `http://localhost:11434/api/generate`

* **Funcionamiento general:**

  1. Se selecciona un modelo de IA.
  2. Se muestra su información en HTML (nombre, tamaño y fecha aproximada).
  3. PHP envía una petición a la API de Ollama.
  4. El modelo genera un texto descriptivo sobre sí mismo.
  5. El resultado se muestra en la página web.

---

## Ejemplo básico de implementación

### 1. Archivo HTML con información del modelo

```html id="ia_html_001"
<!DOCTYPE html>
<html>
<head>
    <title>Modelo de IA</title>
</head>
<body>

<h1>Modelo seleccionado</h1>

<p><strong>Nombre:</strong> llama3:latest</p>
<p><strong>Tamaño:</strong> 4.7 GB (aprox)</p>
<p><strong>Tipo:</strong> Modelo generativo de lenguaje</p>

<form method="POST">
    <button type="submit">Generar descripción con IA</button>
</form>

<?php include("modelo.php"); ?>

</body>
</html>
```

---

### 2. Código PHP para conectar con Ollama

```php id="ia_php_001"
<?php

if ($_POST) {

    $url = "http://localhost:11434/api/generate";

    $data = [
        "model" => "llama3:latest",
        "prompt" => "Explica qué eres como modelo de inteligencia artificial de forma breve",
        "stream" => false
    ];

    $options = [
        "http" => [
            "header"  => "Content-Type: application/json",
            "method"  => "POST",
            "content" => json_encode($data)
        ]
    ];

    $context = stream_context_create($options);

    $response = file_get_contents($url, false, $context);

    $result = json_decode($response, true);

    echo "<h3>Respuesta del modelo:</h3>";
    echo "<p>" . $result["response"] . "</p>";
}
?>
```

---

## ¿Para qué sirve?

Esta práctica sirve para comprender cómo se integran modelos de Inteligencia Artificial en aplicaciones reales. Permite:

* Conectar una web con una IA local.
* Generar texto automáticamente desde un modelo.
* Entender el uso de APIs en PHP.
* Aprender cómo funcionan modelos como Llama o Qwen.
* Integrar IA en sistemas web educativos o empresariales.

También es la base de sistemas modernos como chatbots, asistentes virtuales y herramientas de automatización.

---

## Conclusión

La integración de modelos de IA mediante Ollama y PHP permite crear aplicaciones web inteligentes capaces de generar contenido dinámico. Esta práctica ayuda a comprender el funcionamiento de los modelos de lenguaje y su conexión con interfaces web, fortaleciendo habilidades en desarrollo web e inteligencia artificial. Además, demuestra cómo la IA puede ser utilizada de forma práctica en proyectos reales.
