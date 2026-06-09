



CREATE DATABASE supercrud;

USE supercrud;

CREATE TABLE productos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2) NOT NULL,
    stock INT NOT NULL
);

<?php

$host = "localhost";
$dbname = "supercrud";
$user = "root";
$password = "";

try {
    $conexion = new PDO(
        "mysql:host=$host;dbname=$dbname;charset=utf8",
        $user,
        $password
    );

    $conexion->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

} catch(PDOException $e){
    die("Error de conexión: " . $e->getMessage());
}
?>

<?php
include("conexion.php");

if($_POST){

    $nombre = $_POST['nombre'];
    $precio = $_POST['precio'];
    $stock = $_POST['stock'];

    $sql = "INSERT INTO productos(nombre, precio, stock)
            VALUES(:nombre, :precio, :stock)";

    $stmt = $conexion->prepare($sql);

    $stmt->bindParam(':nombre', $nombre);
    $stmt->bindParam(':precio', $precio);
    $stmt->bindParam(':stock', $stock);

    $stmt->execute();

    header("Location: index.php");
}
?>

<form method="POST">
    Nombre:
    <input type="text" name="nombre"><br><br>

    Precio:
    <input type="number" step="0.01" name="precio"><br><br>

    Stock:
    <input type="number" name="stock"><br><br>

    <button type="submit">Guardar</button>
</form>

<?php
include("conexion.php");

$sql = "SELECT * FROM productos";
$stmt = $conexion->prepare($sql);
$stmt->execute();

$productos = $stmt->fetchAll(PDO::FETCH_ASSOC);
?>

<h2>Lista de Productos</h2>

<a href="crear.php">Nuevo Producto</a>

<table border="1">
<tr>
    <th>ID</th>
    <th>Nombre</th>
    <th>Precio</th>
    <th>Stock</th>
    <th>Acciones</th>
</tr>

<?php foreach($productos as $producto): ?>

<tr>
    <td><?= $producto['id'] ?></td>
    <td><?= $producto['nombre'] ?></td>
    <td><?= $producto['precio'] ?></td>
    <td><?= $producto['stock'] ?></td>

    <td>
        <a href="editar.php?id=<?= $producto['id'] ?>">
            Editar
        </a>

        <a href="eliminar.php?id=<?= $producto['id'] ?>">
            Eliminar
        </a>
    </td>
</tr>

<?php endforeach; ?>

</table>

<?php
include("conexion.php");

$id = $_GET['id'];

$sql = "SELECT * FROM productos WHERE id=:id";
$stmt = $conexion->prepare($sql);
$stmt->bindParam(':id', $id);
$stmt->execute();

$producto = $stmt->fetch(PDO::FETCH_ASSOC);

if($_POST){

    $nombre = $_POST['nombre'];
    $precio = $_POST['precio'];
    $stock = $_POST['stock'];

    $sql = "UPDATE productos
            SET nombre=:nombre,
                precio=:precio,
                stock=:stock
            WHERE id=:id";

    $stmt = $conexion->prepare($sql);

    $stmt->bindParam(':nombre', $nombre);
    $stmt->bindParam(':precio', $precio);
    $stmt->bindParam(':stock', $stock);
    $stmt->bindParam(':id', $id);

    $stmt->execute();

    header("Location: index.php");
}
?>

<form method="POST">

    Nombre:
    <input
        type="text"
        name="nombre"
        value="<?= $producto['nombre'] ?>"
    ><br><br>

    Precio:
    <input
        type="number"
        step="0.01"
        name="precio"
        value="<?= $producto['precio'] ?>"
    ><br><br>

    Stock:
    <input
        type="number"
        name="stock"
        value="<?= $producto['stock'] ?>"
    ><br><br>

    <button type="submit">
        Actualizar
    </button>

</form>

<?php
include("conexion.php");

$id = $_GET['id'];

$sql = "DELETE FROM productos WHERE id=:id";

$stmt = $conexion->prepare($sql);
$stmt->bindParam(':id', $id);

$stmt->execute();

header("Location: index.php");
?>

supercrud/
│
├── conexion.php
├── index.php
├── crear.php
├── editar.php
├── eliminar.php
│
└── base_datos.sql

# Super CRUD en PHP: Gestión de Productos

## Introducción

Un CRUD (Create, Read, Update y Delete) es una aplicación que permite realizar las operaciones básicas sobre una base de datos. En este ejemplo se desarrolló un Super CRUD en PHP para administrar productos, permitiendo registrar, consultar, modificar y eliminar información almacenada en una base de datos MySQL.

## Aspectos Técnicos

* **Lenguaje de programación:** PHP.
* **Base de datos:** MySQL.
* **Conexión:** PDO (PHP Data Objects) para una conexión segura a la base de datos.
* **Operaciones implementadas:**

  * Crear productos.
  * Mostrar productos registrados.
  * Editar información de productos.
  * Eliminar productos.
* **Estructura:** Archivos separados para cada operación (crear, listar, editar y eliminar).

## ¿Para qué sirve?

Este Super CRUD sirve para gestionar información de manera eficiente dentro de una base de datos. En el ejemplo de productos, permite controlar inventarios básicos, actualizar precios, consultar existencias y eliminar registros que ya no sean necesarios. Además, constituye la base para desarrollar sistemas más complejos como tiendas virtuales, sistemas de ventas o aplicaciones empresariales.

## Conclusión

El desarrollo de un Super CRUD en PHP es una excelente práctica para comprender la interacción entre aplicaciones web y bases de datos. A través de las operaciones de creación, consulta, actualización y eliminación, se adquieren conocimientos fundamentales para el desarrollo de sistemas de gestión de información. Este tipo de aplicación representa uno de los componentes más utilizados en el desarrollo de software moderno.
