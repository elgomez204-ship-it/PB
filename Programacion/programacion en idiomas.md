# Selector de idioma en una página web con PHP y HTML

## Introducción

En el desarrollo web es común crear aplicaciones multilingües que permitan al usuario elegir el idioma de la interfaz. Para ello, PHP ofrece herramientas como las **sesiones**, que permiten guardar información del usuario durante su navegación, y funciones como `str_getcsv`, que facilitan la lectura de archivos CSV con traducciones.

En esta práctica se construye un selector de idioma básico utilizando PHP y HTML.

---

## Aspectos técnicos

* **Tecnologías utilizadas:**

  * PHP (lógica del servidor)
  * HTML (interfaz)
  * CSV (almacenamiento de traducciones)
* **Conceptos clave:**

  * Sesiones en PHP (`$_SESSION`)
  * Lectura de archivos CSV (`str_getcsv`)
  * Seguridad de salida (`htmlspecialchars`)
* **Archivo principal de datos:**

  * `idiomas.csv`

---

## Ejemplo práctico

### 1. Ejemplo de archivo `idiomas.csv`

```csv id="csv_001"
es,Hola,Bienvenido a la página
en,Hello,Welcome to the website
fr,Bonjour,Bienvenue sur le site
```

---

### 2. Lectura del CSV y creación del array

```php id="php_csv_001"
<?php
session_start();

$archivo = fopen("idiomas.csv", "r");

$idiomas = [];

while (($linea = fgetcsv($archivo)) !== false) {

    $idioma = $linea[0];

    $idiomas[$idioma] = [
        "saludo" => $linea[1],
        "mensaje" => $linea[2]
    ];
}

fclose($archivo);
?>
```

---

### 3. Selector de idioma con sesiones

```php id="php_session_001"
<?php
session_start();

if (isset($_POST["idioma"])) {
    $_SESSION["idioma"] = $_POST["idioma"];
}

if (!isset($_SESSION["idioma"])) {
    $_SESSION["idioma"] = "es";
}

$idiomaActual = $_SESSION["idioma"];
?>
```

---

### 4. Interfaz HTML con selector

```php id="html_selector_001"
<form method="POST">

    <label>Selecciona idioma:</label>

    <select name="idioma">
        <option value="es">Español</option>
        <option value="en">Inglés</option>
        <option value="fr">Francés</option>
    </select>

    <button type="submit">Cambiar</button>

</form>

<h1>
<?php echo htmlspecialchars($idiomas[$idiomaActual]["saludo"]); ?>
</h1>

<p>
<?php echo htmlspecialchars($idiomas[$idiomaActual]["mensaje"]); ?>
</p>
```

---

## ¿Para qué sirve?

Este sistema sirve para:

* Crear páginas web multilingües.
* Mejorar la experiencia del usuario.
* Adaptar contenido según el país o idioma.
* Gestionar traducciones de forma sencilla.
* Mantener preferencias del usuario mediante sesiones.

---

## Conclusión

El uso de PHP junto con sesiones y archivos CSV permite crear sistemas de traducción simples pero funcionales. Este tipo de implementación es muy útil en páginas web modernas que necesitan adaptarse a diferentes idiomas, mejorando la accesibilidad y la experiencia del usuario.
