# Todo Jardín V3 — prototipo funcional

Este es un prototipo front-end responsive que permite probar los principales flujos como demostración.

## Funciones de la V3
- Catálogo con búsqueda y filtros, carrito y solicitud de entrega.
- Formulario de pedido que guarda una copia local en el navegador y prepara un mensaje de WhatsApp.
- Diseñador de jardín 2D: dimensiones, elementos, selección, arrastre en escritorio, controles de posición en móvil, etiquetas y cantidades.
- Resumen de materiales y precios de referencia.
- Guardar y recuperar un proyecto en el mismo navegador (`localStorage`).
- Exportar proyecto a JSON.
- Imprimir/guardar el plano y presupuesto como PDF desde el diálogo de impresión del navegador.
- Solicitud de cotización que incorpora el resumen del diseño a WhatsApp.

## Configuración para demo
En `app.js`, sustituye `WHATSAPP_NUMBER` por el número de la tienda (código de país y número, solo dígitos). Reemplaza catálogo, precios, fotos, horarios y políticas por datos autorizados.

## Límites importantes
- Los pedidos y proyectos guardados en `localStorage` solo existen en ese navegador/dispositivo; no los ve el personal desde otro equipo.
- No procesa pagos ni cobra tarjetas. La opción de pago con tarjeta es solo una preferencia dentro de la solicitud.
- No hay autenticación real, roles de personal, inventario compartido, bloqueo de horario, notificaciones automáticas ni panel de administración multiusuario.
- El presupuesto usa importes de demostración por elemento; no es una cotización técnica y no calcula automáticamente geometrías complejas, desperdicio, instalación, transporte o impuestos.
- WhatsApp se abre para enviar el mensaje; el usuario debe enviarlo manualmente.
- Las imágenes externas requieren conexión a internet.

## Qué se requiere para producción
1. Backend y base de datos (por ejemplo, Firebase o Supabase) para productos, inventario, usuarios, proyectos, cotizaciones, pedidos y estados.
2. Pasarela de pago mexicana (por ejemplo, Mercado Pago o Stripe, sujeto a elegibilidad y condiciones comerciales), con creación de sesiones de pago en backend, webhooks y confirmación del servidor. Nunca guardar datos de tarjetas directamente.
3. Backend para validar precios, inventario, envío, cupones y total final antes del cobro.
4. Gestión de entrega: cobertura por CP/colonia, tarifas, horarios/cupos, políticas de cambios/cancelaciones y notificaciones.
5. Panel privado para personal: editar productos, existencias, costos, aprobar cotizaciones, convertirlas a pedidos y dar seguimiento.
6. Aviso de privacidad, términos de compra, políticas de envío/devolución, facturación y soporte; confirmar requisitos fiscales y de protección al consumidor con asesoría local.
7. Dominio propio y HTTPS para producción. GitHub Pages sirve para el frontend estático, pero no es el backend ni un entorno seguro para secretos.
8. Pruebas en móvil, accesibilidad, copias de seguridad, manejo de errores y monitoreo.

## Publicar la demo
Sube `index.html`, `styles.css`, `app.js` y `README.md` a un repositorio `todo-jardin`, y activa **Settings → Pages → Deploy from a branch → main → /(root)**. URL aproximada: `https://TU-USUARIO.github.io/todo-jardin/`.
