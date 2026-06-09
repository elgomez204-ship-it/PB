# Conexión a bases de datos con PHP y Python (SQLite y MySQL)

## Introducción

En el desarrollo web es fundamental saber cómo conectar aplicaciones a bases de datos, ya que son el núcleo del almacenamiento de información. Existen diferentes tecnologías y motores de bases de datos, como SQLite y MySQL, que pueden utilizarse desde lenguajes como PHP y Python. En esta práctica se trabajan varias formas de conexión para consultar datos de una tabla de clientes.

---

## Aspectos técnicos

* **Lenguajes utilizados:**

  * PHP
  * Python
* **Bases de datos:**

  * SQLite (`empresa2026.db`)
  * MySQL (`empresa2026`)
* **Métodos de conexión:**

  * PDO (PHP Data Objects)
  * MySQLi (PHP)
  * mysql-connector-python (Python)
* **Operación realizada:**

  * `SELECT * FROM clientes`

---

## 1. Conexión a SQLite con PHP (PDO)

```php id="sqlite_pdo_001"
<?php

try {

    $conexion = new PDO("sqlite:empresa2026.db");

    $conexion->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

    $sql = "SELECT * FROM clientes";
    $stmt = $conexion->prepare($sql);
    $stmt->execute();

    $clientes = $stmt->fetchAll(PDO::FETCH_ASSOC);

    foreach ($clientes as $cliente) {
        echo $cliente["nombre"] . "<br>";
    }

} catch (PDOException $e) {
    echo "Error: " . $e->getMessage();
}

?>
```

---

## 2. Conexión a MySQL con PHP (PDO)

```php id="mysql_pdo_001"
<?php

try {

    $host = "localhost";
    $dbname = "empresa2026";
    $user = "root";
    $password = "";

    $conexion = new PDO(
        "mysql:host=$host;dbname=$dbname;charset=utf8",
        $user,
        $password
    );

    $conexion->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

    $sql = "SELECT * FROM clientes";
    $stmt = $conexion->prepare($sql);
    $stmt->execute();

    $clientes = $stmt->fetchAll(PDO::FETCH_ASSOC);

    foreach ($clientes as $cliente) {
        echo $cliente["nombre"] . "<br>";
    }

} catch (PDOException $e) {
    echo "Error: " . $e->getMessage();
}

?>
```

---

## 3. Conexión a MySQL con Python (mysql-connector)

```python id="python_mysql_001"
import mysql.connector

conexion = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",
    database="empresa2026"
)

cursor = conexion.cursor(dictionary=True)

cursor.execute("SELECT * FROM clientes")

clientes = cursor.fetchall()

for cliente in clientes:
    print(cliente["nombre"])

conexion.close()
```

---

## 4. Conexión a MySQL con PHP (MySQLi)

```php id="mysqli_001"
<?php

$conexion = new mysqli("localhost", "root", "", "empresa2026");

if ($conexion->connect_error) {
    die("Error de conexión: " . $conexion->connect_error);
}

$sql = "SELECT * FROM clientes";
$resultado = $conexion->query($sql);

while ($cliente = $resultado->fetch_assoc()) {
    echo $cliente["nombre"] . "<br>";
}

$conexion->close();

?>
```

---

## ¿Para qué sirve?

Este tipo de conexiones sirve para:

* Acceder a datos almacenados en bases de datos.
* Crear sistemas web dinámicos.
* Gestionar clientes, productos o usuarios.
* Integrar aplicaciones con distintos motores de base de datos.
* Desarrollar sistemas empresariales reales.

---

## Conclusión

El manejo de conexiones a bases de datos es una habilidad esencial en el desarrollo web. En esta práctica se han utilizado diferentes tecnologías como PDO, MySQLi y Python para conectar con SQLite y MySQL. Esto permite comprender cómo interactúan los lenguajes de programación con los sistemas de almacenamiento de datos, facilitando el desarrollo de aplicaciones completas y funcionales.
