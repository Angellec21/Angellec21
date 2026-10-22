# Progreso de proyectos comerciales

Archivo de estado del plan diario de proyectos. Lo actualiza la tarea programada.

## Proyecto actual

**2. boutique-inventario** (Python/FastAPI): inventario para tienda de ropa. Día 1 completado (2026-10-22). Último commit: `3617638`. 27 pruebas pasando.

- Hecho: catálogo con precio/costo en Bs y margen, variantes talla × color con SKU automático y generación de matriz, stock por sucursal (ingresos todo-o-nada, ajustes por conteo con motivo, kardex), matriz de stock talla × color con valor en Bs, alertas de reposición con stock en otras sucursales, API FastAPI, CI (Python 3.11–3.13), README, topics.
- Falta: transferencias entre sucursales (envío/recepción), ventas con descuento de stock y anulaciones, reporte de más vendidos y rotación por talla, usuarios/roles, persistencia (SQLite) y datos de ejemplo de Santa Cruz, release v1.0.0.
- Nota: el repo ya existía en GitHub con un "Initial commit" (README + LICENSE); el trabajo se hizo encima de `911c841` (origin/main es ancestro del bundle). En el README de perfil va sin enlace hasta que el Mac publique el bundle.

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

## Lista de proyectos

| # | Proyecto | Estado |
|---|----------|--------|
| 1 | farmacia-pos-api | Terminado |
| 2 | boutique-inventario | En desarrollo (día 1) |
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
