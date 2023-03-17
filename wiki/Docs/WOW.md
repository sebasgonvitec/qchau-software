# WOW: QChau Software

Versión 1.0

Por

Ana Paula Katsuda

Sebastián González

Gerardo Gutiérrez

Francisco Salcedo

Luis Javier Karam

Al 16 de Marzo del 2023

## Índice

[**Índice 1**](#_79k8zadbhael)

[**Introducción 1**](#_spbd314if8q3)

[**Alcance del Proyecto 1**](#_cpcfx2adyit8)

[Contexto 1](#_8ucw1lrowa1u)

[Perspectiva del Producto 2](#_uap260nsk03w)

[Alcance 2](#_iuu11pd2o9g)

[**Proceso de Desarrollo 3**](#_om7urq8gqr89)

[Metodología 3](#_j3c0qs7q9vir)

[Distribución de Trabajo 3](#_a2s1yvuo25u5)

[**Roles y Responsabilidades 3**](#_rif8tohn3nrv)

[**Estándares 4**](#_i5vvzm22esfm)

[**Estándar de Comunicación 4**](#_ghrwmhdfka9k)

[Notación para estimación en Kanban 4](#_x7yt5okv85ic)

[**Referencias 4**](#_ic08cu19mvkq)

## Introducción

El presente documento WOW (Way of Working) tiene como objetivo definir los lineamientos con los que se trabajará en QChau Software durante el desarrollo de la aplicación web de adquisición de autos. Dichos lineamientos tienen el propósito de controlar y mejorar la interacción, la colaboración y el trabajo de todos los miembros del equipo.

## Alcance del Proyecto

La presente sección explica y detalla con mayor claridad el proyecto que se realizará y su actual alcance.

## Contexto

NDS Cognitive Labs es una empresa dedicada a la implementación de soluciones digitales en México. De manera específica, la empresa trabaja en temas tales como Inteligencia Artificial, Internet de las Cosas, la nube y analítica. Actualmente, NDS busca una plataforma capaz de facilitar la adquisición digital de autos.

Considerando las necesidades planteadas por NDS Cognitive Labs, la presente empresa - QChau Software - realizará un planteamiento de solución digital en este documento de Especificación de Requerimientos de Software (SRS).

La introducción en este caso, tiene el objetivo de proveer una descripción general del documento, en donde se incluye el propósito, las convenciones del documento, el alcance del proyecto y las respectivas referencias. Con lo anterior, se logrará tener una mejor comprensión de la propuesta del proyecto y del análisis de necesidades para NDS Cognitive Labs en el que se desarrollará el sistema de compra de autos mencionado anteriormente.

## Perspectiva del Producto

La necesidad del producto nace del proceso inconveniente que sufren muchos clientes en la adquisición de un auto. En muchos casos, los clientes tienen que asistir múltiples veces a las agencias para resolver temas que podrían ser solucionados de manera remota. De esta manera, la solución le ahorrará tiempo y recursos al cliente y generará la posibilidad de realizar más ventas por parte de los grupos automotrices.

El producto propuesto, es nuevo (es decir, no es la extensión ni desarrollo de un proyecto ya iniciado), compartiendo características con páginas tales como la de Kavak o la de Tesla. Se planea tener una aplicación transparente e interactiva con los usuarios de manera que reciban la misma experiencia o una mejor que en las agencias. Más adelante, se describirán las funcionalidades del sistema y la manera en la que otorgarán un valor agregado a la aplicación.

## Alcance

La aplicación planteada involucra un sistema de adquisición de autos de manera mayormente digital. El sistema será diseñado de manera que un usuario comprador pueda revisar catálogos de las marcas registradas (distintos grupos automotrices y agencias), solicitar pruebas de manejo, comparar autos, obtener estimaciones de precios (cotización), comenzar su proceso de compra desde la plataforma, subir la documentación necesaria, obtener retroalimentación de su documentación, comunicarse con agentes, y mantener un seguimiento de su compra.
 Asimismo, permitirá a grupos automotrices inscribirse y registrar sus agencias con sus respectivos gerentes y vendedores. De esta manera, los vendedores podrán dar seguimiento a las compras de sus clientes y los gerentes podrán tener un seguimiento administrativo (tal como la gestión de catálogos de autos) desde una plataforma intuitiva.

La aplicación será de gran utilidad no solo para los compradores que quieran realizar sus compras digitalmente de una manera fácil y segura, sino también para las agencias y grupos automotrices que quieran aumentar el alcance de sus ventas utilizando herramientas tecnológicas. Todos los autos registrados en la plataforma estarán al alcance del usuario y se tendrá una atención con la misma calidad que la que se ofrece en una agencia.

En cuanto a las limitaciones de la aplicación, es relevante mencionar que ésta es principalmente un medio de contacto digital y publicación de productos únicamente de agencias, por lo que no se gestionan procesos internos de cada agencia y grupo automotriz. Ahondando en lo anterior, las entidades involucradas en el desarrollo de la plataforma no tienen responsabilidades en cuanto a los acuerdos de pagos de mensualidades, las negociaciones realizadas por la agencia, la entrega ni el mantenimiento de los vehículos.

## Proceso de Desarrollo

## Metodología

En cuanto al proceso de desarrollo se plantea utilizar una metodología mayormente ágil. Se trabajará con distintos Sprints en los que se desarrollarán las distintas historias de usuario pertenecientes a los EPICS que se definieron. Asimismo, se trabajará con un Kanban para que los miembros del equipo tengan claridad respecto a sus tareas y les puedan dar un seguimiento pertinente. Si bien se trata de una metodología ágil, es posible que existan momentos en los que se tenga que trabajar con metodologías tales como cascada.

Cabe destacar que, al ser una metodología ágil, se tienen daily standups (en donde cada miembro del equipo menciona sus actividades del día, lo que hará y los bloqueos que tiene), sprint planning (en donde se revisará el siguiente sprint a realizar considerando su relevancia y otros puntos) y sprint review (en donde se revisa lo que se hizo en el sprint y se notan aspectos a mejorar en próximos sprints).

## Distribución de Trabajo

El trabajo se distribuirá en tres principales etapas y cada miembro del equipo trabajará una carga distinta de días en las actividades como se muestra a continuación:

## ![](RackMultipart20230317-1-93f9ez_html_1dc95c284a0a2c37.png)

Debido a la naturaleza del proyecto, todos los miembros del equipo tomarán distintos roles a lo largo del desarrollo y la planeación. Con lo mostrado en la imagen, es posible notar la distribución de horas que tendrá cada integrante, cumpliendo con roles distintos respecto a las actividades.

## Estándares

En la presente sección se describirán los estándares que serán seguidos por el equipo.

## Estándar de Comunicación

En cuanto al plan de comunicación, se plantea el uso de GitHub para subir resultados de pruebas unitarias y mantener un seguimiento de lo que se ha realizado. GitHub es una herramienta de versiones por lo que todos los integrantes del equipo y aquellos involucrados en las pruebas, tendrán la posibilidad de visualizar cualquier cambio o avance que se realice. Adicional a Github, se utilizará Github Actions con el fin de lograr la automatización de notificaciones de manera que todos los miembros del equipo puedan recibir las actualizaciones en el momento en el que se realizan.

## Notación para estimación en Kanban

Fibonacci (emojis)

| 0 | 1 | 2 | 3 | 5 | 8 | 13 | 21 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 🤣 | 🥳 | 😎 | 🤔 | 🙃 | 😰 | 🤬 | 😭 |

## Referencias

Para la realización del presente documento, se tomó la información definida tanto en el Documento SRS, como en el Documento de Pruebas y la Presentación del Departamento.
