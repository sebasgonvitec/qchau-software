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
    4. [Referencias](#referencias)
2. [Descripción General](#descripción-general)
    1. [Perspectiva de Producto](#perspectiva-del-producto)
    2. [Clases de Usuario y Características](#clases-de-usuario-y-características)
    3. [Ambiente de Operación](#ambiente-de-operación)
        - [Interacciones con la Aplicación](#interacciones-con-la-aplicación)
        - [Arquitectura](#arquitectura)
        - [Tech Stack](#tech-stack)
    4. [Restricciones de Diseño e Implementación](#restricciones-de-diseño-e-implementación)
    5. [Supuestos y Dependencias](#supuestos-y-dependencias)
3. [Características del Sistema](#características-del-sistema)
    1. [Historias de Usuario](#historias-de-usuario)
    2. [Requerimientos Funcionales](#requerimientos-funcionales)
    3. [Requerimientos No Funcionales](#requerimientos-no-funcionales)
4. [Requerimientos de Datos](#requerimientos-de-datos)
    1. [Estructura Lógica de los Datos](#estructura-lógica-de-los-datos)
    2. [Diccionarios de Datos](#diccionarios-de-datos)
    3. [Características de la Base de Datos](#características-de-la-base-de-datos)
    4. [Reportes](#reportes)
    5. [Adquisición, Integridad, Retención, y Disposición de los Datos](#adquisición-integridad-retención-y-disposición)
5. [Requerimientos de la Interfaz Externa](#requerimientos-de-la-interfaz-externa)
    1. [Elementos Relevantes del Diseño de la Interfaz de Usuario](#elementos-relevantes-del-diseño-de-la-interfaz-de-usuario)
    2. [Mapa de Navegación General](#mapa-de-navegación-general)
    3. [Interfaces de Software](#interfaces-de-software)
    4. [Interfaces de Hardware](#interfaces-de-hardware)
    5. [Interfaces de Comunicación](#interfaces-de-comunicación)
    6. [Diagramas de Casos de Uso](#diagramas-de-casos-de-uso)
    7. [Diagramas de Actividad](#diagramas-de-actividad)

6. [Atributos de Calidad](#atributos-de-calidad)
	1. [Usabilidad](#usabilidad)
	2. [Desempeño](#desempeño)
	3. [Seguridad](#seguridad) 
	4. [Protección](#protección)
7. [Requerimientos de Internacionalización y Localización](#requerimientos-de-internacionalización-y-localización)
8. [Otros Requerimientos](#otros-requerimientos)
9. [Apéndices](#apéndices)
    1. [Apéndice A: WBS](#apéndice-a-wbs)
    2. [Apéndice B: Diagrama de Gantt](#apéndice-b-diagrama-de-gantt)
    3. [Apéndice C: Tableros de Kanban](#apéndice-c-tableros-de-kanban)
    4. [Apéndice D: Análisis de Margen](#apéndice-d-análisis-de-margen)
    5. [Apéndice E: Análisis de Riesgos](#apéndice-e-análisis-de-riesgos)
    6. [Apéndice F: Documento de Historias de Usuario](#apéndice-f-documento-de-historias-de-usuario)

---
## _Historial de Versiones_
| Nombre       | Fecha     | Razones de cambios | Version |
|--------------|-----------|------------|------|
| Ana Paula Katsuda Zalce | 6 de Marzo del 2023 | Comienzo de redacción de las secciones introducción y descripción general | v1.1 |
| Sebastián González Villacorta | 8 de Marzo del 2023 | Comienzo de redacción de sección Requerimientos de Datos | v1.2 |
| Ana Paula Katsuda Zalce | 9 de Marzo del 2023 | Redacción de parte de la interfaz externa del usuario y agregación de características del sistema | v1.3 |
| Gerardo Gutiérrez Paniagua | 10 de Marzo del 2023 | Adicion de apéndices y corrección de referencias a los requerimientos en los atributos de calidad | v1.4 |

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
| SRS | Documento de Especificación de Requerimientos de Software en el que se describen las funcionalidades necesarias para un proyecto de desarrollo de software |
| Project Manager | Se entiende como la persona responsable de dar seguimiento y gestionar las actividades al desarrollar un proyecto |
| Product Owner | Se entiende como la persona que representa las necesidades del cliente de cara al equipo de desarrollo |

### _Alcance del Proyecto_
La aplicación planteada involucra un sistema de adquisición de autos de manera mayormente digital. El sistema será diseñado de manera que un usuario comprador pueda revisar catálogos de las marcas registradas (distintos grupos automotrices y agencias), solicitar pruebas de manejo, comparar autos, obtener estimaciones de precios (cotización), comenzar su proceso de compra desde la plataforma, subir la documentación necesaria, obtener retroalimentación de su documentación, comunicarse con agentes, y mantener un seguimiento de su compra.  
Asimismo, permitirá a grupos automotrices inscribirse y registrar sus agencias con sus respectivos gerentes y vendedores. De esta manera, los vendedores podrán dar seguimiento a las compras de sus clientes y los gerentes podrán tener un seguimiento administrativo (tal como la gestión de catálogos de autos) desde una plataforma intuitiva. 

La aplicación será de gran utilidad no solo para los compradores que quieran realizar sus compras digitalmente de una manera fácil y segura, sino también para las agencias y grupos automotrices que quieran aumentar el alcance de sus ventas utilizando herramientas tecnológicas. Todos los autos registrados en la plataforma estarán al alcance del usuario y se tendrá una atención con la misma calidad que la que se ofrece en una agencia. 

En cuanto a las limitaciones de la aplicación, es relevante mencionar que ésta es principalmente un medio de contacto digital y publicación de productos únicamente de agencias, por lo que no se gestionan procesos internos de cada agencia y grupo automotriz. Ahondando en lo anterior, las entidades involucradas en el desarrollo de la plataforma no tienen responsabilidades en cuanto a los acuerdos de pagos de mensualidades, las negociaciones realizadas por la agencia, la entrega ni el mantenimiento de los vehículos. 

### _Referencias_
https://www.youtube.com/watch?v=9kRgVxULbag

https://firebase.google.com/codelabs/firebase-android#0

https://www.freecodecamp.org/news/building-a-real-time-chat-app-with-reactjs-and-firebase/

https://blog.logrocket.com/how-to-build-chatroom-app-react-firebase/ 

https://nodejs.org/en/docs/

https://www.freecodecamp.org/learn/back-end-development-and-apis/

https://cloud.google.com/products#section-1

---
## _Descripción General_
En la presente sección se incluyen las especificaciones generales del producto final, en donde se describirán detalles tales como los tipos de usuarios definidos para el proyecto, el ambiente del software, limitaciones, asunciones, y dependencias. Lo anterior con la finalidad de obtener una mejor idea de las características y las consideraciones que se tienen que tomar para un correcto desarrollo. 

### _Perspectiva del Producto_
La necesidad del producto nace del proceso inconveniente que sufren muchos clientes en la adquisición de un auto. En muchos casos, los clientes tienen que asistir múltiples veces a las agencias para resolver temas que podrían ser solucionados de manera remota. De esta manera, la solución le ahorrará tiempo y recursos al cliente y generará la posibilidad de realizar más ventas por parte de los grupos automotrices. 

El producto propuesto, es nuevo (es decir, no es la extensión ni desarrollo de un proyecto ya iniciado), compartiendo características con páginas tales como la de Kavak o la de Tesla. Se planea tener una aplicación transparente e interactiva con los usuarios de manera que reciban la misma experiencia o una mejor que en las agencias. Más adelante, se describirán las funcionalidades del sistema y la manera en la que otorgarán un valor agregado a la aplicación.

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

---

#### **Arquitectura**
En cuanto a la arquitectura del sistema, se plantea una solución en la nube y se considera el uso de una estructura de microservicios.

![Arquitectura en la Nube](Media/SRSmedia/ArquitecturaNube.png)
Figura 2. Propuesta de Arquitectura en la Nube

Es posible notar en el diagrama, el uso de distintas tecnologías en la nube. En primer lugar, se tienen los servidores web que servirán para correr la aplicación junto con el servidor de aplicación (lógica) de manera que pueda ser posible escalar tanto horizontal (agregando más servidores) como verticalmente (agregando recursos a los servidores). 

Asimismo, se agregaron bases de datos tanto relacionales como no relacionales considerando que parte de los datos puede ser altamente flexible (por lo tanto escalabes) mientras otros datos son más fijos y se relacionan altamente entre ellos. Se plantea adicionalmente, un servicio que contenga copias de seguridad de los datos para protegerlos en caso de que algo suceda a las bases de datos.

En cuanto a el análisis de datos, se planea tener seguimiento de funciones que responden a eventos (colección y warehouse) acompañados de un servicio de inteligencia de negocios para el análisis. 

Considerando los servicios de mensajería se plantea agregar al servidor de la aplicación servicios tanto de correo electrónico como de chat. 

Haciendo referencia a la salida al público, se planea tener un balanceador de carga con el fin de distribuir el tráfico a los servidores. De igual manera, se planea utilizar un servicio de firewall para monitorear el tráfico de la red y un servicio de autenticación de usuarios para la administración de identidad de los usuarios. Se quiere utilizar el servicio de CDN para, junto con un cache, alojar ahí los medios que se utilizarán en la plataforma. Finalmente, se tiene un proveedor de DNS para resolver los dominios de los sitios web a usar. 

Asimismo se plantea el uso de una arquitectura enfocada en servicios (muy similar a microservicios pero con servicios compartiendo las bases de datos), se considera esto dadas las múltiples funcionalidades y la complejidad del sistema requerido. El uso de la aruitectura orientada a servicios contribuirá a la eficiencia de desarrollo puesto a que facilita que muchas personas trabajen en distintos módulos al mismo tiempo, en la diversidad de tecnologías permitiendo utilizar las mejores dependiendo de la funcionalidad y haciendo que tanto la escalabilidad, el mantenimiento y las pruebas sean más simples dado lo seccionado que se vuelve. 

---

#### **Tech Stack**
En la presente sección se definen las tecnologías que serán utilizadas para el desarrollo y operación del servicio propuesto. A su vez, cada tecnología definida muestra sus principales beneficios para el servicio propuesto por razones de soporte, operatividad y diseño.


1. **Componentes de Desarrollo Frontal**

_Interfaz de Usuario_

HTML5, CSS3, ECMAScript 2021

Estos son los lenguajes y estándares a utilizar - son virtualmente el método universal de desarrollo en un ambiente web. HTML5 y CSS3 son las versiones más extendidas a través de los navegadores en actual uso. ECMAScript 2021 es el último versionamiento del estándar para JavaScript - extendido en múltiples navegadores modernos.

_Estructuras de Front-End_

**React**

React es una librería de JavaScript enfocada en el desarrollo frontal de aplicaciones Web. Está enfocada meramente en el desarrollo frontal, lo que la habilita en perder enfoque a otras partes del desarrollo y maximizar su potencial de uso para el mismo.

A pesar de ser una librería de código abierto, es mantenida por Meta (anteriormente Facebook) - una empresa líder en servicios de redes sociales en Internet. Meta, utiliza esta librería para el desarrollo frontal de sus aplicaciones como Facebook e Instagram: servicios que son reconocidos por promover una UX/UI intuitiva, fácil de utilizar y escalable.

El poder apalancarse del soporte y métodos de las redes sociales mas utilizadas en Internet - permite al equipo poder solventar la dirección de UX/UI del servicio - haciendo al servicio uno más familiar para el usuario.

_Estilo_

**React-Bootstrap**

Bootstrap es una librería de HTML/CSS enfocada en el diseño del desarrollo frontal de aplicaciones Web. Siendo una librería de código abierto, es utilizada por alrededor del 15% de los sitios de Internet disponibles.

Su potencial está en la longevidad y soporte continuo en la comunidad de desarrollo - existen formatos y métodos probados por múltiples desarrolladores: quitándole al equipo el tiempo y esfuerzo necesario para planear la implementación de diseño y dar más tiempo al diseño mismo (que termina siendo una característica crítica en el servicio).

2. **Componentes de Desarrollo Servidor**

_Lenguajes de Programación y Ambientes de Ejecución_

**Node.JS**

NodeJS es un ambiente de ejecución de JavaScript multiplataforma que opera código fuera del navegador utilizado.

NodeJS se ha convertido en un estándar global para el desarrollo de aplicaciones tanto de escritorio como aplicaciones web. Operado y mantenido por OpenJS Foundation, el ambiente se apalanca del liderazgo de sus empresas fundadoras para su soporte.

Corre sobre el motor V8 del proyecto Chromium - base de dos de los navegadores más populares en el mundo: Chrome y Edge.

Su potencial está en el diseño del ambiente que permite una eficiente E/S asíncrona - permitiendo que el servicio pueda soportar múltiples peticiones de múltiples usuarios sin afectar el rendimiento y experiencia del usuario de los demás. La escalabilidad es un patrón en los servicios que corren en NodeJS.

_Estructuras de Aplicación Web_

**Express**

Express es una estructura de código abierto para desarrollar aplicaciones Web y APIs RESTful para comunicación con el servidor.

Express es extremadamente popular con servicios web de gran escala - como PayPal y Uber: comprobando su utilidad para aplicaciones de servicio, contacto y proveo por Internet.

La estructura es de código abierto y es mantenida regularmente por StrongLoop - una empresa de desarrollo respaldada por IBM; además, la última versión estable fue publicada hace 10 meses. Por esto, se comprueba su sustentabilidad de soporte y mantenimiento: minimizando así el riesgo de migración e incompatibilidad.

Express es reconocido por su concentración en proveer alto rendimiento: considerando que el proyecto abarcaría toda la República Méxicana - un país con un porcentaje de penetración de 71% - es probable que el servicio requiera mantener la integralidad y accesibilidad a pesar del flujo de usuarios.

_Base de Datos_

**MongoDB**

MongoDB es una base de datos de Software Libre de tipo no relacional. Es una de las bases de datos más populares para el desarrollo de aplicaciones y otros productos.

MongoDB permite tener una base de datos flexible y fácil de adaptar a los requerimientos del usuario. Otro de los beneficios de esta base de datos es que existen muchos módulos y librerías para integrar esta base de datos con otras tecnologías de desarrollo de aplicaciones.

Durante el desarrollo de este proyecto se utilizará MongoDB para el almacenamiento y acceso de datos que estén en constante actualización, como es el historial del usuario, las publicaciones guardadas del usuario, entre otras.

**MySQL**

MySQL es uno de los muchos sabores de bases de datos relacionales y el más popular de código abierto del mercado

Esta base de datos permite tener los datos almacenados en tablas y con relaciones entre sí, de manera que el acceso a la información se hace mucho más fácil y eficiente.

Una de las ventajas de MySQL es que los diferentes proveedores de nube permiten su fácil implementación con las herramientas y servicios que ofrece cada uno.

Se usará MySQL en este proyecto para almacenar los datos que no necesiten constante actualización y que convenga, por su naturaleza, ser guardados con las relaciones necesarias para facilitar el acceso.

3. **Componentes de Infraestructura**

_Virtualización_

**Docker**

Docker es una herramienta de contenerización de aplicaciones de código abierto utilizada para el desarrollo y despliegue de aplicaciones web.

Los contenedores ofrecen la ventaja de tener un ambiente de despliegue ajustado a las medidas de cada aplicación y de igual manera poder generar una imagen de esa configuración para facilitar el despliegue de varias instancias idénticas de la aplicación.

Durante el proyecto se utilizará Docker como una opción de despliegue de los servicios que compongan el backend de la aplicación.

**Kubernetes**

Como se mencionó anteriormente, Docker se utiliza para generar empaquetar instancias de la aplicación en contenedores. Kubernetes trabaja de igual manera en la gestión de las instancias de estos contenedores.

Es una herramienta de orquestación de despliegue y uso de contenedores que permite escalar, administrar e implementar múltiples contenedores.

Se utilizará como opción de despliegue junto con Docker para asegurar la escalabilidad de la aplicación.

_Servicio de Nube_

**Google Cloud Platform**

Google Cloud Platform o GCP es una suite de infraestructura de cómputo en la nube ofrecida y soportada por Google.

Esta plataforma es utilizada de manera extensa en servicios de Internet - incluyendo el mismo Google: quien es virtualmente el servicio de Internet mas utilizado a nivel mundial.

La capacidad de cómputo proveída por la empresa líder en servicios de Internet es suficiente validación y comprobación de la utilidad apreciable para el servicio a desarrollar. Además, poder apalancarse de los servicios de Google - que están presentes en la gran mayoría de sitios (Google, Gmail, Youtube, etc..) facilita la habilidad del servicio de crecer.

La curva de aprendizaje en el equipo es más reducida. 40% del equipo está familiarizado con GCP, a comparación de un 20% familiarizado con AWS y un 0% familiarizado con Azure - servicios de cómputo en la nube alternativos.

_Servicios de Infraestructura_

_Computación_

**Compute Engine**

Compute Engine es el servicio de cómputo y hosting en la nube de GCP. Este servicio ofrece máquinas virtuales para ejecutar la aplicación en diferentes instancias o regiones para su acceso por los clientes.

Es inherente a la implementación en la nube, pues sugiere que toda la aplicación corra en la misma.

Compute Engine ofrece múltiples ventajas frente a otras alternativas disponibles, como AWS Elastic Compute.

Las máquinas virtuales de Compute Engine ofrecen consistencia en rendimiento, haciéndolas sustentables para aplicaciones de alto rendimiento de Linux.

Compute Engine utiliza la red de fibra global privada de Google, propagando así la aplicación sobre una red exclusiva y rápida.

Compute Engine se financia frente al uso por minuto, es decir nunca se va a cobrar adicionales por cómputo no utilizado, o por cómputo imprevisto.

_Seguridad y Acceso_

**Cloud Identity**

Cloud Identity es la plataforma de IAM/EMM de GCP - ofrece soluciones de administración de identidades para los administradores del servicio. Múltiples características maximizan la seguridad y experiencia de todos los usuarios de la plataforma: MFA y SSO.

Además, permite a los usuarios del servicio inscribirse al sistema utilizando su cuenta de Google - el proveedor de correo electrónico más grande del mundo.

**Firewalls**

Firewalls es el servicio de Cortafuegos de GCP. El nivel _Essential_ del servicio prueba ser suficiente para el servicio - permitiendo mantener una granularidad sencilla de control de cortafuegos para el servicio: ya que no es necesario mantener una revisión singular y específica.

_Almacenamiento_

**Cloud Storage**

Cloud Storage es el servicio de almacenamiento en cubetas de GCP. Teniendo múltiples niveles de servicio - todas pueden ser apalancadas para diferentes etapas del negocio.

Cloud Storage tiene una estructura de archivos superior a otros proveedores, además de ofrecer recuperación de archivos rápida (esencial para mantener al cliente interesado en la plataforma). Del lado del desarrollo, la configuración de Cloud Storage es mucho más sencilla, y requiere menos aprendizaje que las alternativas como S3 de AWS.

Además Cloud Storage se incorpora fácilmente con el servicio de almacenamiento en nube comercial de Google - Drive: que es utilizado por múltiples empresas y corporaciones para sus soluciones de documentación, pudiendo así facilitar a los Grupos Automotrices el acceso a sus documentos, y al usuario con sus Derechos de Acceso (ARCO).

_Bases de Datos_

**CloudSQL**

CloudSQL es el producto de GCP para el manejo de bases de datos relacionales SQL. Cuenta con compatibilidad con varias bases de datos SQL como lo es MySQL, PostgreSQL, etc.

Durante el proyecto se utilizará CloudSQL como el servicio en el que se montará la parte de nuestra base de datos relacional y se utilizarán funciones como su opción de MySQL completamente gestionado para facilitar la implementación.

**Firestore**

Firestore es un producto relativamente nuevo de GCP. Consiste en una base de datos gestionada y de tipo no relacional. Firestore es muy amigable para usuarios nuevos y no es muy costosa comparada con las demás alternativas.

Se utilizará Firestore en el proyecto como la base de datos del servicio de mensajería instantánea, ya que cuenta con una base de datos en tiempo real que funciona a través de eventos disparados por los cambios hechos en los datos.

**Backup and DR**

Backup and DR es un servicio de protección de información para GCP.

Este servicio protege al sistema frente a un cambio erróneo, ataques y otros riesgos que atenten contra la información almacenada.

Este servicio protege no solo las bases de datos, si no también a las maquinas virtuales propuestas para la aplicación - haciendo así muy fácil restaurar el servicio inmediatamente después de un desastre.

_Servicios de Internet_

**Cloud DNS**

Cloud DNS es un servicio de resolución de nombres de dominio desarrollado por Google.

Este servicio es requerido para operar una aplicación web familiar, útil y agradable al usuario (tanto final, como los grupos automotrices).

Cloud DNS tiene varias variables donde triunfa frente a otros servicios de DNS: por ejemplo, es el DNS más rápido disponible en internet, y tiene una precisión del 97.2%.

**Cloud CDN**

Cloud CDN es un servicio de entrega de contenido desarrollado por Google con las aplicaciones web implementadas en GCP en mente. Este servicio se utiliza para poder reducir el esfuerzo requerido por la aplicación para enviar contenido multimedia (fotos, videos, etc.)

No usar un CDN puede resultar en una ralentización del servicio y afectar de forma severa a su escalabilidad y accesibilidad a muchos usuarios.

Cloud CDN ofrece una integración fluida con GCP, e incluso apalanca otros servicios de Google para ofrecer una seguridad extendida - como Google Cloud Armor.

Aunque Cloud CDN se queda muy corto frente a los CDNs mas populares - como CloudFlare - en cuanto a presencia (puntos en la red), es mucho mas rápido gracias a la utilización de protocolos exclusivos de Google que optimizan el rendimiento.

**Cloud Load Balancing**

Cloud Load Balancing es un servicio de distribución y balanceo de carga global desarrollado por Google. Este balanceador responde al tráfico de la aplicación en tiempo real para instancias nuevas virtualizaciones del equipo y aliviar el esfuerzo de las existentes en tiempo de uso masivo.

Cloud Load Balancing ofrece gestiones automáticas para escalación - haciendo que en tiempo de estrés sobre la aplicación pueda escalar el servicio de manera instantánea.

Cloud Load Balancing puede admitir de más de un millón de peticiones por segundo, y es integrable con el CDN propuesto sin requerir esfuerzo absoluto.

_Inteligencia de Negocios_

**Cloud Functions**

Cloud Functions es uno de los servicios de cómputo que ofrece Google Cloud Platform. Consiste en un espacio de procesamiento para funciones individuales o pequeñas que se activan por medio de un trigger.

En nuestro caso, este trigger será una llamada al API al que hagan referencia, y las usaremos en el desarrollo del proyecto para montar los diferentes servicios por los que se compone nuestra aplicación.

**BigQuery**

BigQuery es el servicio de almacén de datos de GCP por excelencia. Este servicio está diseñado para almacenar datos crudos y específicos que agrupados forjan big data sobre el servicio.

BigQuery permite la fácil administración del almacén puesto que deshace la necesidad de tener un administrador de base de datos asignado al automáticamente gestionar la administración.

Además esta solución es amigable con los procesos operativos del desarrollo y de la administración de la implementación: ofrece la capacidad de estimar el costo previo a una consulta, y a setear cuotas y límites así como notificaciones del mismo.

Este servicio se utilizaría para el almacenamiento de datos de uso de la plataforma (clicks, scrolls, etc) para su limpieza, y análisis con herramientas de BI. Estos datos son recopilados de manera extensa por lo que generan demasiada información que no es sustentable en los servicios de BD mencionados anteriormente.

**Looker**

Looker es un servicio de Inteligencia de Negocios de Google. Este servicio es traducible con múltiples bases y almacenes de datos (incluida BigQuery - la propuesta para este servicio) para la generación de estadísticas de inteligencia con base en big data.

Este servicio será aplicado a la plataforma para la generación de estadísticas en tiempo real de la plataforma. Aprovechando su utilidad de recolección, cómputo, y flujos de trabajo por evento: Looker generará estadísticas de uso para poder evaluar la sustentabilidad, rentabilidad y rendimiento de la plataforma: permitiendo al equipo generar cambios en la implementación a raíz del uso sin necesidad de generar un consenso o estudio tardado.

_Comunicación_

**Firebase**

Firebase es una suite de servicios de hosting de Google. Estos servicios de hosting se enfocan principalmente en soluciones de tiempo-real, ya sea contenido, notificaciones o autenticación.

Siendo una suite de Google, es fácilmente integrable a los servicios de GCP. Además operando como un Backend-as-a-Service, se encarga de la gestión automática de algunas configuraciones críticas para lo que se utilice.

En este caso, el servicio puede apalancarse para crear el sistema de Chat en Vivo sin tener que involucrar directamente el backend del servicio - segmentando así el servicio de una de las funcionalidades críticas y más complejas del desarrollo.

**Natural Language Processing AI API**

NLP API es un producto de GCP que apalanca los esfuerzos de aprendizaje automatizado de Google para desarrollar un modelo que traduzca I/O natural en algo mas discreto.

Esta herramienta podrá utilizarse para darle una familiaridad y experiencia increíble al proceso de buscar un automóvil en el servicio - ingresando la búsqueda sin estructuración del cliente y devolviéndole en filtros útiles para el esquema de datos del servicio.

**SendGrid**

SendGrid es un API de envío de correos electrónicos masivos de Twilio - una de las empresas de comunicación por Internet más grandes del mundo. Este servicio es utilizado por miles de plataformas de usuarios por Internet: Uber, Airbnb, etc - para sus servicios de correspondencia de mercado y transaccional.

Las habilidades y facultades de hacer de SendGrid una herramienta crítica para el desarrollo de la UX del servicio: confirmación de registro por correo, notificaciones de estatus, y correspondencia de marketing.

Además SendGrid opera un financiamiento por evento, es decir se paga conforme se va utilizando el servicio - para así no pagar de mas en un momento que no llegase a estar usando. SendGrid API es ampliamente soportado por GCP y varios de sus productos - de tal manera que Google tiene manuales ya hechos para integración.

### _Restricciones de Diseño e Implementación_
En cuanto a las posibles restricciones que se tienen en el desarrollo de la aplicación, una de las más relevantes es el acceso a los servicios de la nube. En este caso, se tienen algunos créditos para AWS o Google Cloud, sin embargo, no necesariamente son suficientes. Similarmente, más adelante en el desarrollo, se podrían encontrar limitaciones de tecnologías tales como APIs que puedan no ser open source. 

### _Supuestos y Dependencias_
En el caso de las suposiciones y dependencias que se consideran para la creación del presente documento son las siguientes: 
1.  Las agencias y grupos automotrices tienen la disposición de transformar digitalmente sus negocios. 
2. Una sección creciente de clientes prefieren hacer sus compras de coches en línea.
3. Se buscarán ciertas tecnologías externas tales como verificadores de INE o procesadores de pago. 

---
## _Características del Sistema_
En la presente sección se describirán las características que serán planteadas para el sistema. Éstas incluyen los requerimientos funcionales, los requerimientos no funcionales, las historias de usuario y los casos de uso. Es relevante mencionar, que todas las anteriores fueron organizadas basadas en el tipo de usuario.

### _Historias de Usuario_
En el caso de las historias de usuario, se utilizaron para definir las necesidades en cuanto a funcionalidad de lo que requiere cada usaurio. Además, son de gran utilidad para realizar estimaciones y priorizar tareas, pues fueron diseñadas de manera que un EPIC (una tarea muy grande) se granulara lo suficiente para tener pequeñas tareas. Es posible ver las historias de usuario en el siguiente link: 
[Link a Historias de Usuario](https://docs.google.com/spreadsheets/d/1OA5w8ZCMMJ0BG5iCwsFjzHLo56HG9Y7ydczv7Ib8RqM/edit?usp=sharing)

### _Requerimientos Funcionales_
En cuanto a los requerimientos funcionales de la plataforma por tipo de usuario, se establecieron los siguientes.

#### **Usuario Final**
| ID | Concepto | Descripción |
|----|----------|-------------|
| REQ_FUN[1001] | Filtrar catálogo de autos | La búsqueda de autos debe ser posible a través de múltiples filtros por categoría que involucren características del auto al igual que sus usos y aspectos relacionados |
| REQ_FUN[1002] | Solicitud de prueba de manejo | El usuario debe tener la posibilidad de solicitar una prueba de manejo del auto que está interesado al lugar de su conveniencia |
| REQ_FUN[1003] | Administrar documentos del usuario | La plataforma debe permitir que el usuario suba los documentos requeridos para la compra de coches con el fin de autorizar dichos documentos |
| REQ_FUN[1004] | Comparar de autos | La plataforma debe permitir al usuario comparar las distintas opciones de autos (con diferentes modelos, dos ofertas del mismo auto, etc) con un máximo de 5 coches a comparar a la vez |
| REQ_FUN[1005] | Iniciar el proceso de orden de compra | La plataforma debe permitir al usuario elegir el coche que desea comprar, visualizar su orden de compra y confirmarla para posterior asignación a un agente |
| REQ_FUN[1006] | Seguimiento de orden de compra | La plataforma debe permitir que el usuario suba los documentos requeridos, conozca el estatus de su orden y los pasos requeridos para dar continuidad a su compra |
| REQ_FUN[1007] | Comunicación con agentes | La plataforma debe permitir al usuario contacto con el agente asignado por medio de la plataforma a manera de contacto inicial |
| REQ_FUN[1008] | Notificaciones | La plataforma debe mostrar las notificaciones correspondientes al usuario y enviar correos con las mismas |
| REQ_FUN[1009] | Registrar usuario | La plataforma debe solicitar el registro de usuario una vez que pide cotización o prueba de manejo. Debe ser posible que el usuario ingrese sus datos para crear una cuenta |
| REQ_FUN[1010] | Actividad de usuario | El usuario debe poder revisar información acerca de su actividad en la plataforma desde la vista de su perfil. Incluye compras, pruebas de manejo, comunicación con agentes y posibles estatus de cualquier movimiento mencionado anteriormente |
| REQ_FUN[1011] | Portal de usuario con expediente | El usuario debe poder ver, editar, borrar y actualizar su información de contacto, documentos, y otros datos desde la vista del portal de usuario |
| REQ_FUN[1012] | Asignación automática de vendedor | La plataforma debe asignar a la orden de compra que solicite el usuario un vendedor de manera automática (utilizando FIFO) |
| REQ_FUN[1013] | Historial de autos revisados | La plataforma debe mostrar al usuario los últimos autos que revisó |
| REQ_FUN[1014] | Cotizar automáticamente | La plataforma debe permitir al usuario cambiar ciertos parámetros tales como enganche y mensualidades para obtener un estimado del costo del auto de su interés |
| REQ_FUN[1015] | Listas de espera con emails desde la plataforma | La plataforma debe permitir al usuario inscribirse a una lista de espera para recibir notificaciones de disponibilidad de los autos de su interés |
| REQ_FUN[1016] | Agregar autos como favoritos | Los usuarios registrados deben poder añadir autos a un apartado de favoritos para futura referencia |
| REQ_FUN[1017] | Borrar usuario | La plataforma debe permitir al usuario borrar su cuenta |

#### **Usuario Gerente**
| ID | Concepto | Descripción |
|----|----------|-------------|
| REQ_FUN[2001] | Subir coches nuevos | El gerente debe tener la capacidad de dar de alta distintos coches con sus respectivas características y posibles accesorios mediante un formulario |
| REQ_FUN[2002] | Gestionar usuarios vendedores | El gerente debe poder hacer la alta y baja de sus vendedores de la plataforma |
| REQ_FUN[2003] | Subir coches nuevos mediante un archivo de tipo csv, excel y/o json | El gerente debe de tener la capacidad de dar de alta múltiples coches a la vez mediante un archivo de tipo csv, excel y/o json. Las plantillas estandarizadas serán provistas por el sistema |
| REQ_FUN[2004] | Visualizar ventas | La plataforma debe permitir al gerente visualizar las ventas activas |
| REQ_FUN[2005] | Reasignar vendedores | La plataforma debe permitir al gerente reasignar a una orden de compra a los vendedores |
| REQ_FUN[2006] | Gestionar publicaciones de autos | La plataforma debe permitir ocultar, editar y borrar publicaciones de autos que sube el usuario gerente |
| REQ_FUN[2007] | Registrar opciones de financiamiento | La plataforma debe permitir al usuario gerente registrar las opciones de financiamiento que quiere ofrecer para sus autos |
| REQ_FUN[2008] | Registrar opciones de seguros | La plataforma debe permitir al usuario gerente registrar las opciones de seguro que quiere ofrecer para sus autos |

#### **Usuario Vendedor**
| ID | Concepto | Descripción |
|----|----------|-------------|
| REQ_FUN[3001] | Revisar de documentación del cliente | La plataforma debe permitir que el vendedor visualice, descargue, dé retroalimentación, decline o acepte los documentos de los clientes |
| REQ_FUN[3002] | Gestionar órdenes de compra | La plataforma debe permitir que el vendedor gestione órdenes de compra y ver su histórico |
| REQ_FUN[3003] | Gestionar solicitudes de cita | La plataforma debe permitir que el vendedor acepte, decline y dé seguimiento a las solicitudes de cita para ver el auto o revisar otro tema |
| REQ_FUN[3004] | Gestionar avance de compra | La plataforma debe permitir que el vendedor cambie el estado de avance de compra de sus respectivos compradores |

#### **Usuario Grupo Automotriz**
| ID | Concepto | Descripción |
|----|----------|-------------|
| REQ_FUN[4001] | Crear perfil para grupo automotriz | La plataforma debe permitir a los grupos automotrices darse de alta y subir toda la información necesaria para ser verificada |
| REQ_FUN[4002] | Estadísticas del Grupo | El grupo automotriz debe tener acceso a estadísticas relevantes de sus agencias, por ejemplo: resumen del perfil de sus agencias, ventas totales, ventas por agencia. También deberá poder acomodar y filtrar esta información dependiendo de sus necesidades|
| REQ_FUN[4003] | Exportar estadísticas del Grupo | La plataforma debe permitir al grupo automotriz la descarga de sus estadísticas |
| REQ_FUN[4004] | Solicitar la creación del dominio de agencias | Los grupos automotrices deben poder proporcionar la información de sus agencias con el fin de crear un dominio una vez que se verifique la información |
| REQ_FUN[4005] | Solicitar la creación del usuario gerente | La plataforma debe permitir al grupo proporcionar la información de sus gerentes para que sean agregados a cierto dominio de agencia |

#### **Usuario Administración de la Plataforma**
| ID | Concepto | Descripción |
|----|----------|-------------|
| REQ_FUN[5001] | Coleccionar de datos | Se deben coleccionar y almacenar datos como: número de vehículos en un catálogo por agencia, clicks de usuarios en compra/prueba de vehículo, agencias con mayor número de ventas, vehículos más vendidos, número de agencias, número de grupos|
| REQ_FUN[5002] | Verificar | La plataforma debe permitir la verificación de dada de alta tanto de grupos automotrices como de agencias y gerentes |
| REQ_FUN[5003] | Gestionar datos | La plataforma debe permitir agregar, editar y borrar datos |
| REQ_FUN[5004] | Exportar información de usuarios | La plataforma debe permitir la exportación de datos generales del usuario |

### _Requerimientos No Funcionales_

Para los requerimientos no funcionales, se consideraron los siguientes: 
| ID | Concepto | Descripción |
|----|----------|-------------|
| REQ_NO_FUN[0001] | Diseño intuitivo | La plataforma debe ser sencilla de utilizar y debe incluir elementos que faciliten el entendimiento de uso |
| REQ_NO_FUN[0002] | Diseño de UX armonioso | Se debe crear una interfaz armoniosa entre el tamaño, color y diseño de cada aspecto de la plataforma |
| REQ_NO_FUN[0003] | Transparencia | La plataforma debe mostrar los datos de todos los coches de manera que los usuarios puedan tomar la decisión más informada posible |
| REQ_NO_FUN[0004] | Divulgación de la información legal pertinente al usuario | El usuario debe poder acceder a los términos y condiciones redactadas por el equipo legal de NDS |
| REQ_NO_FUN[0005] | Compra a cualquier agencia | La plataforma debe permitir que los usuarios compren de cualquier agencia sin importar en dónde se encuentre |
| REQ_NO_FUN[0006] | Esquema de datos estandarizado | Debe existir un estándar de datos a través de la plataforma que permita una inteligibilidad mutua entre usuarios |
| REQ_NO_FUN[0007] | Asegurar que la información de ventas y usuarios sea guardada por lo menos cinco (5) años antes de ser descartada | Por motivos legales y de auditoría, los datos que se utilicen en la plataforma deben ser guardados de manera segura por lo menos cinco años. No borrar información, deshabilitar cuentas inactivas únicamente |
| REQ_NO_FUN[0008] | Protección de información | El sistema debe ser capaz de proteger la integridad de la información de los usuarios. Se deben integrar técnicas de cifrado y seguridad |
| REQ_NO_FUN[0009] | Tutoriales y sección de FAQ | La plataforma debe mostrar al usuario distintos tutoriales y preguntas frecuentes respecto a la aplicación |
| REQ_NO_FUN[0010] | Política de Privacidad | La plataforma muestra y es transparente con su política de privacidad |
| REQ_NO_FUN[1011] | Visualización predeterminada del catálogo | La plataforma, al iniciar una búsqueda, debe mostrar el catálogo completo de forma ordenada |
| REQ_NO_FUN[1012] | Método de autorización | La plataforma debe tener incluido un método de autorización para cada usuario, para manejar accesos |

---
## _Requerimientos de Datos_
En esta sección se describiran a detalle los requerimientos sobre los datos que se manejarán en el sistema.

### _Estructura Lógica de los Datos_
Los dato que se almacenarán en la base de datos de la aplicación y las relaciones entre si se describen en el siguiente diagrama de entidad relación.
![Diagrama ER](Media/SRSmedia/Diagrama_ER_BD.png)
A continuación se hace una descripción de cada una de las entidades

### _Diccionarios de Datos_
**Grupo_Automotriz**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único del Grupo Automotriz | PK |
| Nombre | string | Nombre del Grupo | |
| Dirección | string | Dirección del Grupo | |
| Telefono1 | int | Teléfono principal del Grupo Automotriz | |
| Telefono2 | int | Teléfono secundario del Grupo Automotriz | |
| Estatus | string | Estatus del grupo en términos de procesos de dada de alta y baja | |

**Agencia**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único de la Agencia | PK |
| Nombre | string | Nombre de la Agencia | |
| Dirección | string | Dirección de la Agencia | |
| Telefono1 | int | Teléfono principal de la Agencia | |
| Telefono2 | int | Teléfono secundario de la Agencia | |
| Estatus | string | Estatus de la Agencia en términos de procesos de dada de alta y baja | |
| GrupoAutomotriz | int | ID del Grupo Automotriz al que pertence | FK |

**Usuario_GA**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único del Usuario administrador de Grupo Automotriz | PK |
| GrupoAutomotriz | int | ID del Grupo Automotriz al que pertence | FK |
| Nombre | string | Nombre del administrador del grupo | |
| Apellidos | string | Apellidos del administrador del grupo | |
| Telefono1 | int | Teléfono principal del administrador del grupo | |
| Telefono2 | int | Teléfono secundario del administrador del grupo | |
| Email1 | string | Dirección de correo primaria del administrador del grupo | |
| Email2 | string | Dirección de correo secundaria del administrador del grupo | |

**Usuario_Gerente**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único del Usuario administrador de Agencia (Gerente)| PK |
| Agencia | int | ID de la Agencia a la que pertence | FK |
| Nombre | string | Nombre del gerente | |
| Apellidos | string | Apellidos del gerente | |
| Telefono1 | int | Teléfono principal del gerente | |
| Telefono2 | int | Teléfono secundario del gerente | |
| Email1 | string | Dirección de correo primaria del gerente | |
| Email2 | string | Dirección de correo secundaria del gerente | |

**Usuario_Vendedor**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único del Usuario Vendedor| PK |
| Agencia | int | ID de la Agencia a la que pertence | FK |
| Nombre | string | Nombre del vendedor | |
| Apellidos | string | Apellidos del vendedor | |
| Telefono1 | int | Teléfono principal del vendedor | |
| Telefono2 | int | Teléfono secundario del vendedor | |
| Email1 | string | Dirección de correo primaria del vendedor | |
| Email2 | string | Dirección de correo secundaria del vendedor | |

**Usuario_Final**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único del Usuario Final| PK |
| Nombre | string | Nombre del usuario final | |
| Apellidos | string | Apellidos del usuario final | |
| Domicilio | string | Domicilio del usuario final | |
| Telefono1 | int | Teléfono principal del usuario final | |
| Telefono2 | int | Teléfono secundario del usuario final | |
| Email1 | string | Dirección de correo primaria del usuario final | |
| Email2 | string | Dirección de correo secundaria del usuario final | |

**Usuario_Admin**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único del Usuario Administrador de plataforma| PK |
| Nombre | string | Nombre del administrador | |
| Apellidos | string | Apellidos del administrador | |
| Telefono1 | int | Teléfono principal del administrador | |
| Telefono2 | int | Teléfono secundario del administrador | |
| Email1 | string | Dirección de correo primaria del administrador | |
| Email2 | string | Dirección de correo secundaria del administrador | |

**Listing_Coche**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único de la publicación del coche| PK |
| Agencia | int | ID de la Agencia a la que pertenece | FK |
| Gerente | int | ID del gerente que realizó la publicación del coche | FK |
| Fecha | dateTime | Fecha en la que se realizó la publicación| |
| Visibilidad | bool | Estado de visibilidad de la publicación en el catálogo| |
| Marca | string | Marca del coche | |
| Modelo | string | Modelo del coche | |
| Año | int | Año del modelo del coche | |
| Precio | float | Precio del coche en pesos mexicanos | |
| Color | string | Color del coche | |
| Tipo | string | Tipo de coche (Sedán, Van, Hatchback, etc.) | |
| Combustible | string | Combustible del coche | |
| Localización | string | Lugar en donde se encuentra el coche (agencia) | |

**Orden_de_Compra**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único de la orden de compra | PK |
| Comprador | int | ID del usuario que realiza la orden de compra | FK |
| Vendedor | int | ID del usuario vendedor al que se le asigna la orden de compra para dar seguimiento| FK |
| Coche | int | ID del coche que se quiere comprar | FK |
| Estatus | string | Estatus del proceso de compra | | 

**Orden_PruebaManejo**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único de la solicitud de prueba de manejo | PK |
| Solicitante | int | ID del usuario que realiza la solicitud de prueba de manejo | FK |
| Vendedor | int | ID del usuario vendedor al que se le asigna la solicitud de prueba de manejo | FK |
| Coche | int | ID del coche que se quiere probar | FK |
| Estatus | string | Estatus del proceso de prueba de manejo | | 

**Opciones_Financiamiento**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único de la opción de financiamiento | PK |
| Agencia | int | ID de la Agencia que ofrece la opción | FK |
| NombreProveedor | string | Nombre de la empresa que provee el financiamiento| |
| Tasa | float | Tasa de interés de la opción de financiamiento | |
| Enganche | int | Porcentaje de enganche mínimo de la opción de financiamiento | |

**Opciones_Seguros**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único de la opción de seguro | PK |
| Agencia | int | ID de la Agencia que ofrece la opción | FK |
| NombreProveedor | string | Nombre de la aseguradora| |
| Cobertura | string | Cobertura de la opción | |
| PlazoMínimo | int | Plazo mínimo de la opción | |

**Chats**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único del chat | PK |
| Usuario | int | ID del usuario que participa en el chat | FK |
| Vendedor | int | ID del vendedor que participa en el chat| FK |

**Chat_Msgs**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único del mensaje del chat | PK |
| Chat | int | ID del chat al que pertenece el mensaje | FK |
| Remitente | int | ID del remitente del mensaje (cliente o vendedor)| FK |
| Destinatario | int | ID del destinatario del mensaje (cliente o vendedor)| FK |
| ContenidoMsg | string | Contenido del mensaje enviado | |
| Fecha | dateTime | Fecha en la que se envió el mensaje | |

**Documentos_Usuario**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único del documento subido por el usuario | PK |
| Usuario | int | ID del usuario que subió el documento | FK |
| Título | string | Título que le da el usuario al archivo | |
| Descripción | string | Descripción que le da el usuario al archivo | |
| Retroalimentación | string | Retroalimentación que da el vendedor sobre el documento | |
| Estatus | string | Estado de aceptación del documento | |

**Documentos_GA**
| Atributo       | Tipo     | Descripción | Comentario |
|----------------|----------|-------------|------------|
| ID | int | Identificador único del documento subido por el usuario administrador de Grupo Automotriz | PK |
| GrupoAutomotriz | int | ID del administrador de GA que subió el documento | FK |
| Título | string | Título que le da el usuario al archivo | |
| Descripción | string | Descripción que le da el usuario al archivo | |
| Retroalimentación | string | Retroalimentación que da el administrador de la plataforma sobre el documento | |
| Estatus | string | Estado de aceptación del documento | |

### _Características de la Base de Datos_
Debido a la naturaleza del sistema que se desarrollará en donde se cuentan con múltiples funcionalidades o módulos, se requiere una base de datos híbrida - una combinación entre relacional y no relacional. La parte relacional de la base de datos se utilizará para el manejo de datos que sean constantes y que tengan la mayor cantidad de accesos según la prioridad de las funcionalidades de la aplicación. Por otro lado la parte no relacional de la base de datos será utilizada para el manejo de datos cuya naturaleza sea de cache, es decir que cambien constantemente y que no tengan una gran cantidad de accesos.

Para el almacenamiento de documentos se utilizará la herramienta DynamoDB de Amazon Web Services o en el caso de usar otro proveedor Buckets de Google Cloud Platform.

De igual manera se utilizarán Bases de Datos Gestionadas como Firebase para algunas funcionalidades de la aplicación como el chat.

### _Reportes_
En el caso de los reportes, no se planea generarlos directamente. Sin embargo, se harán consultas de las ventas mensuales de cada agencia, así como de la actividad de los usuarios en la plataforma. 

### _Adquisición, Integridad, Retención y Disposición_
Debido al carácter de los datos que estará manejando el sistema y la importancia de la información que se manejará, se tomarán diferentes medidas para garantizar la integridad y seguridad de los datos. 

**Integridad de los datos** <br/>
Una de estas medidas es una base de datos de repaldo que se actualice cada cierto tiempo, esto con el fin de que en caso de que se presente algún problema con la base de datos principal, se pueda recuperar la información de la base de datos de respaldo.

**Seguridad de los datos** <br/>
La seguridad de los datos será manejada con productos del proveedor de nube que se elija para el desarrollo del programa. Se utilizarán herramientas de seguridad como el cifrado de datos, autenticación de usuarios, etc. De igual manera se pondrán restricciones de leido/borrado de datos para los usuarios que no tengan permiso para realizar dichas acciones.

Asimismo, la adquisición de los datos será a través de las interacciones de los usuarios con la plataforma y se planea tener dichos datos en la nube de manera que estén altamente disponibles.

---
## _Requerimientos de la Interfaz Externa_
En la presente sección, se incluyen las características principales de la interfaz de usuario, explicando el flujo general que tendrá cada tipo de usuario y asegurando una interacción agradable con el sistema. A continuación, se explican elementos esenciales del diseño de la interfaz y se muestran los flujos que seguirá el usuario al ingresar en la aplicación. 

### _Elementos Relevantes del Diseño de la Interfaz de Usuario_
Puesto a que se busca una experiencia de usuario altamente óptima, se consideran distinos aspectos en el diseño de la interfaz. En primer lugar, se plantea trabajar con tarjetas para facilitar la vista de elementos en la página (en la visualización de catálogos tanto de coches como de usuarios) como se muestra en el siguiente boceto.

![Boceto para catálogo](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/SRSmedia/boceto_catalogos.png)

Como es posible observar, las pantallas están diseñadas para observar mediante tarjetas los catálogos, incluyendo filtros en la parte izquierda de la pantalla, una barra de búsqueda arriba y una barra de navegación que estará presente en todas las vistas del usuario. 

Asimismo, se planea utilizar distintos símbolos con el fin de hacer que la interacción sea más simple e intuitiva. 

Es relevante reiterar que se trata de una aplicación web por lo que todos los diseños que se generen posteriormente (considerando lo mencionado previamente) serán orientados a un navegador web.

### _Mapa de Navegación General_
En cuanto al mapa de navegación, este describe de una manera visual y muy general las pantallas que serán mostradas a los usuarios en un flujo. Es importante comentar que se trata únicamente de un esquema de pantallas, por lo que no contiene diseño y es general. Para ver dicho mapa, es necesario acceder al siguiente link:
[Mapa de Navegación Primera Versión](https://www.figma.com/proto/NRQZxBVY6hrFFCrxHObOMm/QChau-Mockup?node-id=2%3A2&scaling=min-zoom&page-id=0%3A1&starting-point-node-id=2%3A2&show-proto-sidebar=1)

Para poder acceder a los flujos de los distintos usuarios, es necesario ingresar al usuario deseado mediante los botones que se encuentran en la ventana emergente izquierda. 
En cuanto al mapa de navegación, este describe de una manera visual y muy general las pantallas que serán mostradas a los usuarios en un flujo.

### _Interfaces de Software_
En cuanto a las interfaces de software se utilizarán distintas APIs para llevar a cabo distintas funcionalidades. 

### _Interfaces de Hardware_
En este caso, no aplican las interfaces de hardware por lo que no se explicará. 

### _Interfaces de Comunicación_
Las interfaces de comunicación con el cliente consistirán en el navegador web y el correo electrónico. Además de las anteriores, no aplica ninguna otra descripción. 

## _Diagramas de Casos de Uso_

A continuación, se muestran los diagramas de caso de uso para el presente proyecto: 

### _Diagramas de Usuario Final_

**Compra de un Auto**

![Compra de un Auto](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/compra_auto_uf.png)

**Contacto con un Agente**

![Contacto con un Agente](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/contacto_agente_uf.png)

**Gestión de Cuenta**

![Gestión de Cuenta](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/cuenta_uf.png)

**Herramientas de Consulta**

![Herramientas de Consulta](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/herramientas_consuta_uf.png)

**Notificaciones**

![Notificaciones](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/notificaciones_uf.png)

**Navegación del Catálogo**

![Navegación del Catálogo](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/nav_catalogo.png)

**Solicitud de Prueba de Manejo**

![Solicitud de Prueba de Manejo](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/prueba_manejo_uf.png)

### _Diagramas de Usuario Gerente_

**Registro de Autos**

![Registro de Autos](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/registro_autos_ug.png)

**Registro de Vendedores**

![Registro de Vendedores](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/registro_vendedores_ug.png)

### _Diagramas de Usuario Vendedor_

**Control de Venta**

![Control de Venta](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/control_venta_uv.png)

**Gestión Perfil**

![Gestión Perfil](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/gestion_perfil_uv.png)

**Gestión de Solicitudes de Pruebas de Manejo**

![Gestión de Solicitudes de Pruebas de Manejo](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/pruebas_manejo_uv.png)

### _Diagramas de Usuario Administrador Grupo Automotriz_

**Gestión de Grupo Automotriz**

![Gestión de Grupo Automotriz](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/gestion_uga.png)


### _Diagramas de Usuario Admin Plataforma_

**Administración de Agencias y Grupos Automotrices**
![Administración de Agencias y Grupos Automotrices](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/CasosDeUso/admin_uga_ua_uadmin.png)

## _Diagramas de Actividad_ ##
A continuación se muestran los diagramas de actividad que describen los flujos principales en la aplicación: 

**Usuario Final**
![Usuario Final](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/DiagramaActividad/DiagramaActividad_UsuarioFinal.png)

**Usuario Administrador**
![Usuario Administrador](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/DiagramaActividad/DiagramaActividad_UsuarioAdministrador.png)

**Usuario Vendedor**
![Usuario Vendedor](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/DiagramaActividad/DiagramaActividad_UsuarioVendedor.png)
    
**Usuario Gerente**
![Usuario Gerente](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/DiagramaActividad/DiagramaActividad_UsuarioGerente.png)

**Usuario Grupo Automotriz**
![Usuario Grupo Automotriz](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/DiagramaActividad/DiagramaActividad_GrupoAutomotriz.png)

## _Atributos de Calidad_

### _Usabilidad_
Uno de los requerimientos (REQ_FUN[1001]) que harán a este software más user-friendly e intuitivo es del sistema de filtrado para el catálogo de autos. No solo se incluyen filtros tradicionales por modelo o marca, sino que se puede contestar un cuestionario con el fin de encontrar autos que cumplan con las necesidades que se buscan.

Otro requerimiento que hará que la plataforma tenga un valor agregado sobre las demás de su tipo es la característica de poder comparar los autos que se encuentran dentro del catálogo (REQ_FUN[1005]), señalando diferencias entre estos y entre la información de compra que tengan.

Adicionalmente a las características de navegación, requerimientos como poder comunicarse con un agente asignado (REQ_FUN[1008]) al seguimiento de la compra hacen la diferencia en la experiencia de usuario, impulsando el trato y servicio de un vendedor junto con la versatilidad y simplicidad de un proceso digitalizado.

Con la intención de mejorar la experiencia del usuario en la etapa de navegación previa a la compra, tenemos un sistema de cotización semiautomática (REQ_FUN[1015]), con el fin ofrecer transparencia en el precio real que conlleva la compra de un vehículo. 

### _Desempeño_
Es necesario señalar algunos objetivos de desempeño para los requerimientos del software; comenzando por el sistema de administración de documentos referentes a la compra de autos (REQ_FUN[1012]), donde el usuario final debe poder subir los documentos necesarios y adicionales a la plataforma, se espera que se pueda manejar un espacio de almacenamiento flexible y que se pueda hacer consulta constante de estos documentos por parte del usuario vendedor.

Otro objetivo de rendimiento en el sistema es tener los medios de recopilar información (REQ_FUN[5000], ) del mismo para ser después analizada y explotada por los usuarios administradores de la plataforma, buscando así mejorar el software y tomar decisiones informadas para el negocio.

### _Seguridad_
Dado que se van a estar manejando datos sensibles de los usuarios al momento de realizar una acción avanzada dentro de la plataforma, el usuario final tiene el control completo de su información (REQ_FUN[1012], REQ_FUN[1018], REQ_FUN[5002]), dejando disponible la opción de borrar y editar datos o documentos, al igual que borrar la cuenta por completo.

Al mismo tiempo que se respeta la decisión de divulgación de datos de cada usuario, también se busca proteger estos datos mediante la integración de técnicas de cifrado y seguridad (REQ_NO_FUN[0008]), de manera que se pueda mantener la integridad de la información que guardamos como plataforma.

Por todo lo anterior y más, se va a tener una política de privacidad (REQ_NO_FUN[0010]), que a través de los términos y condiciones de uso exprese toda la información que debe saber el usuario a cerca de su información, actividad en la plataforma y datos adicionales.

### _Protección_

En cuanto la protección de posibles pérdidas o daños de información, específicamente cuando un usuario opta por borrar su información de la plataforma; se respetará el borrado de los datos de cuenta, sin embargo, en caso de que el usuario haya hecho una compra, esta información será guardada por lo menos cinco años (REQ_NO_FUN[0007]). Lo anterior principalmente por motivos legales y de auditoría. 

## _Requerimientos de Internacionalización y Localización_
En este caso, se trata de una aplicación con alcance a la República Mexicana, por lo que esta sección no aplica. 

## _Otros Requerimientos_
En cuanto a requerimientos adicionales encontrados, se tienen los siguientes. 

| ID | Requirimiento | Descripción |
|-----|-----------------|------------------------|
| 6001 | Cumplimiento Normativo de LFPDPPP | Debido a que el sistema gestiona la información identificable de las personas mexicanas - la Ley Federal de Protección Personales en Posesión de Particulares obliga al sistema a regularse frente a los articulos que hacen referencia al los derechos ARCO del ciudadano. |
| 6002 | Modelo Opt-In de Cookies | Debido a la tendencia internacional de gestión de cookies que varios servicios estan obligados a hacer por regulaciones como el GDPR, el sistema debe seguir un modelo de consentimiento explicito para la gestión de cookies no funcionales. |
| 6003 | Estandár de Accesibilidad | Para una promoción sustentable de los servicios de Internet, el sistema debe ofrecer alternativas de accesibilidad para usuarios con dificultades - e.j. reCAPTCHA |
| 6004 | Cumplimiento de Estandares de la Procuraduría Federal de Protección al Consumidor | Debido a que el sistema conduce un sistema de ofertas y ventas, debe intentar apegarse a la buena conducta referida por la PROFECO - para así minimizar riesgos o pérdida de reputación | 
| 6005 | Selección de Vocabulario Accesible | Para que el sistema pueda ser rentable y accesible para todos los usuarios, debe usar vocabulario común pero llamativo - facilitando la actividad de indización de los Motores de Busquéda y ser promovido mas fácilmente.|

## _Apéndices_

### _Apéndice A: WBS_
<!-- ![WBS](../Docs/Media/SRSmedia/wbs.png) -->

![WBS](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/SRSmedia/wbs.png)

### _Apéndice B: Diagrama de Gantt_

<!-- ![diagrama de Gantt](../Docs/Media/SRSmedia/Gantt_parte1.png) -->

<!-- ![diagrama de Gantt](../Docs/Media/SRSmedia/Gantt_parte2.png) -->

![diagrama de Gantt](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/SRSmedia/Gantt_parte1.png)

![diagrama de Gantt](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/SRSmedia/Gantt_parte2.png)

### _Apéndice C: Tableros de Kanban_
Enlace al
[Tablero de Kanban](https://trello.com/w/qchausoftware)

### _Apéndice D: Análisis de Margen_
Enlace al
[Análisis de Margen](https://docs.google.com/spreadsheets/d/1UTt1D2rFVk_DhkA7mzKPPlH6Srpp3uOx5DZERmDJf3g/edit?usp=sharing)

### _Apéndice E: Análisis de Riesgos_
Enlace al 
[Análisis de Riesgos](https://docs.google.com/document/d/1PCigrMcjWb4i5g_0i9aFNPFGGtTjEMCb-dS_vvqyhmA/edit?usp=sharing)

### _Apéndice F: Documento de Historias de Usuario_
[Link a Historias de Usuario](https://docs.google.com/spreadsheets/d/1OA5w8ZCMMJ0BG5iCwsFjzHLo56HG9Y7ydczv7Ib8RqM/edit?usp=sharing)
