# Dashboard Integrador de Servicios Digitales (Frontend API Consumer)

**Materia:** Interacción de Servicios Digitales  
**Unidad:** 2 - Práctica 2  

---

## 📄 Descripción de la Arquitectura Client-Side

Este proyecto consiste en una **Single Page Application (SPA)** desarrollada en HTML5, JavaScript Vanilla y estilizada con Tailwind CSS. La aplicación actúa como un centro de control cliente que interactúa con servicios web mediante protocolos de la capa de aplicación.

### Módulos Implementados

#### 1. Subárea b: Comercio Electrónico (E-Commerce)
* **Endpoint Consumido:** `https://fakestoreapi.com/products`
* **Método HTTP:** `GET`
* **Manejo Asíncrono:** Uso de `async/await` con bloques `try/catch` para la captura de fallos de red.
* **Seguridad:** Simulación de inserción del encabezado de autorización seguro: `Authorization: Bearer <JWT_TOKEN>`.
* **Manipulación del Estado:** Gestión en memoria del carrito de compras (`cart[]`) con cálculo dinámico de totales y renderizado en el DOM sin recarga de página.

#### 2. Subárea a: Notificaciones y Correo Electrónico
* **Concepto:** Consumo de servicio de correo/notificaciones en el cliente enviando un payload estructurado en JSON.
* **Headers:** `Content-Type: application/json`
* **Control de Errores y Estados HTTP:** Manejo simulado y explícito de respuestas:
  * `200 OK`: Petición procesada correctamente.
  * `400 Bad Request`: Payload estructurado de forma errónea.
  * `401 Unauthorized`: Ausencia o invalidez del token de autenticación.

---

## 🛠️ Guía de Ejecución Local

1. Clona este repositorio o descarga los archivos.
2. Abre el archivo `index.html` directamente en cualquier navegador moderno (Google Chrome, Firefox, Edge).
3. No requiere instalación de dependencias ni servidores locales (Node.js/NPM), ya que utiliza Tailwind CSS e Iconos Lucide desde CDN.

---

## 🔍 Guía para la Exposición (Tech Demo - Pestaña Network)

Para la validación de la práctica durante la demostración técnica:

1. Abre la **Developer Tools** en el navegador (`F12` o `Clic derecho -> Inspeccionar`).
2. Ve a la pestaña **Network (Red)** y asegúrate de filtrar por **Fetch/XHR**.
3. **Punto B (E-Commerce):** Recarga la página o cambia a la pestaña del catálogo y observa la petición `GET /products`. Al hacer clic sobre ella:
   * Verifica los **Headers de Solicitud** (`Request Headers`) para comprobar el encabezado `Authorization: Bearer ...`.
   * Observa el **Status Code: 200 OK**.
4. **Punto A (Notificaciones):** Envía el formulario de correo:
   * Revisa la vista previa del **Payload JSON** generado.
   * Cambia el selector de "Status Simulado" para probar los comportamientos de error `400 Bad Request` y `401 Unauthorized` procesados mediante `try/catch`.