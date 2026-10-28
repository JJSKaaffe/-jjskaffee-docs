# Documentación de diseño · JJSKaffee

Entrega final de la documentación de diseño. El modelo de dominio y los diagramas de componentes, paquetes, secuencia y despliegue están hechos en draw.io (archivos `.drawio` en [`img/`](img/), con su imagen `.drawio.svg` editable); los demás diagramas están en Mermaid. GitHub muestra todos al abrir cada archivo.

| Documento | Contenido |
|---|---|
| [Diseño de alto nivel](01-diseno-alto-nivel.md) | Drivers de calidad, estilo de arquitectura, C4 nivel 1 (contexto, con API Gateway y vault de secretos) y C4 nivel 2 (contenedores) con la trazabilidad de registrar ingreso |
| [Modelo de dominio](06-modelo-de-dominio.md) | Entidades con su `id` y multiplicidades (draw.io), clases del dominio por módulo, reglas de negocio y su paso a tablas |
| **Diseño detallado** | |
| [Diagrama de componentes](02-diagrama-componentes.md) | Componentes del backend con la notación del profesor: el jar propio, Spring Boot 4.1.1, las librerías externas y la plataforma, con sus dependencias `«use»` (draw.io) |
| [Diagrama de paquetes](03-diagrama-paquetes.md) | Paquetes anidados al estilo del profesor: backend (`co.edu.uco.jjskafee`, todos los paquetes del código) y frontend (Vue 3) en draw.io; API Gateway y reglas de dependencia |
| [Diagrama de secuencia](04-diagrama-secuencia.md) | Registrar ingreso: de la aplicación web al API Gateway, el backend por capas y PostgreSQL, con fragmentos `ref`, `alt` y `loop` (draw.io) |
| [Diagrama de despliegue](05-diagrama-despliegue.md) | Contenedores del C4 nivel 2 sobre los nodos de Google Cloud y Firebase (draw.io), y los ambientes local, CI y producción |

## Alcance

El sistema completo aparece en los niveles 1 y 2. Desde el nivel 3, el detalle es de la funcionalidad a mi cargo, **registrar ingreso**: login → elegir cafetería → rol → registrar venta o ingreso libre → verlo en los movimientos.

## Qué está implementado y qué está diseñado

| Parte | Estado |
|---|---|
| Backend: módulos `acceso`, `ingresos`, `movimientos`, `egresos` | Implementado y probado (unitarias, ArchUnit e integración contra PostgreSQL en el CI) |
| Base de datos con Row Level Security | Implementada (`db/01` a `db/10`) |
| Firebase Authentication | En uso, probado con un usuario real en Postman |
| API Gateway, Cloud Run, Cloud SQL y Secret Manager | Diseñados (ADR-0013, ADR-0014, ADR-0017); se montan en la Fase 6 |
| Aplicación web en Vue 3 | Estructura base hecha (TypeScript, rutas por permiso, cliente HTTP, stores y api de los cuatro módulos); pantallas por construir |
| Inventario, nómina, reportes, alertas e IA | Planeados como módulos nuevos del monolito |

## Decisiones relacionadas

Los ADR están en [`adr/`](../adr/), con un resumen de todos en [`adr/README.md`](../adr/README.md).
