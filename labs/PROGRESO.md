# Progreso de proyectos comerciales

Archivo de estado del plan diario de proyectos. Lo actualiza la tarea programada.

## Proyecto actual

**2. boutique-inventario** (Python/FastAPI): inventario para tienda de ropa. Día 5 completado (2026-10-28). Último commit: `a95fcf6`. 133 pruebas pasando.

- Hecho: catálogo con precio/costo en Bs y margen, variantes talla × color con SKU automático, stock por sucursal (ingresos, ajustes, kardex), matriz de stock, alertas de reposición, transferencias entre sucursales, ventas en caja (descuentos, efectivo/QR/tarjeta, anulaciones), reportes del dueño, **usuarios y roles** (login JWT, admin / encargado limitado a su sucursal, costos y reportes solo para admin, gestión de usuarios), **persistencia en archivo JSON** (escritura atómica, incluye usuarios, se guarda tras cada cambio), **datos de ejemplo** de una boutique de Santa Cruz (`python -m app.datos_ejemplo`), CI, README, topics.
- Falta (día 6, final): versión 1.0.0 (pyproject y API), CHANGELOG, README final y notas de la release `labs/entregas/boutique-inventario.release.md`.

## Bitácora

- 2026-10-07: se creó este archivo. No se pudo avanzar en farmacia-pos-api porque la sesión no pudo adjuntar el repo (la herramienta `add_repo` no estaba disponible).

- 2026-10-07 (más tarde): se programó el día 1 de farmacia-pos-api (3 commits, 22 pruebas). Se entregó a Angel como .zip con historial para que cree el repo y lo publique desde su Mac.

- 2026-10-08: día 2 de farmacia-pos-api — servicio y endpoints de ventas, ticket térmico, resumen diario, README con arquitectura (3 commits, 39 pruebas). Push rechazado (repo fuera de las fuentes de la sesión); se entregó bundle + parches a Angel.

- 2026-10-09: sin avance. El repo farmacia-pos-api sigue en el día 1 (no se aplicó el bundle del día 2) y el push volvió a ser rechazado por el proxy (repo fuera de las fuentes autorizadas de la sesión). No se rehízo el trabajo para no duplicar ni chocar con el bundle del día 2 pendiente.

- 2026-10-10: sin avance, mismo bloqueo. `add_repo` no está disponible en la sesión y el proxy rechaza el push a farmacia-pos-api (no está en las fuentes autorizadas). El repo remoto sigue en `82fa9d2` (día 1). Solución: agregar los repos de proyectos a las fuentes de la tarea programada (o instalar la app de Claude con acceso a ellos) y aplicar el bundle del día 2.

- 2026-10-13: sin avance, mismo bloqueo (4.º día seguido). `add_repo` sigue sin estar disponible y el acceso a farmacia-pos-api es rechazado (la sesión solo autoriza Angellec21/angellec21). El repo remoto sigue en `82fa9d2` (día 1). Solución: en la configuración de la tarea programada, agregar los 12 repos de proyectos como fuentes (o habilitar `add_repo`) y aplicar el bundle del día 2.

- 2026-10-14: sin avance, mismo bloqueo (5.º día seguido). `add_repo` sigue sin aparecer en la sesión y el proxy rechaza el push a farmacia-pos-api (403: no está en las fuentes autorizadas; solo Angellec21/angellec21). El repo remoto sigue en `82fa9d2` (día 1). Solución: en la tarea programada (app de Claude → Tareas programadas → esta tarea → Fuentes/Repositorios) agregar farmacia-pos-api y los demás repos de proyectos, o instalar la app de Claude en GitHub con acceso a ellos.

- 2026-10-15: sin avance, mismo bloqueo (6.º día seguido). `add_repo` sigue sin estar disponible y el proxy rechaza el push a farmacia-pos-api con 403 ("not in this session's authorized repository set"). El repo remoto sigue en `82fa9d2` (día 1). Solución: en la tarea programada (app de Claude → Tareas programadas → esta tarea → Fuentes/Repositorios) agregar farmacia-pos-api y los otros 11 repos de proyectos.

- 2026-10-15 (día 2, rehecho con el nuevo flujo de bundles): el bundle del 2026-10-08 nunca llegó al repo, así que se rehízo el día 2 sobre `82fa9d2`. Commits: `e6a490f` feat: ventas todo-o-nada con FEFO y trazabilidad de lotes; `d004857` feat: ticket térmico de 58 mm y cierre de caja diario (incluye README con arquitectura). 37 pruebas pasando. Entregado en `labs/entregas/farmacia-pos-api.bundle`.

- 2026-10-16 (día 3): se continuó desde el bundle del día 2 (aún no publicado; origin/main es ancestro). Commits: `75c85d5` feat: proveedores y compras con ingreso de lotes y cuentas por pagar; `9af2fec` feat: endpoints de proveedores, compras y cuentas por pagar (README actualizado). 49 pruebas pasando. Bundle actualizado con días 2 y 3.

- 2026-10-18: la tarea "Preparar repos en Mac" estaba pausada desde el 15-oct (no encontraba el Mac). Angel la reactivó y la ejecutó a mano: días 2 y 3 publicados (`origin/main` = `9af2fec`).

- 2026-10-19 (día 4): `origin/main` ya tenía los días 1–3 (bundle anterior publicado). Commits: `a34c0f5` feat: autenticación JWT con usuarios y contraseñas cifradas; `402119b` feat: permisos por rol admin/cajero en ventas, productos y compras (README con tabla de permisos). 65 pruebas pasando. Bundle actualizado.

- 2026-10-20 (mejoras de perfil, a pedido de Angel): `115da62` ci: pruebas automáticas en GitHub Actions con Node 20, 22 y 24 + insignias en el README. Temas del repo en `labs/entregas/farmacia-pos-api.topics`. README de perfil: tabla de proyectos con estado e insignia de CI (los repos aún vacíos ya no tienen enlace). Nuevas reglas para las tareas: commits por etapa, CI desde el día 1, release v1.0.0 al terminar y repos creados solo cuando ya tienen contenido.

- 2026-10-20 (día 5): se continuó desde el bundle (origin/main = `402119b`, ancestro). Commits: `8b56fcb` feat: reportes del dueño (más vendidos, margen por producto, ventas por cajero); `907470d` feat: endpoints /reportes para el dueño, solo admin (README actualizado). 77 pruebas pasando. Bundle actualizado. README de perfil: descripción de farmacia-pos-api con reportes.

- 2026-10-21 (día 6, final): `origin/main` ya tenía los días 1–5 (`907470d`). Commits: `658bc8c` feat: persistencia en archivo JSON con guardado automático (escritura atómica, carga al iniciar); `3de7a9b` feat: datos de ejemplo de una farmacia de Santa Cruz (`npm run seed`); `158f9a7` docs: versión 1.0.0 con CHANGELOG y README final. 92 pruebas pasando. Se eligió archivo JSON en vez de SQLite porque `node:sqlite` no existe en Node 20 (incluido en el CI); SQLite/PostgreSQL queda en el roadmap. Notas de la release en `labs/entregas/farmacia-pos-api.release.md`. **farmacia-pos-api terminado (v1.0.0).** README de perfil: marcado como Terminado.

- 2026-10-22 (boutique-inventario, día 1): base sobre `911c841` (Initial commit ya publicado). Commits: `5526da5` feat: catálogo con variantes por talla y color y stock por sucursal; `f5cfe1b` feat: API REST con FastAPI para catálogo, variantes y stock (incluye CI); `3617638` docs: README con problema de negocio, arquitectura y uso de la API (LICENSE a nombre de Angel). 27 pruebas pasando. Entregado en `labs/entregas/boutique-inventario.bundle` + `.topics`.

- 2026-10-23 (boutique-inventario, día 2): `origin/main` ya tenía el día 1 (`3617638`, publicado por el Mac). Commits: `65f7617` feat: transferencias entre sucursales con envío, recepción y anulación; `16f049a` feat: endpoints de transferencias entre sucursales; `d288c52` docs: transferencias en el README con ciclo de vida y ejemplos. 43 pruebas pasando. Bundle actualizado. README de perfil: boutique-inventario ya con enlace e insignia de CI.

- 2026-10-26 (boutique-inventario, día 3): el Mac aún no había publicado el día 2 (`origin/main` = `3617638`, ancestro del bundle); se continuó desde el bundle. Commits: `6de1bb5` feat: ventas en caja con descuento de stock y anulaciones; `d4c5b15` feat: reportes de más vendidos, ventas por talla, cierre de caja y valor de inventario; `034848f` feat: endpoints de ventas y reportes del dueño (README actualizado). 68 pruebas pasando. Bundle actualizado con días 2 y 3.

- 2026-10-27 (boutique-inventario, día 4): `origin/main` ya tenía el día 3 (`034848f`, publicado por el Mac). Commits: `6454ace` feat: usuarios con contraseñas cifradas (PBKDF2) y tokens JWT; `aa98b15` feat: inicio de sesión y permisos por rol en toda la API (encargado limitado a su sucursal, costos/reportes/anulaciones solo admin); `6d79ad0` docs: roles y permisos, configuración de acceso y ejemplos con token. 107 pruebas pasando. Bundle actualizado. README de perfil: descripción con roles y 107 pruebas.

- 2026-10-28 (boutique-inventario, día 5): `origin/main` ya tenía el día 4 (`6d79ad0`, publicado por el Mac). Commits: `a56788e` feat: persistencia del inventario y usuarios en archivo JSON (escritura atómica, carga todo o nada); `b58d916` feat: la API guarda cada cambio y recupera los datos al reiniciar (`BOUTIQUE_DATOS`); `a95fcf6` feat: datos de ejemplo de una boutique de Santa Cruz (3 tiendas, 54 variantes, 2 semanas de ventas, usuarios demo). 133 pruebas pasando. Se eligió archivo JSON (igual que farmacia-pos-api); SQLite/PostgreSQL queda en el roadmap. Bundle actualizado. README de perfil: descripción con persistencia, datos de ejemplo y 133 pruebas.

## Lista de proyectos

| # | Proyecto | Estado |
|---|----------|--------|
| 1 | farmacia-pos-api | Terminado |
| 2 | boutique-inventario | En desarrollo (día 5) |
| 3 | licoreria-pos | Siguiente |
| 4 | zapateria-catalogo-web | Pendiente |
| 5 | erp-pymes-api | Pendiente |
| 6 | ferreteria-stock | Pendiente |
| 7 | restaurante-comandas | Pendiente |
| 8 | distribuidora-catalogo-web | Pendiente |
| 9 | rrhh-planillas-api | Pendiente |
| 10 | crm-ventas-api | Pendiente |
| 11 | dashboard-gerencial-react | Pendiente |
| 12 | minimarket-pos-web | Pendiente |

## Proyectos terminados

- [farmacia-pos-api](https://github.com/Angellec21/farmacia-pos-api) — v1.0.0 (2026-10-21), 92 pruebas, último commit `158f9a7`. Release pendiente de crear por el Mac con `labs/entregas/farmacia-pos-api.release.md`.
