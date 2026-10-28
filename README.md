# JJSKaffee · Documentación

Documentación del sistema **JJSKaffee**: una aplicación web SaaS para que cafeterías pequeñas e independientes de Colombia controlen sus ingresos y egresos, con reportes, comparación entre períodos y alertas. Proyecto de Ingeniería de Software II (UCO).

| Repositorio | Contenido |
|---|---|
| **jjskaffee-docs** (este) | Documentación: diseño, decisiones de arquitectura, negocio, requisitos y calidad |
| [jjskaffee-backend](https://github.com/JJSKaaffe/jjskaffee-backend) | API REST en Java 27 y Spring Boot 4.1: monolito modular con módulos hexagonales |
| [jjskaffee-frontend](https://github.com/JJSKaaffe/jjskaffee-frontend) | Aplicación web en Vue 3 |

## Entrega final: diseño

La entrega final está en [`diseno/`](diseno/README.md). Se enfoca en la funcionalidad **registrar ingreso**.

| Documento | Contenido |
|---|---|
| [Diseño de alto nivel](diseno/01-diseno-alto-nivel.md) | Drivers de calidad, estilo de arquitectura, C4 nivel 1 (con API Gateway y vault de secretos) y C4 nivel 2 con la trazabilidad de registrar ingreso |
| [Modelo de dominio](diseno/06-modelo-de-dominio.md) | Entidades con su `id` y multiplicidades, clases del dominio y reglas de negocio |
| **Diseño detallado** | |
| [Diagrama de componentes](diseno/02-diagrama-componentes.md) | Componentes del backend: el jar propio, Spring Boot, librerías externas y plataforma, con sus dependencias `«use»` |
| [Diagrama de paquetes](diseno/03-diagrama-paquetes.md) | Paquetes del backend y del frontend con sus dependencias `«import»` |
| [Diagrama de secuencia](diseno/04-diagrama-secuencia.md) | Registrar ingreso, de la aplicación web a PostgreSQL |
| [Diagrama de despliegue](diseno/05-diagrama-despliegue.md) | Contenedores del C4 nivel 2 sobre Google Cloud y Firebase |

## Resto de la documentación

| Carpeta | Contenido |
|---|---|
| [`adr/`](adr/README.md) | Decisiones de arquitectura ADR-0001 a ADR-0017, con un resumen de todas |
| [`spikes/`](spikes/) | Pruebas técnicas SPIKE-01 a SPIKE-06 que respaldan las decisiones |
| [`arquitectura/`](arquitectura/) | [Drivers de arquitectura](arquitectura/drivers.md) y la [arquitectura del backend](arquitectura/backend-hexagonal.md): módulos, capas, endpoints y reglas de negocio |
| [`negocio/`](negocio/) | [Negocio, alcance y decisiones vigentes](negocio/negocio-y-alcance.md), y [visión y mapa de impacto](negocio/vision-y-mapa-de-impacto.md) |
| [`requisitos/`](requisitos/) | [Requisitos funcionales](requisitos/requisitos-funcionales.md) e [historias de usuario y funcionalidades significativas](requisitos/historias-y-funcionalidades-significativas.md) |
| [`calidad/`](calidad/) | [Atributos y escenarios de calidad](calidad/atributos-y-escenarios.md), [priorización](calidad/priorizacion-y-escenarios-qa.md), [dot voting](calidad/dot-voting.md), [matriz de tiempos](calidad/matriz-de-tiempos.md) y mapa de empatía |
| [`restricciones/`](restricciones/) | [Restricciones de negocio](restricciones/restricciones-de-negocio.md) y [técnicas](restricciones/restricciones-tecnicas.md) |

La colección de Postman para probar registrar ingreso está en el [repositorio del backend](https://github.com/JJSKaaffe/jjskaffee-backend/blob/main/docs/postman/jjskaffee-registrar-ingreso.postman_collection.json).

## Cómo ver y editar los diagramas

- GitHub muestra todos los diagramas al abrir cada archivo. Unos están escritos en Mermaid dentro del Markdown y otros son imágenes `.drawio.svg`.
- Los diagramas de draw.io están en [`diseno/img/`](diseno/img/). Cada uno tiene su archivo `.drawio`, que se abre y se edita en [app.diagrams.net](https://app.diagrams.net). La imagen `.drawio.svg` también se puede abrir ahí y lleva el diagrama editable adentro.
