# Test Plan

## Qchau

---

### Revision and Sign Off Sheet

**Document History** - To maintain a list of changes being made

| Version | Date | Author | Description of Change |
|---------|------|--------|-----------------------|
<!-- | 1 | 10/03/2022 | Leonardo Ramírez Landa | Draft |
| 2 | 11/03/2022 | Ian Seidman | Introduction, Test Objectives | 
| 3 | 11/03/2022 | Ignacio Joaquín Moral | Scope, Levels of testing, Test Acceptance criteria |
| 4 | 11/03/2022 | Tomás Díaz Servín | Milestones List |
| 5 | 12/03/2022 | Leonardo Ramírez Landa | Test Strategy |
| 6 | 12/03/2022 | Leonardo Ramírez Landa, Ignacio Joaquín Moral | Execution Strategy |
| 7 | 13/03/2022 | Leonardo Ramírez Landa | Communications Plan and Team Roster |
| 8 | 13/03/2022 | Ian Seidman | Test Risks and Mitigation Factors, Test Environment |
| 9 | 14/03/2022 | Ricardo Alonso Arostegui | Test Execution Process, Activities Cronogram |
| 10 | 15/03/2022 | Tomás Díaz Servín | Conclusions |
| 11 | 16/03/2022 | Ignacio Joaquin Moral | Updated Table of Contents | -->

---

**Approvers List** - To track who has reviewed and signoff on the Test plan

| Name | Role | Approver / Reviewer | Approval / Review Date |
|------|------|---------------------|------------------------|
| Gilberto Echeverria | Instructor | 

**Reference Documents** - Clearly mark the document used as an input to create the test plan (todos los
documentos adicionales para crear este, cronograma, excel, etc)

| Version | Date | Document Name |
|---------|------|---------------|
| 1.0 | 14/3/2022 | Test specification document |
 
---

## Table of Contents

