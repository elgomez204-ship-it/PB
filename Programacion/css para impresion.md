# Estilos CSS para impresión de facturas en formato A4

## Introducción

En el desarrollo web es común generar documentos imprimibles como facturas, recibos o reportes. Para ello, CSS ofrece herramientas específicas que permiten adaptar el contenido a un formato físico, como el papel A4. En esta práctica se trabaja la configuración de estilos de impresión para crear una factura lista para ser impresa y archivada.

---

## Aspectos técnicos

* **Tecnologías utilizadas:**

  * HTML (estructura de la factura)
  * CSS (estilos de visualización e impresión)
* **Conceptos clave:**

  * Regla `@page` para impresión
  * Formato de papel A4
  * Unidades físicas en CSS (mm)
  * Tipografía serif para documentos formales
* **Objetivo técnico:**

  * Adaptar una página web para impresión profesional

---

## Ejemplo práctico

### 1. Configuración de estilos CSS para impresión

```css id="css_print_001"
@page {
    size: A4;
    margin: 20mm;
}

body {
    width: 210mm;
    height: 297mm;
    margin: 0;
    padding: 0;
    font-family: serif;
}
```

---

### 2. Ejemplo básico de estructura de factura

```html id="html_invoice_001"
<!DOCTYPE html>
<html>
<head>
    <title>Factura</title>

    <style>
        @page {
            size: A4;
            margin: 20mm;
        }

        body {
            width: 210mm;
            height: 297mm;
            margin: 0;
            padding: 0;
            font-family: serif;
        }

        .factura {
            padding: 20mm;
        }

        h1 {
            text-align: center;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        table, th, td {
            border: 1px solid black;
        }

        th, td {
            padding: 8px;
            text-align: left;
        }
    </style>
</head>

<body>

<div class="factura">

    <h1>Factura</h1>

    <p><strong>Cliente:</strong> Juan Pérez</p>
    <p><strong>Fecha:</strong> 10/06/2026</p>

    <table>
        <tr>
            <th>Producto</th>
            <th>Cantidad</th>
            <th>Precio</th>
        </tr>

        <tr>
            <td>Teclado</td>
            <td>1</td>
            <td>25.50 €</td>
        </tr>

        <tr>
            <td>Monitor</td>
            <td>1</td>
            <td>180.00 €</td>
        </tr>
    </table>

    <h3>Total: 205.50 €</h3>

</div>

</body>
</html>
```

---

## ¿Para qué sirve?

Este tipo de configuración sirve para:

* Generar facturas imprimibles desde páginas web.
* Adaptar documentos digitales a formato físico.
* Crear reportes empresariales en PDF o impresión directa.
* Cumplir requisitos de documentación oficial.
* Mejorar la presentación de documentos comerciales.

---

## Conclusión

El uso de CSS para impresión permite transformar una página web en un documento profesional listo para papel A4. Mediante propiedades como `@page`, unidades en milímetros y tipografía serif, es posible crear facturas bien estructuradas y compatibles con impresión. Este conocimiento es fundamental en sistemas de gestión empresarial y aplicaciones de facturación.
