# Libro Mayor — Cartera & Vehículos

Prototipo funcional para el negocio de **préstamos de dinero y compraventa de vehículos (carros y motos)** en Caucasia, con socios capitalistas. Construido por Vibras Positivas HM como punto de partida para validar la idea con el cliente antes de definir la versión final.

## Qué hace ahora mismo

- **Acceso por token**: el administrador crea el negocio y se genera un código único (ej. `CAU-7K2P9X`). Ese mismo código se usa para entrar desde otro celular o el PC de la oficina y ver la misma información — funciona como una contraseña compartida.
- **Clientes**: nombre, dirección, celular, observaciones, forma de pago. Datos sensibles (celular, dirección) aparecen enmascarados salvo en "modo administrador" (Habeas Data — Ley 1581 de 2012).
- **Préstamos**: monto, interés mensual, fecha, fecha límite, abonos parciales con historial, saldo automático, sello visual (PAGADO / PENDIENTE / VENCIDO).
- **Vehículos (carros y motos)**: marca, modelo, placa, comprador, precio, abonos, saldo, qué socio financió la compra.
- **Socios capitalistas**: nombre, celular, capital aportado, y en cuántos préstamos/vehículos participa.
- **Movimientos**: registro histórico de todo (préstamo nuevo, venta, abono) que sirve de soporte.
- **Botones en cada registro**: ✏️ Editar · 🖨️ Imprimir (formato de recibo) · 💬 Enviar por WhatsApp (manda un comprobante con los datos de la transacción).
- **Backup**: descarga toda la información del negocio en un archivo `.json`. Restaurar backup la carga de nuevo.
- **Panel de administración**: muestra el token, botón para copiarlo o enviarlo por WhatsApp (para sincronizar otro dispositivo), y permite activar el "modo administrador" para ver los datos completos de los clientes.

## Cómo se guardan los datos

Esta versión usa el almacenamiento del artefacto de Claude (`window.storage`, modo compartido) en lugar de una base de datos propia. Es ideal para **probar la idea con el cliente rápido**, pero conviene tener claro:

- El token actúa como contraseña: cualquiera que lo conozca y abra este mismo enlace puede ver y editar los datos del negocio.
- Es un prototipo de validación, no un sistema de producción. Cuando el cliente confirme que esta es la idea, lo recomendable es migrarlo a una base de datos real (por ejemplo, siguiendo el mismo patrón de `api-vibras`: Node.js/Express + base de datos propia), para tener control total, copias de seguridad automáticas y mejor seguridad.

## Pendiente para siguientes iteraciones

- PIN o clave adicional para el modo administrador (hoy es un interruptor sin contraseña).
- Reportes por socio (cuánto ha invertido, cuánto ha generado cada uno).
- Alertas automáticas de cartera vencida.
- Manifest con íconos reales + Service Worker para instalación offline completa.
- Definir con el cliente: ¿el token lo genera un solo administrador o cada socio necesita su propio acceso con permisos distintos?

## Dato de contacto temporal

El celular de administrador quedó configurado como `3117700431` (de Harold) mientras llega el cliente. Se actualiza desde el panel de administración (ícono de engranaje) en cuanto el cliente confirme su número.

---
Desarrollada por Vibras Positivas HM — Derechos de Autor Reservados