1. [INTRODUCCIÓN](#1-introducción)

    1.1 [Propósito](#11-propósito)

    1.2 [Descripción del Proyecto](#12-descripción-del-proyecto) 

    1.3 [Audiencia](#13-audiencia)

2. [ESTRATEGIA DE PRUEBAS](#2-estrategia-de-pruebas)

    2.1 [Descripción de Pruebas](#21-descripción-de-pruebas) 

    2.2 [Objetivos de Prueba](#22-objetivos-de-las-pruebas)

    2.3 [Suposiciones de Prueba](#23-suposiciones-de-pruebas)

    2.4 [Objetos de Prueba](#24-objetos-de-prueba)

    2.5 [Alcance](#25-alcance)

    2.6 [Niveles de Pruebas](#26-niveles-de-pruebas) 

    2.7 [Criterio de Aceptación de las Pruebas](#27-criterio-de-aceptación-de-las-pruebas)
    
    2.8 [Pruebas del Entregable](#28-pruebas-del-entregable)

    2.9 [Lista de Hitos](#29-lista-de-hitos)

    2.10 [Estimación del Esfuerzo de Prueba](#210-estimación-del-esfuerzo-de-prueba)

3. [ESTRATEGIA DE EJECUCIÓN](#3-esrategia-de-ejecución) 

    3.1 [Criterio de Entrada y Salida](#31-criterios-de-entrada-y-salida) 

4. [PROCESO DE GESTIÓN DE PRUEBAS](#4-proceso-de-gestión-de-pruebas)

    4.1. [Prueba de Proceso de Ejecución](#41-prueba-de-proceso-de-ejecución)

    4.2. [Probar Riesgos y Factores de Mitigación](#42-prueba-de-riesgos-y-factores-de-mitigación)

    4.3. [Plan de Comunicación y Nómina del Equipo](#43-plan-de-comunicación-y-nómina-del-equipo)

    4.3.1. [Espectativas de Rol](#431-espectativas-de-rol)

    • [Gestión de Proyecto](#gestión-de-proyecto)

    • [Planificación de Pruebas (Test Lead)](#planificación-de-pruebas-test-lead)

    • [Equipo de Pruebas](#equipo-de-pruebas)

    •   [Líder de Pruebas](#líder-de-pruebas)

    • [Equipo de Desarrollo](#equipo-de-desarrollo)

    4.4.[Cronograma de Actividades](#44-cronograma-de-actividades) 

5. [AMBIENTE DE PRUEBAS](#5-ambiente-de-pruebas)
6. [PRUEBAS](#6-pruebas)
7. [CONCLUSIONES](#7-conclusiones)
8. [APROBACIONES](#8-aprobaciiones)

---

## 1. Introducción
### 1.1. Propósito

El objetivo del presente documento, es proveer una propuesta respecto a las pruebas de software necesarias para el desarrollo y la funcionalidad correcta de la aplicación web de adquisión de autos. Estas contribuirán en la creación de un producto con un control de calidad alto por lo que serán detalladas y argumentadas en este escrito. 

En cuanto al plan de pruebas que se realizará, este incluirá la especificación de elementos de software que serán probados, el nivel y la secuencia en la que serán probados, los criterios de salida y la manera en la que se aplicará la estrategia en el ambiente de pruebas. Junto con lo anterior, se considerarán los siguientes puntos:
- Lo que está dentro y fuera del alcance
- Supuestos
- Roles y responsabilidades del equipo QA
- Herramientas
- Entregables
- Gestión de Defectos
- Riesgos
- Calendario

### 1.2. Descripción del Proyecto

El proyecto que será desarrollado por Qchau Software se trata de una solución para grupos automotices y compardores de autos en donde se permitirá digitalizar una parte del proceso de compra, evitando visitas excesivas a las agencias. Dicha solución está planteada como una aplicación web que permitirá a los usuarios interactuar con el agente, explorar distintas opciones de autos, obtener cotizaciones estimadas automáticamente, comparar autos, subir y editar sus documentos, solicitar pruebas de manejo y mantener un seguimiento adecuado (con la misma calidad de atención que en una agencia tradicional) de sus compras. 

La aplicación beneficiará a los clientes de las agencias ya que les ahorrará tiempo, les proporcionará opciones de distintas marcas y agencias (con distintos planes de financiamiento) en una misma plataforma, y les permitirá tener una visión más clara de lo que quieren. Asimismo, beneficiará a las agencias y grupos automotrices, dándoles un espacio en el que tendrán visibilidad, la posibilidad de agilizar ciertos procesos (como lo es el de la entrega de documentos del cliente) para poder atender a más clientes y la posibilidad de obtener ciertas estadísticas que les podrán ayudar a analizar sus ventas. 


### 1.3. Audiencia

El presente documento estará a la vista de los encargados del diseño de pruebas (quienes podrán cambiar ciertos componentes), los desarrolladores de software (quienes ejutarán las pruebas que se mencionarán), del Product Owner (quien tendrá una visión de la perspectiva del cliente y las necesidades de calidad), del Project Manager (quien supervisará que se lleven a cabo correctamente los casos de prueba) y de cualquier entidad involucrada en el proyecto (quienes podrán revisar que se cumplan los estándares del proyecto que se requieren). 

En este caso, los desarrolladores utilizarán el documento como una guía para la ejecución adecuada de las pruebas, para la comprensión de los elementos relevantes a probar, y para la aclaración del proceso en general. 

## 2. Estrategia de Pruebas
### 2.1. Descripción de las Pruebas
Para asegurar la calidad y funcionalidad de nuestro producto, se llevarán a cabo diferentes tipos de pruebas en diferentes etapas del desarrollo del proyecto. Primero, conforme el desarrollo vaya avanzando se harán pruebas informales sobre los componentes que se estén trabajando. Solo unas cuantas de estas pruebas informales serán documentadas. 

Igualmente durante el proceso de desarrollo se llevarán a cabo pruebas unitarias en cada uno de los componentes del software. Entiendase por componentes a segmentos del código que cumplan una funcionalidad crítica. Con estas procederemos de la siguiente manera:
1. Se llevan a cabo pruebas de caja negra, validando que las entradas y salidas sean correctas. Para estas se utilizarán pruebas de cobertura.
2. Una vez se cumpla esta cobertura, el componente quedará listo.
3. En caso de que el componente no cumpla con las especificaciones, se procederá a realizar pruebas de caja blanca, validando que el componente cumpla con las especificaciones de usuario. Para estas pruebas se utilizarán pruebas de Casos de Uso.

Después de este proceso de pruebas unitarias se pasará a hacer pruebas de integración en donde se definirán por lo menos 2 caminos que representen una funcionalidad de cada usuario. Estos caminos estarán conformados por varios de módulos probados anteriormente.

Por último, se harán pruebas de aceptación en donde ciertos candidatos cumplirán la función del usuario final y probaran el sistema. De estas pruebas obtendremos información de retroalimentación con la que podremos mejorar el sistema y sobre todo, asegurarnos de que los caminos que decida tomar el usuario cumplan con su funcionalidad.

Todas las pruebas que se realicen -a excepción de las informales- serán documentadas en la sección de pruebas de este documento.
<!-- NOTA: Ver si agregar pruebas de rendimiento o algún otro tipo de pruebas -->

### 2.2. Objetivos de las Pruebas
El objetivo de estas pruebas es validar la funcionalidad de cada uno de los requerimientos funcionales del sistema y obtener retroalimentación del usuario para hacer las modificaciones necesarias y mejorar su experiencia. Algunas de las acciones fundamentales que se estarán midiendo son las siguientes:
- Funcionalidad de los filtros de búsqueda.
- Correcto almacenamiento de archivos de los usuarios.
- Comunicación entre el cliente y el vendedor en tiempo real.
- Experiencia de usuario y usabilidad de la plataforma.
- Estabilidad del producto.

### 2.3. Suposiciones sobre Pruebas

- Se omitirán pruebas de humo.
- Todas las pruebas se llevarán a cabo en el mismo ambiente.
- Se realizarán limitadas pruebas no funcionales -de estrés, escalabilidad, etc.- debido al tiempo y recursos con los que se cuenta.
- Las mismas pruebas deben de tener los mismos resultados.
- Los casos de prueba deben de ser aptos para probar los componentes.
- Los datos utilizados en los casos de prueba deben de ser accesibles.
- Si el ambiente de pruebas idóneo no se encuentra disponible, se utilizará un ambiente lo más parecido posible para las pruebas.
- Se probarán todas las funciones individuales.
- Únicamente se llevarán a cabo pruebas de caja blanca si en cualquier etapa de pruebas se obtiene un resultado no deseado.
- Se documentarán todas las pruebas menos las informales.
- Se llevará a cabo una revisión de los entregables de cada prueba.
- Todos los casos de prueba deberán ser revisados con anterioridad.

### 2.4. Objetos de Prueba
**Todos los Usuarios**
1. Funcionalidad de Login.
2. Funcionalidad de Registro de Usuarios (cualquier usuario).
3. Funcionalidad de almacenamiento y descarga de archivos.
4. Funcionalidad de modificación de información del perfil

**Usuario Final**
1. Funcionalidad de filtros de catálogo.
2. Funcionalidad de comunicación con el vendedor.
3. Funcionalidad de comparación de autos.
4. Funcionalidad de cotización automática.
5. Funcionalidad de pago.

**Usuario Vendedor**
1. Funcionalidad de asignación de ordenes.
2. Funcionalidad de visualización de compras activas.
3. Funcionalidad de comunicación con el cliente.

**Usuario Gerente**
1. Funcionalidad de registro de autos.

**Usuario Administrador de Grupo Automotriz**
1. Funcionalidad de registro de agencias.
2. Funcionalidad de obtención de estadísticas.

**Usuario Administrador de Plataforma**
1. Funcionalidad de registro de agencia o grupo automotriz.
2. Funcionalidad de obtención de estadísticas de la plataforma.

<!-- 
### 2.5. Scope 
Creo que esta sección se puede omitir, el diseño de los diferentes casos de prueba se hará después
-->

### 2.6. Niveles de Pruebas

#### ■ Pruebas Unitarias

**PROPOSITO**: Las pruebas unitarias nos permitirán evaluar el funcionamiento de nuestro software, de manera que podemos medir si los requerimientos funcionales están siendo cumplidos o no.

**SCOPE**: Se deben someter a pruebas las partes funcionales del sistema.

**TESTERS:** Equipo de Pruebas.

**METHOD:** Pruebas de Caja Negra, especificamente utilizando entradas y salidas. 

**TIMING:** Hacer pruebas al inicio de cada Sprint.

### ■ Pruebas de Integración

**PURPOSE:** Las pruebas de integración evaluan la interaccion entre dos partes de un mismo sistema, de manera que debemos asegurar que el software que desarrollamos funciona en su completud.

**SCOPE:** Cada aspecto del softwre desarrollado debe ser sometido a estas pruebas.

**TESTERS:** Equipo de Pruebas

**METHOD:** Integración ascendente, Bottom-top.

**TIMING:** Cada vez que se tengan subfunciones o piezas de una funcionalidad más grande.

### ■ Pruebas de Validación

**PURPOSE:** Las pruebas de validación son necesarias para poder confirmar que el producto es el acordado y de su agrado.

**SCOPE:** Todas las partes del productoma entregar debe ser validado en estas pruebas.

**TESTERS:** Cliente (NDS) junto con el equipo de prueba.

**METHOD:** Compartir los avances de funcionalidades con el Socio-Formador semana con semana recibiendo retroalimentación.

**TIMING:** Durante la sesión semanal, avances de funcionalidades comlpetas.

### ■ Pruebas del Sistema

**PURPOSE:** Las pruebas del sistema evaluan el funcionamiento del software posteriormente a la ejecución de las pruebas unitarias y de integración. 

**SCOPE:** Una vez que este hecho todo el sistema, este deberá ser sometido a la prueba en cuestión.

**TESTERS:** Equipo de Pruebas.

**METHOD:** Se realizarán ´ruebas de entrada y salida (Caja negra), haciendo un recorrido por el sistema. 

**TIMING:** Al finalizar la validación e integración, esta prueba concluye la evaluación.

## 2.7. Criterio de Aceptación de las Pruebas
### Pruebas Unitarias

● Login Functionality: This functionality should never fail. All tests must either deliver
the correct user and home page, or it should send an error message displaying that
the user doesn’t exist.

- Enrolamineto y Login de Usuario Final: Esta parte del sistema es escencial para el usuario pueda realizar acciones signifactivas dentro de la plataforma, y pued cumplir el proposito comercial del sistema.

● Video Recording: This functionality should, at the very minimum, record the entire
screen and audio of the call. It also needs to start and end automatically, depending
on the Amazon Connect condition.

● Video Saving: The video needs to be saved to the correct database, and needs to be
retrievable from said location. Name, time, and datetime should be saved
automatically.

● Analysis Functionality: There should be different options for analysis. Rating, day of
the week, monthly view, section, etc. The display should show problematic ratings
with a different color from the rest.

### Pruebas de Integración

● Login Functionality: If it’s an Agent, only give access to the video recording
functionality. If it’s an Administrator or a Supervisor, give access to their respective
analysis functionality. All users will be able to access their respective home page and
an “Inform of an Error” section.

● Video Recording: Only Agents can access this functionality.

● Video Saving: Automatically after ending a call. Needed to give the rating of the call
and section. Name of the agent recorded automatically.

● Analysis Functionality: Only accessible from Administrator or Supervisor account.
Can delete old videos. Needs to connect to the database and be able to retrieve
videos. Rating based on the Video Saving functionality. Administrators can only see
their own Agents’ calls, and Supervisors can see all of their company’s calls, but not
others.

### Pruebas de Validación

● The clients and stakeholders are satisfied with the functionalities.

### Pruebas del Sistema

● The basic flow is able to be completed in one run, from log in to log out. Agents are
able to log in, record a video, save it, and log out; while Administrators and
Supervisors can log in, see their analysis, and log out.

## 2.8. Pruebas del Entregable
| S.No. | Deliverable Name | Author | Reviewer |
|-------|------------------|--------|----------|
| 1. | Test Plan | Test Lead | Project Manager/Business Analyst’s |
2. Unit Test Cases Test Team Business Analyst’s
Sign off
3. Formal Technical Review Test Lead Project Manager/
Business Analyst’s
4. Inspection Test Lead Business Analyst’s
Sign off
3. Examples of Successful Tests Test Team Test Lead/ Business
ANalyst’s Sign off
4. Logging Defects in DataMatics Test Team Test Lead/
Programming
Lead(Vijay)
5. Daily/weekly status report Test Team/ Test Lead Test Lead/ Project
Manager
6. Test Closure report Test Lead Project Manager

## 2.9. Lista de Hitos
The milestone list is tentative and may change due to below reasons

a) Any issues in the System environment readiness

b) Any change in scope/addition in scope

c) Any other dependency that impacts efforts and timelines

|  | Tipo de Prueba | Ejemplo de Prueba (SUT) | Dependencias (DOC) |
|--|-----------|--------------------|------------------|
| 1 | Unit Testing | DB Connection Test | Completed database. |
| 2 | Unit Testing | Call Recording |  | 

<!-- 3
Integration Testing
Agent call recording
successfully saves
automatically to the database
after completion of call.
Call recording is successful,
the database completely
works as well as APIs that
trigger recording as well as
saves it.
4 Integration Testing Supervisor has access to only
the recordings of his team.
Call recording is successful,
the database completely
works as well as APIs that
trigger recording as well as
saves it. Supervisor is also
able to successfully login.
5 Validation Testing Design interface is up to client
standards.
Interface Design
Completed
6 Validation Testing System is complete and works
to customers' standards.
Software is completed.
7 System Testing Agent is able to login,
recording begins
automatically when a call is
received which is then saved
automatically to the database
at the completion of the call.
Complete Database
Complete API connections
between Database and
Front End
Complete Agent Front End
8 System Testing Administrator has access to all
recordings in the database
and is able to filter them
based on tags, agent and
performance score.
Complete Database
Complete API connections
between Database and
Front End
Complete Administrator
Front End -->

Testing generally is not carried out in one cycle. Based on the testing scope, we can
estimate how much time it takes and establish the time lines as you can see in the below
embedded excel sheet

---

## 2.10. Estimación del Esfuerzo de Prueba

This document lists out all the activities that have to be performed by the QA team and estimates how
many man-hours each activity is going to take.

QA DEPARTMENT IMAGE

The document can be visualized here and in the appendix
Note: this estimate is for the TCOE team only Testing Schedule

# 3. ESTRATEGÍA DE EJECUCIÓN

## 3.1. Criterios de Entrada y Salida

**Criterio de Entrada**

Unitarias


|*Criterio de Entrada*|*Equipo de Prueba*|*Equipo Técnico*|*Notas*|
| :- | :- | :- | :- |
|- El equipo de cómputo es completamente funcional, y configuración.||||
|<p></p><p>- Los paquetes requeridos están instalados y disponibles en el equipo de computo.</p>||||
|- La librería de pruebas está disponible y funcional en el equipo de cómputo.||||
|- El ambiente de pruebas está configurado y funcional en el equipo de cómputo.||||

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



# 4. PROCESO DE GESTIÓN DE PRUEBAS
## 4.1. Prueba de Proceso de Ejecución
. Once all Test cases are approved and the test environment is ready for testing,
testers will start an exploratory test of the application to ensure the application is
stable for testing.
i. The test lead will assign test cases to each tester.
ii. Developers will be in charge of the informal reviews, but will be assisted by testers in
order to achieve better results.
iii. Test lead will be in charge of the technical development review, and will be assisted by
the testers.
iv. The people in charge of the development inspections will be: Project Manager,
Business Analyst, Development Lead, Testing Lead.
v. Testers to ensure necessary access to the testing environment, Docs for updating test
status and raising defects. If any issues, will be escalated to the Test Lead and in turn
to the Project Manager as escalation.
vi. If any showstopper occurs during exploratory testing will be escalated to the
respective development for fixes.
vii. Each tester performs step by step execution and updates the execution status. The
tester enters Pass or Fail Status for each of the steps directly in Docs.
viii. Tester will prepare a Run chart with day-wise execution details
ix. If any failures, defects will be raised as per severity guidelines in Docs detailing steps
to simulate along with screenshots if appropriate.
x. Daily Test execution status as well as Defect status will be reported to all stakeholders.
xi. Testing team will participate in defect triage meetings in order to ensure all test cases
are executed with either pass/fail category.
xii. If there are any defects that are not part of steps but could be outside the test steps,
such defects need to be captured in Docs and map it against the test case level or at
the specific step that issue was encountered after confirming with Test Lead.
xiii. This process is repeated until all test cases are executed fully with Pass/Fail status.
xiv. During the subsequent cycle, any defects fixed applied will be tested and results will be
updated in Docs during the cycle.
As per Process, final sign-off or project completion process will be followed

## 4.2. Prueba de Riesgos y Factores de Mitigación
| Riesgo | Prob. | Impacto | Plan de Mitigación|
|------|-------|--------|-----------------|

--- 

## 4.3. Plan de Comunicación y Nómina del Equipo
### 4.3.1 Espectativas de Rol
Para el proceso de pruebas que se realizará, se tendrán los siguientes roles:

| Rol | Detalle |
|-----|---------|
| Project Manager | Es el responsable de mantener un seguimiento y la organización de las actividades a realizar por el equipo durante el proyecto, de manera que se realicen los entregables en tiempo y forma. |
| Líder de Pruebas | Es el responsable de las pruebas. Esto implica la planificación de pruebas, asignación de tareas, gestión de riesgos y cualquier otra actividad que involucre pruebas. |
| Business Analyst | Es el responsable de comprender las necesidades y procesos de empresa y puede contribuir en el diseño de las pruebas considerando dichas necesidades. |
| Product Owner | Es el responsable de representar las necesidades de los clientes por lo que  y en cerciorarse de que se cumplan los requerimientos. |
| Equipo de Desarrollo | Es el responsable de crear el código (y modificarlo) conforme a los requerimientos y de manera correcta. En su alcance, se encuentra la realización de pruebas unitarias. |
| Equipo de Pruebas | Es el responsable de ejecutar pruebas funcionales, no funcionales y todo lo que implican. Se encarga de asegurarse de que la calidad del producto sea la adecuada y necesaria. |

--- 

### Gestión de Proyecto

● Project Manager: reviews the content of the Test Plan, Test Strategy and Test Estimates
signs off on it.

### Planificación de Pruebas (Test Lead)

● Ensure entrance criteria are used as input before starting the execution.
● Develop test plans and the guidelines to create test conditions, test cases, expected
results and execution scripts.
● Provide guidelines on how to manage defects.
● Attend status meetings in person or via the conference call line.
● Communicate to the test team any changes that need to be made to the test
deliverables or application and when they will be completed.
● Provide on premise or telecommute support.
● Provide functional (Business Analysts) and technical team to test team personnel (if
needed).

### Equipo de Pruebas
● Develop test conditions, test cases, expected results, and execution scripts.
● Perform execution and validation.
● Identify, document and prioritize defects according to the guidance provided by the Test
lead.
● Re-test after software modifications have been made according to the schedule.
● Prepare testing metrics and provide regular status.

### Líder de Pruebas
● Acknowledge the completion of a section within a cycle.
● Give the OK to start the next level of testing.
● Facilitate defect communications between testing team and technical / development
team.

### Equipo de Desarrollo
● Review testing deliverables (test plan, cases, scripts, expected results, etc.) and provide
timely feedback.
● Assist in the validation of results (if requested).
● Support the development and testing processes being used to support the project.
● Certify correct components have been delivered to the test environment at the points
specified in the testing schedule.
● Keep the project team and leadership informed of potential software delivery date slips
based on the current schedule.
● Define processes/tools to facilitate the initial and ongoing migration of components.
● Conduct first line investigation into execution discrepancies and assist test executors in
creation of accurate defects.
● Implement fixes to defects according to schedule.

---

### 4.4. Cronograma de Actividades

---

5. AMBIENTE DE PRUEBAS
El ambiente de pruebas local consistirá en un mínimo de un ambiente de windows 10 version, un intel i5 2.4 GHz, 8GB RAM 1333MHz, al igual que chrome versión 80 como mínimo. EL funcionamiento de la aplicacion web primero sera probado de manera local antes del despliegue en servicios de la nube.
Todos los testers tendran acceso a la misma version de la base de datos y todos los programas necesarios.

---

# 6. PRUEBAS

---

# 7. CONCLUSIONES


El presente documento demuestra la planeación de pruebas para el aplicativo propuesto. Este documento detalla la
implementación de todas las pruebas a ejecutar sobre el aplicativo: desde su concepción, ejecución, y documentación.

Las pruebas detalladas tienen pensado ejecutarse durante el desarrollo del aplicativo propuesto: para poder
identificar, documentar, exhibir y corregir errores que surjan en el ambiente de desarrollo - así como para identificar riesgos en el diseño o implementación y poder emplear una solución.

Estas pruebas serán ejecutadas por un equipo definido de pruebas - que trabaja de la mano con el equipo de desarrollo - esta comunicación entre equipos asegura un flujo de pruebas correcto y eficiente.

La implementación exitosa de este documento será de gran beneficio para el equipo de desarollo, el cliente y 
últimamente para el usuario: asegurando así la sustentabilidad y operabilidad del aplicativo - que se espera, sea un 
gran producto.

# 8. APROBACIIONES
The Names and Titles of all persons who must approve this plan.

| Firma: |  |
|------------|--|
| **Nombre:** |  |
| **Rol:** |  |
| **Fecha:** |  |

| Firma: |  |
|------------|--|
| **Nombre:** |  |
| **Rol:** |  |
| **Fecha:** |  |
Signature:
Name:
Role:
Date:
Signature:
Name:
Role:
Date:
