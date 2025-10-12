# StockSync CLI 

Esta prueba técnica forma parte del proceso de selección para Backend Engineer en Greenvase.es.
Tu tarea será diseñar y desarrollar una herramienta de línea de comandos (CLI) para sincronizar inventarios entre distintos sistemas.

## Objetivo

Construir una CLI capaz de sincronizar automáticamente el stock de productos desde un ERP interno hacia diferentes canales de venta:

- **Origen**: ERP interno (100,000 productos)
- **Destinos**: 
  - Greenvase.es (tienda online con WooCommerce)
  - Makro (marketplace para hostelería)

El resultado debe ser una herramienta robusta, escalable y concurrente, que pueda operar sin inconsistencias al ejecutarse en paralelo.

## Instrucciones

- Haz un fork de este repositorio, implementa los requisitos y envíanos el enlace por correo electrónico
- Puedes utilizar cualquier lenguaje de programación, framework o tecnología
- Si algún requisito no es suficientemente claro, toma decisiones de negocio razonables y documéntalas en el README
- Actualiza el README con los pasos necesarios para instalar, ejecutar y probar el proyecto
- Si necesitas más de 4-5 horas, deja documentado donde te quedaste y qué habrías implementado con más tiempo
- Incluye una sección con los requisitos pendientes para producción

## Requisitos

- El comando de sincronización de stock debe permitir elegir si se sincroniza con Makro o con WooCommerce.
- Debe ofrecer dos modos de funcionamiento: incremental y completo. En el modo incremental, solo se sincronizan los productos que han cambiado desde la última sincronización. En el modo completo, se sincronizan todos los productos.
- El CLI debe poder ejecutarse en varios procesos al mismo tiempo sin generar inconsistencias, permitiendo repartir la actualización de productos entre varios procesos sin que se solapen.
- Usa el SKU como identificador único del producto.
- Se deben definir reglas de negocio para decidir cómo actualizar el stock de cada producto o categoría. Estas reglas pueden aplicarse tanto a nivel de producto como de categoría. No todos los 100k productos tendrán reglas, serán muy pocas al principio. Las opciones disponibles para cada producto son:
  - Actualizar el stock real del producto según el ERP.
  - Forzar que el producto aparezca siempre como fuera de stock en un canal de venta (WooCommerce o Makro).
  - Forzar que el producto tenga stock disponible aunque el ERP indique que no hay stock.
  - Definir un stock mínimo para el producto; si no se alcanza, marcarlo como fuera de stock.
- Las definiciones de las APIs están disponibles en el directorio `openapi`. Para facilitar las pruebas, puedes utilizar el servidor mock proporcionado a través de https://spotlight.io/. Las APIs pueden consultarse usando la siguiente URL de mock server: https://greenvase.stoplight.io/docs/greenvase-test/9rlphke1phdj8-erp-system-api
- No hace falta implementar la autenticación para las APIs.

¡Buena suerte!



