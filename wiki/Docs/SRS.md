# **Especificación de Requerimientos de Software para NDS Cognitive Labs**
Versión 1.0

_Preparado por:_
- Ana Paula Katsuda Zalce
- Sebastián González Villacorta
- Gerardo Gutiérrez Paniagua
- Luis Javier Karam
- Francisco Salcedo Catalán

### ITESM
### 9 de Marzo del 2023

---
## _Tabla de Contenidos_
1. [Introducción](#introducción)
    1. [Propósito](#propósito)
    2. [Convenciones del Documento](#convenciones-del-documento)
    3. [Alcance del Proyecto](#alcance-del-proyecto)
    4. [Objetivos de QChau Software](#objetivos-de-qchau-software)
    5. [Referencias](#referencias)
2. [Descripción General](#descripción-general)
    1. [Perspectiva de Producto](#perspectiva-del-producto)
    2. [Clases de Usuario y Características](#clases-de-usuario-y-características)
    3. [Ambiente de Operación](#ambiente-de-operación)
        - [Interaccionescon la Aplicación](#interacciones-con-la-aplicación)
        - [Arquitectura](#arquitectura)
        - [Tech Stack](#tech-stack)
    4. [Asunciones y Dependencias](#asunciones-y-dependencias)

---
## _Historial de Versiones_
| Nombre       | Fecha     | Razones de cambios | Version |
|--------------|-----------|------------|------|
| Ana Paula Katsuda Zalce | 6 de Marzo del 2023 | Comienzo de redacción de las secciones introducción y descripción general | v1.0 |
|  |  |  |  |

---
## _Introducción_
NDS Cognitive Labs es una empresa dedicada a la implementación de soluciones digitales en México. De manera específica, la empresa trabaja en temas tales como Inteligencia Artificial, Internet de las Cosas, la nube y analítica. Actualmente, NDS busca una plataforma capaz de facilitar la adquisición digital de autos.

Considerando las necesidades planteadas por NDS Cognitive Labs, la presente empresa - QChau Software - realizará un planteamiento de solución digital en este documento de Especificación de Requerimientos de Software (SRS). 

La introducción en este caso, tiene el objetivo de proveer una descripción general del documento, en donde se incluye el propósito, las convenciones del documento, el alcance del proyecto y las respectivas referencias. Con lo anterior, se logrará tener una mejor comprensión de la propuesta del proyecto y del análisis de necesidades para NDS Cognitive Labs en el que se desarrollará el sistema de compra de autos mencionado anteriormente. 

### _Propósito_
El propósito de este documento es detallar, analizar y definir el sistema de adquisición de autos (en su primera versión) que será propuesto a NDS Cognitive Labs de una manera clara y comprensible. En este caso, se describirán los requerimientos funcionales, los requerimientos no funcionales, las limitaciones del sistema y la interacción del sistema y el usuario. 

El documento será de gran utilidad para los Project Owners, Project Managers, desarrolladores y cualquier entidad que participe en la creación de la aplicación puesto a que se puede utilizar como un punto de partida para la misma.

### _Convenciones del Documento_
| Término | Definición |
|---------|------------|
|Especificación de Requerimientos de Software (SRS)| Un documento en el que se detallan las funcionalidades de un software.|
| PO | Product Owner |
| PM | Project Manager |

### _Alcance del Proyecto_
La aplicación planteada involucra un sistema de adquisición de autos de manera mayormente digital. El sistema será diseñado de manera que un usuario comprador pueda revisar catálogos de las marcas registradas (distintos grupos automotrices y agencias), solicitar pruebas de manejo, comparar autos, obtener estimaciones de precios (cotización), comenzar su proceso de compra desde la plataforma, subir la documentación necesaria, obtener retroalimentación de su documentación, comunicarse con agentes, y mantener un seguimiento de su compra.  
Asimismo, permitirá a grupos automotrices inscribirse y registrar sus agencias con sus respectivos gerentes y vendedores. De esta manera, los vendedores podrán dar seguimiento a las compras de sus clientes y los gerentes podrán tener un seguimiento administrativo (tal como la gestión de catálogos de autos) desde una plataforma intuitiva. 

La aplicación será de gran utilidad no solo para los compradores que quieran realizar sus compras digitalmente de una manera fácil y segura, sino también para las agencias y grupos automotrices que quieran aumentar el alcance de sus ventas utilizando herramientas tecnológicas. Todos los autos registrados en la plataforma estarán al alcance del usuario y se tendrá una atención con la misma calidad que la que se ofrece en una agencia. 

En cuanto a las limitaciones de la aplicación, es relevante mencionar que ésta es principalmente un medio de contacto digital y publicación de productos únicamente de agencias, por lo que no se gestionan procesos internos de cada agencia y grupo automotriz. Ahondando en lo anterior, las entidades involucradas en el desarrollo de la plataforma no tienen responsabilidades en cuanto a los acuerdos de pagos de mensualidades, las negociaciones realizadas por la agencia, la entrega ni el mantenimiento de los vehículos. 
### _Objetivos de QChau Software_

- Asegurar la integridad y accesibilidad de los sistemas informáticos involucrados.
- Diseñar el sistema de tal manera que la integración a través del mercado automovilístico sea fácil e intuitiva. 
- Desplegar los listados e información de una manera agradable, útil y eficiente para el usuario. 

### _Referencias_

---
## _Descripción General_
En la presente sección se incluyen las especificaciones generales del producto final, en donde se describirán detalles tales como los tipos de usuarios definidos para el proyecto, el ambiente del software, limitaciones, asumpciones, y dependencias. Lo anterior con la finalidad de obtener una mejor idea de las características y las consideraciones que se tienen que tomar para un correcto desarrollo. 

### _Perspectiva del Producto_
La necesidad del producto nace del proceso inconveniente para muchos clientes en la adquisición de un auto. En muchos casos, los clientes tienen que asistir múltiples veces a las agencias para resolver temas que podrían ser solucionados de manera remota, ahorrando tiempo y recursos al cliente y generando la posibilidad de realizar más ventas por parte de las agencias. 

El producto propuesto, es completamente nuevo, compartiendo características con páginas tales como Kavak o Tesla. Se planea tener una aplicación completamente transparente e interactiva con los usuarios de manera que reciban la misma experiencia o una mejor que en las agencias. Más adelante, se describirán las funcionalidades del sistema y la manera en la que otorgarán un valor agregado a la aplicación.

### _Clases de Usuario y Características_
En cuanto a los usuarios que utilizarían el sistema, se identificaron cinco principales como se describe a continuación.
- *Usuario Final*: este es el usuario que quiere comprar un auto, cotizar, solicitar una prueba de manejo, comunicarse con su agente, o revisar su proceso de compra. Es el usuario que se beneficia de llevar al proceso de manera digital, por lo que se busca que su interacción con la aplicación sea sencilla e intuitiva. 
- *Usuario Vendedor*: este es el usuario que tiene contacto directo con el usuario final, que lleva el proceso de compra de los usuarios, y que le da la atención necesaria a los mismos. Como en una agencia tradicional, la labor de este usuario es brindar confianza y comodidad a los compradores a lo largo de sus adquisiciones. 
- *Usuario Gerente*: este es el usuario que supervisa la evolución de las compras y a los vendedores mientras administra temas relacionados con la agencia (tales como el catálogo que se maneja). Su principal labor dentro de la aplicación, es mantener actualizado su catálogo, visualizar y administrar a sus agentes y planes de financiamiento. 
- *Usuario Grupo Automotriz*: este es el usuario que se inscribe en la plataforma para permitir que sus agencias participen en la misma. Su principal labor es mantener la documentación de sus agencias y tendrá la capacidad de revisar algunas estadísticas referentes a las mismas.
- *Usuario Administrador de la Plataforma*: este usuario es el encargado de revisar todos los temas administrativos de la plataforma. Lo previo incluye verificar el alta de los distintos grupos automotrices con sus agencias, gestionar datos y visualizar información relevante del sistema. 

### _Ambiente de Operación_
La presente sección contiene los aspectos técnicos que se requieren para la operación de la aplicación. Es relevante mencionar que se trata de una aplicación web que será albergada en la nube y será útil para la venta de coches en la República Mexicana.  

#### **Interacciones con la Aplicación**
En cuanto a las interacciones con la aplicación, también consideradas ambiente de sistema, se plasman los actores principales (usuarios) mencionados anteriormente   la manera en la que tendrán acceso a las distintas funcionalidades de la plataforma.

![Ambiente Del Sistema](Media/SRSmedia/AmbienteDelSistema.png)

Figura 1. Ambiente del Sistema

En la figura del ambiente del sistema, es posible observar que la administración del sistema (controlada por el usuario administrador de la plataforma) tiene acceso a todas las áreas del sistema. Por otro lado, se tiene la interfaz de ventas en donde el usuario vendedor puede tener un manejo de sus funciones de venta y su interacción con el usuario final en el área comercial. Finalmente, la administración de negocio (que gestiona el usuario grupo automotriz) involucra la revisión de estadísticas y la gestión de administración de ventas (utilizada por el usuario gerente).

#### **Arquitectura**
En cuanto a la arquitectura del sistema, se plantea una solución en la nube y se considera el uso de una estructura de microservicios.

![Arquitectura en la Nube](Media/SRSmedia/ArquitecturaNube.png)
Figura 2. Propuesta de Arquitectura en la Nube

Es posible notar en el diagrama, el uso de distintas tecnologías en la nube. En primer lugar, se tienen los servidores web que servirán para correr la aplicación junto con el servidor de aplicación (lógica) de manera que pueda ser posible escalar tanto horizontal (agregando más servidores) como verticalmente (agregando recursos a los servidores). 

Asimismo, se agregaron bases de datos tanto relacionales como no relacionales considerando que parte de los datos puede ser altamente flexible (por lo tanto escalabes) mientras otros datos son más fijos y se relacionan altamente entre ellos. Se plantea adicionalmente, un servicio que contenga copias de seguridad de los datos para protegerlos en caso de que algo suceda a las bases de datos.

En cuanto a el análisis de datos, se planea tener seguimiento de funciones que responden a eventos (colección y warehouse) acompañados de un servicio de inteligencia de negocios para el análisis. 

Considerando los servicios de mensajería se plantea agregar al servidor de la aplicación servicios tanto de correo electrónico como de chat. 

Haciendo referencia a la salida al público, se planea tener un balanceador de carga con el fin de distribuir el tráfico a los servidores. De igual manera, se planea utilizar un servicio de firewall para monitorear el tráfico de la red y un servicio de autenticación de usuarios para la administración de identidad de los usuarios. Se quiere utilizar el servicio de CDN para, junto con un cache, alojar ahí los medios que se utilizarán en la plataforma. Finalmente, se tiene un proveedor de DNS para resolver los dominios de los sitios web a usar. 

Regresando a la idea de utilizar microservicios, se consideran los mismos dadas las múltiples funcionalidades y la complejidad del sistema requerido. El uso de microservicios contribuirá a la eficiencia de desarrollo puesto a que facilita que muchas personas trabajen en distintos módulos al mismo tiempo, en la diversidad de tecnologías permitiendo utilizar las mejores dependiendo de la funcionalidad y haciendo que tanto la escalabilidad, el mantenimiento y las pruebas sean más simples dado lo seccionado que se vuelve. 

#### **Tech Stack**

### _Asunciones y Dependencias_
En el caso de las asumpciones que se consideran para la creación del presente documento son las siguientes: 
- Las agencias y grupos automotrices tienen la apertura de transformar digitalmente sus negocios. 
- 