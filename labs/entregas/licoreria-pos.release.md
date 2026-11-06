# licoreria-pos v1.0.0

Primera versión estable del punto de venta para licorerías de barrio en Santa Cruz de la Sierra: venta por unidad y por caja cerrada, caja por turnos con arqueo, control de stock y reporte del día para el dueño, todo en bolivianos (Bs) y funcionando directamente en el navegador.

## Funcionalidades principales

- **Venta por unidad y por caja**: la botella suelta y la caja de 12 con su propio precio; el stock se lleva siempre en unidades y se muestra desglosado (*8 cajas + 3 u.*).
- **Pantalla de cobro**: lector de código de barras USB (`3*código` vende 3 unidades, `c*código` una caja), búsqueda sin tildes, carrito editable y sugerencia de ahorro cuando conviene llevar la caja.
- **Cobro** en efectivo con cálculo de cambio, QR o tarjeta; ventas todo o nada (si falta stock de un producto no se descuenta ninguno).
- **Ticket** para impresora térmica de 58/80 mm y copia del ticket desde *Ventas del turno*.
- **Caja por turnos**: apertura con monto inicial, anulaciones con motivo y hora, y cierre con arqueo (efectivo esperado, faltante o sobrante, margen del turno).
- **Inventario**: alertas de stock mínimo, ingreso de mercadería con proveedor y factura, costo promedio ponderado y pedido sugerido en cajas.
- **Reporte del día**: total, margen bruto en Bs y %, ticket promedio, ventas por hora con hora pico, más vendidos, margen por categoría, métodos de pago y ventas por cajero; exportación a CSV para Excel.
- **Guardado automático** en el navegador, respaldo descargable en JSON y restauración validada.
- **Datos de ejemplo**: licorería de Santa Cruz con 13 productos y una semana de ventas, compras y arqueos, para probar los reportes desde el primer minuto.

## Cómo ejecutarlo

Requiere Node.js 20.19 o superior.

```bash
git clone https://github.com/Angellec21/licoreria-pos.git
cd licoreria-pos
npm install
npm run dev     # http://localhost:5173
```

Producción: `npm run build` y `npm run preview`.

## Calidad

- **84 pruebas** automáticas con Vitest sobre la lógica de negocio (inventario, caja, carrito, ticket, reporte, guardado y datos de ejemplo).
- TypeScript en modo estricto; CI en GitHub Actions con Node 20, 22 y 24 (pruebas y build) en cada push y pull request.

Detalle completo en el [CHANGELOG](https://github.com/Angellec21/licoreria-pos/blob/main/CHANGELOG.md).
