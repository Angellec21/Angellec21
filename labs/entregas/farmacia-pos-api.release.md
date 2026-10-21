# farmacia-pos-api v1.0.0

Primera versión estable de la API REST para farmacias pequeñas y medianas de Bolivia: controla lotes y vencimientos, vende siempre lo que vence primero (FEFO) y le da al dueño reportes en Bs para decidir qué comprar y cuánto gana.

## Funcionalidades principales

- **Inventario por lotes**: cada lote con costo y fecha de vencimiento; la salida de stock es FEFO y nunca usa lotes vencidos.
- **Alertas**: lotes vencidos o por vencer con el dinero en riesgo (Bs) y productos bajo el stock mínimo.
- **Ventas**: todo-o-nada, con trazabilidad de lotes por ítem, pago en efectivo/QR/tarjeta y cálculo de cambio.
- **Caja**: ticket para impresora térmica de 58 mm y cierre diario por cajero o de todo el local.
- **Compras y proveedores**: droguerías con días de crédito, ingreso de lotes por factura, cuentas por pagar y abonos.
- **Seguridad**: login JWT, contraseñas con scrypt y permisos por rol (admin / cajero); el cajero no ve costos ni márgenes.
- **Reportes del dueño**: más vendidos, margen por producto y ventas por cajero.
- **Persistencia**: todo se guarda en un archivo JSON con escritura atómica antes de responder cada operación.
- **Datos de ejemplo**: una farmacia de Santa Cruz lista para probar (`npm run seed`).

## Cómo ejecutarlo

Requiere Node.js 20 o superior.

```bash
git clone https://github.com/Angellec21/farmacia-pos-api.git
cd farmacia-pos-api
npm install
npm run seed   # opcional: carga la farmacia de ejemplo y muestra los usuarios
npm start      # http://localhost:3000
```

Configuración en `.env` (ver `.env.example`): `JWT_SECRET`, `ADMIN_PASSWORD`, `DATA_FILE`, datos del negocio para el ticket.

## Calidad

- **92 pruebas** automáticas (Jest + Supertest): servicios, endpoints, permisos y persistencia.
- CI en GitHub Actions con Node 20, 22 y 24 en cada push y pull request.

Detalle completo en el [CHANGELOG](https://github.com/Angellec21/farmacia-pos-api/blob/main/CHANGELOG.md).
