# boutique-inventario v1.0.0

Primera versión estable de la API de inventario para tiendas de ropa con varias sucursales: cada prenda se controla por talla y color, con stock separado por tienda, transferencias, ventas en caja y reportes en Bs para que el dueño decida qué reponer y cuánto gana.

## Funcionalidades principales

- **Catálogo y variantes**: productos con precio, costo y margen en Bs; combinaciones talla × color con SKU automático (`BLU-001-NEG-M`) y generación de la matriz completa.
- **Stock por sucursal**: ingresos de mercadería, ajustes por conteo físico con motivo, kardex de movimientos y matriz talla × color con valor de la mercadería.
- **Alertas de reposición**: variantes bajo su mínimo, indicando cuánto hay en otras tiendas para transferir antes de comprar.
- **Transferencias**: envío entre sucursales con stock en tránsito, recepción con registro de faltantes y anulación.
- **Ventas en caja**: descuentos por línea, pago en efectivo (con cambio), QR o tarjeta, y anulaciones que devuelven las prendas al stock.
- **Reportes del dueño**: más vendidos con margen, ventas por talla, cierre de caja por método de pago y vendedor, valor del inventario por sucursal.
- **Seguridad**: login JWT, contraseñas con PBKDF2 y roles administrador / encargado (limitado a su tienda, sin ver costos ni reportes).
- **Persistencia y respaldo**: todo se guarda en un archivo JSON con escritura atómica; el administrador descarga un respaldo completo con `GET /respaldo`.
- **Datos de ejemplo**: una boutique de Santa Cruz con 3 tiendas, 54 variantes y dos semanas de ventas (`python -m app.datos_ejemplo`).

## Cómo ejecutarlo

Requiere Python 3.11 o superior.

```bash
git clone https://github.com/Angellec21/boutique-inventario.git
cd boutique-inventario
python -m venv .venv && source .venv/bin/activate
pip install -r requirements-dev.txt
python -m app.datos_ejemplo   # opcional: carga la boutique de ejemplo (usuario rosa / Boutique2026)
uvicorn app.main:app --reload # documentación interactiva en http://localhost:8000/docs
```

Configuración por variables de entorno: `BOUTIQUE_SECRET`, `BOUTIQUE_ADMIN_USUARIO`, `BOUTIQUE_ADMIN_CLAVE`, `BOUTIQUE_DATOS`.

## Calidad

- **139 pruebas** automáticas (pytest + TestClient): servicio, endpoints, permisos por rol, persistencia y respaldo.
- CI en GitHub Actions con Python 3.11, 3.12 y 3.13 en cada push y pull request.

Detalle completo en el [CHANGELOG](https://github.com/Angellec21/boutique-inventario/blob/main/CHANGELOG.md).
