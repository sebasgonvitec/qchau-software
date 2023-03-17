

# Documento de Pruebas




# Índice

[**Índice**](#índice)

[**Introducción**](#introducción)

[Objetivo](#objetivo)

[Descripción del Proyecto](#descripción-del-proyecto)

[Audiencia](#audiencia)

[Dinámicas](#dinámicas)

[Estáticas](#estáticas)

[Dependencias](#dependencias)

[**Estrategia de Pruebas**](#estrategia-de-pruebas)

[Dinámicas](#dinc3a1micas-1)

[Funcionales](#funcionales)

[Suposiciones sobre las Pruebas	](#suposiciones-sobre-las-pruebas)

[Objetos de Prueba](#objetos-de-prueba)

[Niveles de Prueba	](#niveles-de-prueba)

[Criterios de Entrada y Salida](#criterios-de-entrada-y-salida)

[No funcionales](#no-funcionales)

[Estáticas](#estc3a1ticas-1)

[**Manejo de Pruebas**](#manejo-de-pruebas)

[Roles](#roles)

[Pruebas por rol](#pruebas-por-rol)

[Dinámicas](#dinc3a1micas-2)

[Estáticas](#estc3a1ticas-2)

[Gantt](#gantt)

[Estimación de Tiempo de Pruebas](#estimación-de-tiempo-de-pruebas)

[Plantilla de Casos de Prueba y Ejecución](#plantilla-de-casos-de-prueba-y-ejecución)

[Plan de comunicación (Github)](#plan-de-comunicación-github)

[Riesgos](#riesgos)

[**Casos de Prueba**](#casos-de-prueba)

[**Pruebas**](#pruebas)

[**Ambiente de pruebas**](#ambiente-de-pruebas)

[**Conclusiones**](#conclusiones)

# Introducción
## Objetivo
El objetivo del presente documento, es proveer una propuesta respecto a las pruebas de software necesarias para el desarrollo y la funcionalidad correcta de la aplicación web de adquisición de autos. Estas contribuirán en la creación de un producto con un control de calidad alto por lo que serán detalladas y argumentadas en este escrito.

En cuanto al plan de pruebas que se realizará, este incluirá la especificación de elementos de software que serán probados, el nivel y la secuencia en la que serán probados, los criterios de salida y la manera en la que se aplicará la estrategia en el ambiente de pruebas. Junto con lo anterior, se considerarán los siguientes puntos:

- Lo que está dentro y fuera del alcance
- Supuestos
- Roles y responsabilidades del equipo QA
- Herramientas
- Entregables
- Gestión de Defectos
- Riesgos
- Calendario

Es relevante recalcar que el presente documento será organizado de manera que se especifiquen claramente las dos vertientes principales de pruebas: dinámicas y estáticas. 
## Descripción del Proyecto
El proyecto que será desarrollado por Qchau Software se trata de una solución para grupos automotrices y compradores de autos en donde se permitirá digitalizar una parte del proceso de compra, evitando visitas excesivas a las agencias. Dicha solución está planteada como una aplicación web que permitirá a los usuarios interactuar con el agente, explorar distintas opciones de autos, obtener cotizaciones estimadas automáticamente, comparar autos, subir y editar sus documentos, solicitar pruebas de manejo y mantener un seguimiento adecuado (con la misma calidad de atención que en una agencia tradicional) de sus compras.

La aplicación beneficiará a los clientes de las agencias ya que les ahorrará tiempo, les proporcionará opciones de distintas marcas y agencias (con distintos planes de financiamiento) en una misma plataforma, y les permitirá tener una visión más clara de lo que quieren. Asimismo, beneficiará a las agencias y grupos automotrices, dándoles un espacio en el que tendrán visibilidad, la posibilidad de agilizar ciertos procesos (como lo es el de la entrega de documentos del cliente) para poder atender a más clientes y la posibilidad de obtener ciertas estadísticas que les podrán ayudar a analizar sus ventas.
## Audiencia
En cuanto a la audiencia, es necesario separar claramente a las entidades involucradas para las pruebas dinámicas y para las pruebas estáticas. 
### Dinámicas
Puesto a que las pruebas dinámicas requieren de la ejecución del código, su audiencia principal son los desarrolladores (quienes generan en código, lo modifican y verifican que funcione dicho código). De igual manera, aquellos encargados de diseñar las pruebas estarán involucrados en las pruebas dinámicas ya que tendrán que planearlas. 
### Estáticas
En cuanto a las pruebas estáticas - que se basan en la revisión de productos de trabajo sin código -, estas involucrarán a los encargados de diseñar las pruebas (ya que mediante la revisión del trabajo podrán planear mejores pruebas), al Product Owner (quien tiene la visión de la perspectiva del cliente por lo que puede evaluar si se cumplen las necesidades del mismo), el Project Manager (quien supervisará que se lleve a cabo el proyecto correctamente y se entreguen las pruebas adecuadas), y cualquier otro participante del producto que quiera revisar los documentos y asegurar la calidad del mismo. 

### Dependencias
Esta lista de hitos es tentativa y puede cambiar debido a las siguientes razones:

a) Problemas en el ambiente de desarrollo

b) Cambios en el alcance

c) Dependencias que impacten los esfuerzos y tiempos

| Nu. | Tipo de Prueba | Ejemplo de Prueba (SUT) | Dependencias (DOC) |
|--|-----------|--------------------|------------------|
| 1 | Pruebas Unitarias | Conexion a BD  | Base de datos completa & API |
| 2 | Pruebas Unitarias | Login de usuario | Base de datos completa & API |
| 3 | Pruebas Unitarias | Registro de usuario | Base de datos completa & API |
| 4 | Pruebas de integracion | Chat entre usuarios | Los usuarios se pueden comunicar de manera exitosa |
| 5 | Pruebas de integracion | Compra de usuario | El usuario puede realizar compras de manera exitosa |
| 6 | Pruebas de validacion | La interfaz de usuario es agradable y facil de usar |  Diseño de interface completo|
| 7 | Pruebas de validacion | El sistema esta completo y el cliente esta satisfecho con su funcionamiento | El sistema esta completo|
| 8| Prueba de sistema | El usuario final puede iniciar sesion, navegar la pagina, realizar compras y comunicarse con vendedores por medio de chat | Base de datos completa, Conexiones API completas, Frontend de usuario final completo|
| 9 | Prueba de sistema | EL usuario administrador puede iniciar sesion, entrar a la vista de administrador, y administrar los usuarios de la pagina | Base de datos completa, Conexiones API completas Frontend de usuario administrador completo | 
| 10 | Prueba de sistema | El usuario vendedor puede iniciar sesion, entrar a la vista de vendedor, y administrar sus productos | Base de datos completa, Conexiones API completas, Frontend de usuario vendedor completo |
| 11 | Prueba de sistema | El usuario de grupo automotriz puede iniciar sesion, entrar a la vista de grupo automotriz, y asignar agencias asociadas | Base de datos completa, Conexiones API completas, Frontend de grupo automotriz completo |
| 12 | Prueba de sistema | El usuario de agencia puede iniciar sesio, entrar a la vista de agencia, y asignar vendedores asociados | Base de datos completa, Conexiones API completas, Frontend de grupo automotriz completo |

# Estrategia de Pruebas
## Dinámicas
Para asegurar la calidad y funcionalidad del producto, se llevarán a cabo diferentes tipos de pruebas en dinámicas en varias etapas del proyecto. Es importante recalcar que NO se harán pruebas de tipo no funcional, tales como pruebas de rendimientos, pruebas de escalabilidad, etc. por cuestiones de tiempo y recursos con los que se cuentan para el desarrollo. Sin embargo el sistema se diseñará y desarrollará tratando de cumplir con los requerimientos no funcionales previamente establecidos.
### Funcionales
Se realizarán distintas pruebas funcionales para asegurar que todos los componentes del sistema funcionen correctamente. Estas se llevarán a cabo de la siguiente manera:

1. Informales

Durante todo el desarrollo se harán pruebas informales sobre los elementos que esté trabajando cada desarrollador. Estas no serán documentadas.

1. Caja Negra

Una vez un elemento esté listo para probarse se realizarán pruebas de Caja Negra de Casos de Uso. Se buscará probar cada uno de los métodos del código. Estas serán documentadas haciendo uso de la plantilla que se encuentra más adelante.

1. Caja Blanca

Si en cualquier etapa de pruebas llegara a haber un resultado no deseado, se llevarán a cabo pruebas de Caja Blanca de los dos tipos:

- Cobertura: en caso de tratarse de un requerimiento con prioridad baja o media
- Camino Básico: en caso de un requerimiento con una prioridad más alta y fundamental para el funcionamiento de la aplicación

De igual manera estas serán documentadas usando plantillas dependiendo de la etapa de pruebas en la que se lleven a cabo.

1. Integración

Se harán pruebas de integración para corroborar la unión de varios componentes unitarios. Serán documentadas usando una plantilla.

1. Aceptación 

Se realizarán pruebas de aceptación, en las cuáles se revisará el funcionamiento de la aplicación en diferentes recorridos. Estas pruebas se llevan a cabo por el equipo de pruebas y en presencia de la Project Manager, Business Analyst, Product Owner y los diferentes stakeholders.

1. Validación

Se realizarán pruebas de validación en donde se corroborará el correcto funcionamiento de diferentes recorridos de la aplicación vistos desde el lado del usuario final. En este caso, nuestros compañeros del otro grupo cumplirán la función de usuarios finales y serán supervisados por el líder de pruebas de cada célula y la Project Manager. Serán documentadas usando una plantilla.

**NO se realizarán pruebas de Humo ni de Inspección**

![Flujo de pruebas](/wiki/Docs/Media/docPruebasMedia/flujo_de_pruebas.png)
<!-- ![Flujo de pruebas](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/docPruebasMedia/flujo_de_pruebas.png) -->


#### Suposiciones sobre las Pruebas
- Todas las pruebas se llevarán a cabo en el mismo ambiente.
- Si el ambiente de pruebas idóneo no se encuentra disponible, se utilizará un ambiente lo más parecido posible.
- Se hará una validación previa de los casos de prueba.
- Se documentarán todas las pruebas menos las informales.
- Se llevará a cabo una revisión de los entregables de cada prueba

#### Objetos de Prueba
A continuación se muestran el alcance a través de unas tablas con todos los objetos que se probarán durante los procesos de pruebas y desarrollo.

**Caja Negra**

En la siguiente tabla se definen las pruebas de caja negra sobre los requerimientos más relevantes de todo el sistema.


|Clave|Objeto|Usuario|Descripción|Prioridad|
| :- | :- | :- | :- | :- |
|P\_CN\_001|Filtros del catálogo de autos|Usuario Final|Se evalúa el resultado del uso de filtros tradicionales sobre el catálogo|Alta|
|P\_CN\_002|Solicitud de prueba de manejo|Usuario Final|Se evalúa la capacidad de completar el formulario de solicitud de prueba de manejo.|Alta|
|P\_CN\_003|Cita para ir con el agente|Usuario Final|Se evalúa la funcionalidad de poder calendarizar una cita con un Agente Vendedor de una agencia.|Baja|
|P\_CN\_004|Administración de documentos de usuario|Usuario Final|Se evalúa la funcionalidad de poder ver y borrar documentos subidos por el usuario.|Alta|
|P\_CN\_005|Contacto con agente|Usuario Final|Se evalúa la funcionalidad del sistema de chat entre el usuario y el agente vendedor.|Alta|
|P\_CN\_006|Redirección a la vista de login|Usuario Final|Se evalúa la funcionalidad de redireccionar al usuario a iniciar sesión al solicitar una prueba de manejo o compra de auto.|Alta|
|P\_CN\_007|Administración de registros de automóviles nuevos por csv/individual|Usuario Vendedor|Se evalúa la funcionalidad de poder registrar y eliminar autos subidos por el usuario vendedor sea por archivo csv o de manera individual|Alta|
|P\_CN\_008|Administracion de usuarios vendedores|Usuario Gerente|Se evalúa la funcionalidad de poder asignar y eliminar usuarios vendedores de una agencia |Alta|
|P\_CN\_009|Administración de agencias asociadas a grupo automotriz|Usuario Grupo Automotriz|Se evalúa la funcionalidad de poder asignar y eliminar agencias asociadas de un grupo automotriz|Media|
|P\_CN\_010|Administración de usuarios gerentes y grupos automotrices|Usuario Administrador|Se evalúa la funcionalidad de poder aceptar y rechazar solicitudes de usuarios gerentes/grupos automotrices|Alta|

**Integración**


|Clave|Objeto|Usuario|Descripción|Prioridad|
| :- | :- | :- | :- | :- |
|P\_I\_001|Login|Todos|Se validará la funcionalidad del Login para todos los usuarios|Alta|
|P\_I\_002|Registro|Gerente, Vendedor, Grupo Automotriz, Final|Se validará la funcionalidad de Registro para usuarios|Alta|
|P\_I\_003|Registro de automóviles|Usuario vendedor|Se validará que el funcionamiento del registro de nuevos automóviles sea correcto|Alta|
|P\_I\_004|Modificacion de automoviles existentes|Usuario Vendedor|Se validará la funcionalidad de modificar automóviles para vendedores|Alta|
|P\_I\_005|Administracion de usuarios vendedores|Usuario Gerente|Se validará que los usuarios de gerente puedan asignar/eliminar vendedores|Alta|
|P\_I\_006|Administración de gerentes/grupos automotrices |Usuario Administrador|Se validará que el usuario administrador puede asignar/eliminar usuarios de gerentes/grupos automotrices|Alta|
|P\_I\_007|Compra de automóviles|Usuario Final|Se validará que el proceso de compra de un automóvil para el usuario final pueda ser realizado de manera correcta |Alta|
|P\_I\_008|Aprobación/rechazo de compras|Usuario vendedor|Se validará que el usuario vendedor sea capaz de aprobar/rechazar solicitudes de compra|Alta|
|P\_I\_009|Comunicación entre vendedor y usuario final|Final, Vendedor|Se validará que el usuario final y vendedor se puedan comunicar de manera exitosa mediante el chat dentro de la aplicación|Alta|
|P\_I\_010|Solicitud de Prueba de Manejo|Usuario Final|Se validará que el usuario final pueda en el proceso de iniciar sesión o en su defecto crear una, al igual que seguir los pasos de solicitud y formulario con éxito.|Alta|
|P\_I\_011|Aprobación/rechazo de prueba de manejo|Usuario Vendedor|Se validará que el usuario vendedor sea capaz de aprobar/rechazar solicitudes de prueba de manejo|Alta|


**Validación/Aceptación**


|Clave|Objeto|Usuario|Descripción|Prioridad|
| :- | :- | :- | :- | :- |
|P\_V\_001|Landing Page - Busqueda - Listado - Login|Usuario Final|Recorrido desde cuando el usuario entra a la plataforma y se le pide que inicie sesión solamente a la hora de que quiere continuar con la compra de un auto|Media|
|P\_V\_002|Landing Page - Login - Busqueda - Listado - Inicio de Proceso de Compra|Usuario Final|Recorrido desde cuando el usuario entra a la plataforma, inicia sesión en la página de login, busca el coche que quiere comprar e inicia el proceso de compra|Alta|
|P\_V\_003|Landing Page - Busqueda - Comparar autos|Usuario Final|Recorrido cuando el usuario utiliza la plataforma para la comparación de autos sin iniciar sesión|Media|
|P\_V\_004|Landing Page - Login - Búsqueda - Inicio de Venta - Comunicación con Agente - Subida de Documentos - Pago de contado - Finalización de Compra |Usuario Final|Recorrido completo desde que el usuario inicia sesión hasta que finaliza su proceso de compra. Este proceso será una simulación ya que la comunicación con el vendedor puede durar varios días.|Alta|
|P\_V\_005|Login - Página Principal - Lista de órdenes de compra - Chat con el cliente |Usuario Vendedor|Recorrido como vendedor de iniciar sesión, seleccionar una órden de compra y mandar un mensaje a un cliente|Alta|
|P\_V\_006|Login - Página Principal - Página de Listado - Agregar un Coche|Usuario Gerente|Recorrido de cómo un gerente de una agencia agrega autos al catálogo|Alta|
|P\_V\_007|Login - Página Principal - Solicitar creación de usuario gerente|Usuario Grupo Automotriz|Recorrido que seguiría un usuario de grupo automotriz para solicitar la creación de un nuevo gerente de una agencia|Alta|
|P\_V\_008|Login - Página Principal - Aceptar la solicitud de dada de alta de un grupo automotriz|Usuario Administrador de la Plataforma|Recorrido como usuario administrador de la plataforma que se seguirá para aceptar la solicitud de dada de alta de un grupo automotriz|Alta|

#### Niveles de Prueba
**Pruebas Unitarias**

**Pruebas de Caja Negra**

PROPÓSITO: Las pruebas de caja negra nos permitirán evaluar el funcionamiento de nuestro software de manera que se sabe si se está cumpliendo con el requerimiento del que se basa.

ALCANCE: Se deben someter a pruebas las partes funcionales del sistema.

RESPONSABLES: Equipo de Pruebas/Desarrolladores.

MÉTODO: Pruebas de Caja Negra, específicamente utilizando entradas y salidas. Las baterías serían 5 positivas y 5 negativas evaluando funcionalidad y alcance del módulo que se prueba.

MOMENTO: Hacer pruebas al inicio de cada Sprint.


**Pruebas de Caja Blanca**

PROPÓSITO: Las pruebas de caja blanca nos permiten evaluar más de cerca el contenido y funcionamiento de la parte de software desarrollada, logrando así profundizar en la inspección del trabajo desarrollado.

ALCANCE: Se deben someter a pruebas las partes funcionales que hayan fallado pruebas anteriores.

RESPONSABLES: Equipo de Pruebas / desarrolladores.

MÉTODO Pruebas de Caja blanca, específicamente utilizando cobertura y camino básico según indique el caso.

MOMENTO: Hacer pruebas en caso de encontrar un resultado no deseado en las primeras evaluaciones.



**Pruebas de Integración**

PROPÓSITO: Las pruebas de integración evalúan la interacción de múltiples partes de un mismo sistema, de manera que debemos asegurar que el software que desarrollamos funciona completamente.

ALCANCE: Cada aspecto del software desarrollado debe ser sometido a estas pruebas.

RESPONSABLES: Equipo de Pruebas / desarrolladores

MÉTODO: Integración ascendente, Bottom-top.

MOMENTO: Cuando se tengan subfunciones o piezas de una funcionalidad más grande juntas en un sistema.



**Pruebas de Validación**

PROPÓSITO: Las pruebas de validación son necesarias para poder confirmar que el producto es el acordado y cumple con el funcionamiento descrito previamente.

ALCANCE: Todas las partes del producto a entregar debe ser validado en estas pruebas.

RESPONSABLES: Cliente (NDS) junto con el equipo de prueba.

MÉTODO: Compartir los avances de funcionalidades con el Socio-Formador semana con semana recibiendo retroalimentación.

MOMENTO: Durante la sesión semanal, avances de funcionalidades completas. Al igual que al final del periodo de todo el desarrollo del software.

#### Criterios de Entrada y Salida
De Caja Negra


|*Criterio de Entrada*|*Equipo de Prueba*|*Equipo Técnico*|*Notas*|
| :- | :- | :- | :- |
|- El equipo de cómputo es completamente funcional, y configuración.||||
|<p></p><p>- Los paquetes requeridos están instalados y disponibles en el equipo de computo.</p>||||
|- La librería de pruebas está disponible y funcional en el equipo de cómputo.||||
|- El ambiente de pruebas está configurado y funcional en el equipo de cómputo.|||<p></p><p></p>|

De Caja Blanca


|*Criterio de Entrada*|*Equipo de Prueba*|*Equipo Técnico*|*Notas*|
| :- | :- | :- | :- |
|- El equipo de cómputo es completamente funcional, y configuración.||||
|<p></p><p>- Los paquetes requeridos están instalados y disponibles en el equipo de computo.</p>||||
|- La librería de pruebas está disponible y funcional en el equipo de cómputo.||||
|- El ambiente de pruebas está configurado y funcional en el equipo de cómputo.||||
|- Se tiene acceso completo a todo el código fuente de la aplicación||||
|- Se tiene acceso a la documentación o código fuente de los paquetes requeridos.||||
|- Se tiene acceso a los esquemas de bases de datos de la aplicación.||||

Integración


|*Criterio de Entrada*|*Equipo de Prueba*|*Equipo Técnico*|*Notas*|
| :- | :- | :- | :- |
|- Las máquinas virtuales (GCP Compute Engine) están disponibles y corriendo.||||
|- Los paquetes requeridos están instalados y disponibles en las máquinas virtuales.||||
|- Las bases de datos están instanciadas, y con el esquema.  ||||
|- La librería de pruebas está disponible en el equipo de computo.||||
|- El ambiente de pruebas está configurado y corriendo.||||

Aceptación



|*Criterio de Entrada*|*Equipo de Prueba*|*Equipo Técnico*|*Notas*|
| :- | :- | :- | :- |
|- Las máquinas virtuales (GCP Compute Engine) están disponibles y corriendo.||||
|- Los paquetes requeridos están instalados y disponibles en las máquinas virtuales.||||
|- Las bases de datos están instaladas, y con el esquema.  ||||
|- La librería de pruebas está disponible en el equipo de computo.||||
|- El ambiente de pruebas está configurado y corriendo.||||

**Criterio de Salida**

Unitarias, Integración, Aceptación


|*Criterio de Salida*|*Equipo de Prueba*|*Equipo Técnico*|*Notas*|
| :- | :- | :- | :- |
|- Se probaron el 100% de las pruebas establecidas.||||
|- No existen problemas de nivel severo o crítico.||||
|- Los problemas de nivel severo o crítico se documentan, así como su solución o delegación.||||
|- El 100% de los componentes tiene un mínimo de 90% de índice de aprobación.||||
|- Todas las pruebas arrojan un resultado legible, que después es documentado como su resultado.||||
|- El equipo de cómputo, así como los componentes involucrados, sigue funcional después de la ejecución de las pruebas.||||


### No funcionales

**NO se realizarán pruebas de tipo no funcional.**
## Estáticas
Además de las pruebas dinámicas se llevarán a cabo pruebas estáticas, en donde no se necesita hacer una ejecución del código. Estas pruebas nos ayudarán a identificar errores y áreas de oportunidad en los documentos de descripción y diseño del producto. De igual manera nos ayudarán a obtener retroalimentación de varios stakeholders y hacer las correcciones pertinentes.

Las pruebas estáticas que se llevarán a cabo son las siguientes.

**Documento SRS**

*Prioridad: Alta*

En este documento se narra el análisis del problema y la solución planteada por el equipo. Haciendo énfasis en los requerimientos funcionales que se especificaron como soluciones a las necesidades y peticiones del cliente.

Este documento sirve para obtener retroalimentación del cliente y tener por escrito la serie de conclusiones obtenidas durante el análisis del problema y el planteamiento de la solución.

**Documento de Especificación de Pruebas**

*Prioridad: Alta*

Este documento pretende hacer una descripción a profundidad de las pruebas que serán llevadas a cabo en las diferentes fases del desarrollo del proyecto. Describe las pruebas tanto estáticas como dinámicas.

Este documento sirve de igual manera para obtener retroalimentación sobre la parte de pruebas del proyecto y como guía para cuando llegue el momento de su desarrollo.

**Manuales de Usuario (para todos los usuarios)**

*Prioridad: Media*

Se generarán manuales de usuario que describan los diferentes flujos y caminos que puede tomar un usuario en la plataforma. Estos flujos serán los flujos más relevantes como la compra de un coche, la dada de alta de un auto, etc. Es de vital importancia generar un manual de usuario por tipo de usuario (Final, Venedor, Gerente, Grupo Automotriz, Administrador de la Plataforma) y hacer estos manuales lo más gráficos y simples posible.

Para realizar estos manuales utilizaremos una herramienta llamada Tango, que se usa para generar guías paso a paso de alguna funcionalidad de la plataforma.



**Mockup de la interfaz gráfica**

*Prioridad: Alta*

Otra de las pruebas estáticas que realizaremos será la de un Mockup de la Interfaz de Usuario. Este mockup será un predecesor de la Interfaz Gráfica en donde se plantea el diseño de la plataforma y se incluyen los posibles recorridos que puede seguir el usuario.

Este documento será útil para obtener retroalimentación del usuario en cuestiones de experiencia de usuario y de apariencia física de la plataforma. Esta información nos ayudará a refinar la aplicación para ajustarla lo más posible a la comodidad del usuario.

**Documentación de las APIs**  

*Prioridad: Media*

Se generará documentación de todas las APIs que expongan los diferentes servicios que sean necesarios para el funcionamiento de la aplicación. Se realizarán usando la herramienta de OpenAPI para la definición de contratos.

Estos documentos tendrán la función de facilitar el desarrollo de la aplicación con la definición de los valores de entrada y salida esperados para el correcto funcionamiento de los servicios. De igual manera servirán para definir en primera instancia los diferentes endpoints.

# Manejo de Pruebas
En la presente sección de manejo de pruebas, se especificará a profundidad la manera en la que se llevarán a cabo las pruebas. Lo anterior incluye los roles involucrados en el proceso, sus tareas, las etapas en las que se harán las pruebas y toda la documentación necesaria para asegurar que se cumplan dichas pruebas y que todos los integrantes estén enterados. 
## Roles
Los roles que se considerarán son los siguientes: 


|**Rol**|**Detalle**|
| :-: | :-: |
|Project Manager|Es el responsable de mantener un seguimiento y la organización de las actividades a realizar por el equipo durante el proyecto, de manera que se realicen los entregables en tiempo y forma.|
|Líder de Pruebas|Es el responsable de las pruebas. Esto implica la planificación de pruebas, asignación de tareas, gestión de riesgos y cualquier otra actividad que involucre pruebas.|
|Analista de Negocios|Es el responsable de comprender las necesidades y procesos de la empresa y puede contribuir en el diseño de las pruebas considerando dichas necesidades.|
|Product Owner|Es el responsable de representar las necesidades de los clientes por lo que y en cerciorarse de que se cumplan los requerimientos.|
|Equipo de Desarrollo|Es el responsable de crear el código (y modificarlo) conforme a los requerimientos y de manera correcta. En su alcance, se encuentra la realización de pruebas unitarias.|
|Equipo de Pruebas|Es el responsable de ejecutar pruebas funcionales  y todo lo que implican. Se encarga de asegurarse de que la calidad del producto sea la adecuada y necesaria.|

## Pruebas por rol
### Dinámicas
En cuanto a la realización de las pruebas dinámicas, los roles que estarán involucrados y sus actividades principales son los siguientes: 


|Rol|Actividades|Pruebas en las que están involucrados|
| :- | :- | :- |
|Project Manager|<p>- Se cerciora de que las pruebas dinámicas tengan la calidad requerida.</p><p>- Se cerciora de que las pruebas dinámicas sean ejecutadas conforme al plan establecido.</p><p>- Monitorea el proceso de ejecución de pruebas </p><p>- Se comunica con el líder de pruebas para revisar avances.</p>|Caja Negra, Caja Blanca, Integración, Validación|
|Líder de Pruebas|<p>- Revisa que las pruebas sean ejecutadas correctamente y que se llenen de manera completa los formatos de documentación.</p><p>- Valida la calidad de las pruebas.</p><p>- Se asegura de que se siga el plan de pruebas.</p><p>- Gestiona al equipo de pruebas asignando tareas y revisando que se cumplan.</p><p>- Gestiona la documentación de defectos encontrados durante las pruebas.</p><p>- Comunica los avances a las otras entidades involucradas.</p><p>- Da el visto bueno para comenzar las pruebas.</p>|Caja Negra, Caja Blanca, Integración, Validación|
|Analista de Negocios y Product Owner|<p>- Validan que las pruebas cumplen con los intereses del cliente y del negocio.</p><p>- Tienen la posibilidad de revisar que las pruebas se realicen correctamente. </p><p>- Contribuyen a definir los criterios que se deben cumplir en cuanto a pruebas.</p>|Integración, Validación |
|Equipo de Desarrollo|<p>- Modifican el código en caso de ser necesario y resuelven los problemas técnicos que se deriven.</p><p>- Se encargan de integrar el código.</p><p>- Se encargan de asegurar que el código esté bien escrito y que se cumplan los estándares de calidad de código.</p><p>- Se aseguran que se entreguen los componentes en los tiempos establecidos.</p><p>- Revisan y ofrecen retroalimentación respecto al plan de pruebas.</p>|Informales, Caja Negra, Caja Blanca, Integración |
|Equipo de Pruebas|<p>- Realizan los casos de pruebas.</p><p>- Ejecutan y validan las pruebas.</p><p>- Identifican y reportan defectos derivados de las pruebas.</p><p>- Vuelven a ejecutar pruebas fallidas. </p><p>- Generan la documentación pertinente respecto a las pruebas.</p><p>- Comunican sus avances con el Líder de Pruebas.</p>|Caja Negra, Caja Blanca, Integración, Validación |


### Estáticas
En cuanto a las pruebas estáticas 


|Rol|Actividades|Pruebas en las que están involucrados|
| :- | :- | :- |
|Project Manager|<p>- Revisa y aprueba el plan de pruebas, la estrategia de pruebas y toda la documentación relacionada a la planeación de pruebas dinámicas. </p><p>- Se cerciora de que toda la documentación de las pruebas ejecutadas sea entregada. </p><p>- Se encarga de revisar el documento SRS</p>|Todas|
|Líder de Pruebas|<p>- Revisa que el equipo de pruebas realice correctamente su documentación.</p><p>- Se encarga de revisar y desarrollar correctamente el documento de plan de pruebas considerando las necesidades del cliente. </p><p>- Supervisa la generación de manuales de usuario, casos de prueba, entre otros. </p>|Documento SRS, Documento de Pruebas, Manuales de Usuario|
|Analista de Negocios y Product Owner|<p>- Corroboran que la documentación sea entendible y clara para permitir que los clientes puedan leerla.</p><p>- Revisan que la documentación esté completa y coincida con las necesidades del negocio y el cliente.</p>|Todas|
|Equipo de Desarrollo|<p>- Proveen retroalimentación respecto a las especificaciones técnicas de los documentos. </p><p>- Revisan los documentos y se encargan de que su código se alinee a los mismos.</p>|Documento SRS, Documento de Pruebas, Documentación de las APIs|
|Equipo de Pruebas|<p>- Generan el Documento de Especificación de Pruebas conforme a los requisitos establecidos. </p><p>- Contribuyen al diseño de pruebas.</p><p>- Documentan los resultados de las pruebas.</p><p>- Generan el reporte de pruebas.</p>|Documento SRS, Documento de Pruebas, Documentación de las APIs|

## Gantt

![Gantt de pruebas](/wiki/Docs/Media/docPruebasMedia/gantt_de_pruebas.png)
<!-- ![Flujo de pruebas](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/docPruebasMedia/gantt_de_pruebas.png) -->

## Estimación de Tiempo de Pruebas

![Estimación de Timepo de Pruebas](/wiki/Docs/Media/docPruebasMedia/estimacion_de_tiempo_de_pruebas.png)
<!-- ![Flujo de pruebas](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/docPruebasMedia/estimacion_de_tiempo_de_pruebas.png) -->

Para revisar el documento a detalle: <https://docs.google.com/spreadsheets/d/1vxVOYr__iR8I_0m2Jt67_S52jsVDHbXVsfs0EgEdXfY/edit?usp=sharing>

## Plantilla de Casos de Prueba y Ejecución

![Plantilla de Casos de Prueba y Ejecución](/wiki/Docs/Media/docPruebasMedia/plantilla_de_casos_de_prueba_y_ejecucion.png)
<!-- ![Flujo de pruebas](https://github.com/sebasgonvitec/qchau-software/blob/main/wiki/Docs/Media/docPruebasMedia/plantilla_de_casos_de_prueba_y_ejecucion.png) -->

Para revisar la plantilla a detalle: <https://docs.google.com/spreadsheets/d/1nTfMQTk2tjsDCuo7jzP076jQVGeXgG8upYA3rxw7K5Y/edit?usp=sharing>
## Plan de comunicación (Github)
En cuanto al plan de comunicación, se plantea el uso de GitHub para subir resultados de pruebas unitarias y mantener un seguimiento de lo que se ha realizado. GitHub es una herramienta de versiones por lo que todos los integrantes del equipo y aquellos involucrados en las pruebas, tendrán la posibilidad de visualizar cualquier cambio o avance que se realice. Adicional a Github, se utilizará Github Actions con el fin de lograr la automatización de notificaciones de manera que todos los miembros del equipo puedan recibir las actualizaciones en el momento en el que se realizan. 
## Riesgos


|**Riesgo**|**Probabilidad**|**Impacto**|**Plan de Mitigación**|
| :- | :- | :- | :- |
|Existe discrepancia de versiones entre las VMs implementadas.|Med.|Alto|La configuración de implementación debe definir un archivo de requerimientos con versiones específicas para todos los paquetes o librerías utilizadas.|
|Diferentes instancias de VMs arrojan distintos resultados en pruebas.|Med.|Alto |La configuración de implementación debe estar estandarizada y certificada por el Tech Lead.|
|Algún componente que requiera un servicio activo (bases de datos) no está disponible o deja de funcionar.|Alto|Med.|El equipo de desarrollo debe proveer un mantenimiento rutinario a estos componentes, así como proveer al equipo de pruebas con un *troubleshooting* de incidentes.|
|Los recursos de cómputo requeridos por el ambiente de pruebas superan los recursos actuales.|Med.|Alto|El Tech Lead debe ajustar el ambiente de pruebas a la capacidad de los recursos, o solicitar y justificar un incremento al dueño de producto.|
|Los métodos de pruebas no están bien configurados o construidos.|Bajo|Alto|El equipo de pruebas debe mantener revisiones en pareja (peer-reviews) sobre los métodos construidos.|
|Los métodos de pruebas no son reproducibles.|Med.|Alto|El Test Lead debe definir un estándar para la construcción de métodos para que todo el equipo de pruebas pueda ajustarse a.|
|La grabación de las pruebas es deficiente. |Alto|Alto|El método de grabación de pruebas debe ser estandarizado en el equipo, y debe ser probado antes de utilizarlo.|
|Las grabaciones de las pruebas no son identificables.|Alto|Alto|El nombramiento y estructura de grabaciones debe ser definido por el Test Lead y debe por lo mínimo incluir: la fecha de ejecución y el ID de la prueba ejecutada.|
|Las grabaciones de las pruebas están corruptas y no son distribuibles.|Med.|Alto|Deben existir copias de seguridad validadas de las grabaciones de la prueba, así como una validación de integridad del archivo antes de ser almacenado.|
|Las grabaciones de las pruebas son accesibles a personal sin autorización.|Bajo|Med.|Debe haber un estándar de autenticación en el almacén de la documentación de pruebas: definido por el Test Lead.|

Riesgos de Gestión de Proyectos

|**Riesgo**|**Probabilidad**|**Impacto**|**Plan de Mitigación**|
| :- | :- | :- | :- |
|Se inicia una fase de pruebas sin haber acabado la anterior.|Bajo|Alto|Establecer el liderazgo del Test Lead y requerir su aprobación para cualquier inicio o fin de fase de pruebas.|
|La retroalimentación del equipo de desarrollo es deficiente.|Med.|Med.|Establecer un estándar de reporte para el equipo de desarrollo, que cubra las necesidades del equipo de pruebas.|
|La documentación del equipo de pruebas es deficiente.|Med.|Alto|Establecer un estándar de reporte para el equipo de pruebas, que cubra las necesidades del equipo de desarrollo.|
|El equipo de desarrollo no recibe peticiones de cambios, a pesar de existir.|Bajo|Alto|El liderazgo del Tech Lead debe confirmar con el equipo de pruebas si existe alguna petición de cambio.|
|El equipo de pruebas no recibe confirmación de cambios, a pesar de haberse reportado.|Bajo|Alto|El liderazgo del Test Lead debe confirmar rutinariamente con el equipo de desarrollo si existe alguna actualización en un cambio.|


# Casos de Prueba
Los casos de prueba se realizarán durante el despliegue.
# Pruebas
Las pruebas se realizarán durante el despliegue.
# Ambiente de pruebas
El ambiente de pruebas local consistirá en un mínimo de un ambiente de Windows 10, un intel i5 2.4 GHz, y 8GB RAM 1333MHz, al igual que Chrome versión 80 como mínimo. El funcionamiento de la aplicación web primero será probado de manera local antes del despliegue en servicios de la nube. Todos los testers tendrán acceso a la misma versión de la base de datos y todos los programas necesarios.
# Conclusiones
El presente documento demuestra la planeación de pruebas para el aplicativo propuesto. Este documento detalla la implementación de todas las pruebas a ejecutar sobre el aplicativo: desde su concepción, ejecución, y documentación.

Las pruebas detalladas tienen pensado ejecutarse durante el desarrollo del aplicativo propuesto: para poder identificar, documentar, exhibir y corregir errores que surjan en el ambiente de desarrollo - así como para identificar riesgos en el diseño o implementación y poder emplear una solución.

Estas pruebas serán ejecutadas por un equipo definido de pruebas - que trabaja de la mano con el equipo de desarrollo - esta comunicación entre equipos asegura un flujo de pruebas correcto y eficiente.

La implementación exitosa de este documento será de gran beneficio para el equipo de desarrollo, el cliente y últimamente para el usuario: asegurando así la sustentabilidad y operatividad del aplicativo - que se espera, sea un gran producto.

