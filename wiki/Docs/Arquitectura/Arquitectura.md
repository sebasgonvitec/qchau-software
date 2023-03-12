# Arquitectura

El presente documento tiene como objetivo mostrar una propuesta de diseño de arquitectura para la aplicación de adquisición de autos que será propuesta a NDS Cognitive Labs. La propuesta de arquitectura, fue diseñada considerando las distintas necesidades planteadas por el cliente (NDS), el uso de la nube y la propuesta de crear una aplicación web. A continuación, se muestran y se explican las características importantes de la arquitectura. 

---
## _Arquitectura General_
El siguiente diagrama, muestra la arquitectura de una manera resumida y sin considerar posibles servicios de nube (tales como los de Google Cloud o AWS). 

![Diagrama general de arquitectura](https://github.com/sebasgonvitec/qchau-software/blob/64dc167b2890f2f646820183c583b56852540ea3/wiki/Docs/Arquitectura/Diagrama_ArchCloud.png)

Es posible notar en el diagrama, el uso de distintas tecnologías en la nube. En primer lugar, se tienen los servidores web que servirán para correr la aplicación junto con el servidor de aplicación (lógica) de manera que pueda ser posible escalar tanto horizontal (agregando más servidores) como verticalmente (agregando recursos a los servidores). 

Asimismo, se agregaron bases de datos tanto relacionales como no relacionales considerando que parte de los datos puede ser altamente flexible (por lo tanto escalabes) mientras otros datos son más fijos y se relacionan altamente entre ellos. Se plantea adicionalmente, un servicio que contenga copias de seguridad de los datos para protegerlos en caso de que algo suceda a las bases de datos.

En cuanto a el análisis de datos, se planea tener seguimiento de funciones que responden a eventos (colección y warehouse) acompañados de un servicio de inteligencia de negocios para el análisis. 

Considerando los servicios de mensajería se plantea agregar al servidor de la aplicación servicios tanto de correo electrónico como de chat. 

Haciendo referencia a la salida al público, se planea tener un balanceador de carga con el fin de distribuir el tráfico a los servidores. De igual manera, se planea utilizar un servicio de firewall para monitorear el tráfico de la red y un servicio de autenticación de usuarios para la administración de identidad de los usuarios. Se quiere utilizar el servicio de CDN para, junto con un cache, alojar ahí los medios que se utilizarán en la plataforma. Finalmente, se tiene un proveedor de DNS para resolver los dominios de los sitios web a usar. 

Asimismo, se planea utilizar una implementación orientada a servicios (muy parecida a la de microservicios, pero con bases de datos compartidas entre servicios), se consideran los mismos dadas las múltiples funcionalidades y la complejidad del sistema requerido. El uso de una arquitectura orientada a servicios contribuirá a la eficiencia de desarrollo puesto a que facilita que muchas personas trabajen en distintos módulos al mismo tiempo, en la diversidad de tecnologías permitiendo utilizar las mejores dependiendo de la funcionalidad y haciendo que tanto la escalabilidad, el mantenimiento y las pruebas sean más simples dado lo seccionado que se vuelve. 

Para revisar la Especificación de Requerimientos de Software (en donde también se explica la presente arquitectura, hacer click [aquí](https://github.com/sebasgonvitec/qchau-software/blob/64dc167b2890f2f646820183c583b56852540ea3/wiki/Docs/SRS.md)
