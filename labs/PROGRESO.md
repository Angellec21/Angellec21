# Progreso de proyectos comerciales

Archivo de estado del plan diario de proyectos. Lo actualiza la tarea programada.

## Proyecto actual

**1. farmacia-pos-api** (Node.js/Express): sistema para farmacias.
Repo: https://github.com/Angellec21/farmacia-pos-api

- Estado: día 4 de ~6. Publicado en GitHub hasta `9af2fec` (días 1 a 3); día 4 (`a34c0f5`, `402119b`) en el bundle, pendiente de publicar desde el Mac.
- Hecho: estructura Express + Jest, productos con lotes, salida FEFO, alertas de vencimiento/stock mínimo, ventas todo-o-nada con trazabilidad de lotes, ticket térmico de 58 mm, cierre de caja diario, proveedores y compras con cuentas por pagar, autenticación JWT (scrypt para contraseñas) con permisos admin/cajero. 65 pruebas pasando.
- Falta: reportes del dueño (más vendidos, margen por producto, ventas por cajero), persistencia (SQLite) y datos de ejemplo de Santa Cruz.

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

## Lista de proyectos

| # | Proyecto | Estado |
|---|----------|--------|
| 1 | farmacia-pos-api | En curso |
| 2 | boutique-inventario | Pendiente |
| 3 | licoreria-pos | Pendiente |
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

Ninguno todavía.
