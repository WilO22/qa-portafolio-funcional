# Módulo 1 - Práctica en SauceDemo

Ejemplos prácticos realizados sobre `https://www.saucedemo.com/` usando `standard_user` / `secret_sauce` y observaciones con `problem_user`.

## 1. Ejemplos de tipos de prueba (con `standard_user`)

### Prueba funcional
Validar que el filtro de ordenamiento en el catálogo cumpla su regla. Al elegir la opción **Price (low to high)** en la parte superior derecha, los productos deben reordenarse de menor a mayor precio: primero debe aparecer *Sauce Labs Onesie* ($7.99) y al final *Sauce Labs Fleece Jacket* ($49.99).

### Prueba no funcional
Comprobar qué tan rápido carga la pantalla de productos (`/inventory.html`) apenas presiono el botón **Login**, y revisar también la parte visual/usabilidad: que las 6 tarjetas de productos no se deformen ni se corten si achico la ventana del navegador o la abro en una pantalla más pequeña.

### Smoke test
Si recibo una versión nueva (build) de la tienda, hago una pasada rápida por lo más básico para ver si vale la pena seguir probando: entro con `standard_user`, confirmo que cargue el catálogo de productos, agrego un artículo con **Add to cart** para ver si sube el contador del carrito y abro el menú lateral para probar el **Logout**. Si algo de eso falla, no tiene sentido seguir probando a detalle.

### Prueba de regresión
Imagino que el equipo de desarrollo modificó la lógica del menú lateral o del filtro de ordenamiento. Además de probar ese cambio, vuelvo a revisar flujos que antes ya funcionaban bien —como entrar al detalle de *Sauce Labs Backpack*, agregarlo al carrito y cerrar sesión— para asegurarme de que el cambio no rompió otra parte de la tienda.

### Prueba de aceptación
Antes de sacar la tienda al público, el dueño del negocio o un usuario final recorre todo el flujo real de compra desde que inicia sesión hasta completar el pedido, para confirmar que el sistema de verdad le sirve para vender y cumple con lo que esperaba, no solo que funcione a nivel técnico.

---

## 2. Ejemplo de Error → Defecto → Falla (observado con `problem_user`)

* **Causa raíz:** Falta de revisión en el código o un criterio de aceptación poco claro antes de pasar el módulo a pruebas.
* **Error (equivocación humana):** El desarrollador olvidó conectar la función que se activa al hacer clic en el botón **Add to cart** dentro de la vista de detalle del producto.
* **Defecto (bug en el código):** En el código de la página de detalle, el botón **Add to cart** no tiene asociada la llamada a la función para sumar el producto al carrito.
* **Falla (lo que veo en pantalla al probar):** Al ingresar con `problem_user`, abrir el detalle de un producto y hacer clic en **Add to cart**, el botón no hace absolutamente nada y el contador del carrito sigue vacío.
