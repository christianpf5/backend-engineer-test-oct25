# StockSync CLI 

Esta es una prueba técnica para la posición de Backend Engineer en Greenvase.es.

## Objetivo

Desarrollar un CLI que sincronice el stock de 100,000 productos desde nuestro ERP hacia los canales de venta:
- **Greenvase.es**: ecommerce propio basado en WooCommerce
- **Makro**: marketplace líder en el canal horeca con API propia

## Instrucciones

- Haz un fork de este repositorio, implementa los requisitos y envíanos el enlace por correo electrónico
- Puedes utilizar cualquier lenguaje de programación, framework o tecnología
- Si algún requisito no es suficientemente claro, toma decisiones de negocio razonables y documéntalas en el README
- Actualiza el README con los pasos necesarios para ejecutar el proyecto
- Si necesitas más de 4-5 horas, documenta qué habrías implementado con más tiempo
- Incluye una sección con los requisitos pendientes para producción
- ¡Buena suerte!



## Requisitos

- El comando de sincronización de stock debe permitir elegir si se sincroniza con Makro o con WooCommerce.
- Debe ofrecer dos modos de funcionamiento: increme ntal y completo. En el modo incremental, solo se sincronizan los productos que han cambiado desde la última sincronización. En el modo completo, se sincronizan todos los productos.
- El CLI debe poder ejecutarse en varios procesos al mismo tiempo sin generar inconsistencias, permitiendo repartir la actualización de productos entre varios procesos sin que se solapen.
- Se deben definir reglas de negocio para decidir cómo actualizar el stock de cada producto o categoría. Estas reglas pueden aplicarse tanto a nivel de producto como de categoría. No todos los 100k productos tendrán reglas, serán muy pocas al principio. Las opciones disponibles para cada producto son:
  - Actualizar el stock real del producto según el ERP.
  - Forzar que el producto aparezca siempre como fuera de stock en un canal de venta (WooCommerce o Makro).
  - Forzar que el producto tenga stock disponible aunque el ERP indique que no hay stock.
  - Definir un stock mínimo para el producto; si no se alcanza, marcarlo como fuera de stock.




