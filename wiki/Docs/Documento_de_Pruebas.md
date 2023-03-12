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

1. [INTRODUCTION]()

    1.1 [Purpose]()

    1.2 [Project Overview]() 

    1.3 [Audience]()

2. [TEST STRATEGY]()

    2.1 [Test Description]() 

    2.2 [Test Objectives]()

    2.3 [Test Assumptions]()

    2.4 [Test Objects]()

    2.5 [Scope]()

    2.6 [Levels of Testing]() 

    2.7 [Test Acceptance Criteria]()
    
    2.8 [Test Deliverables]()

    2.9 [Milestone List]()

    2.10 [Test Effort Estimate]()

3. [EXECUTION STRATEGY]() 

    3.1 [Entry and Exit Criteria]() 

4. [TEST MANAGEMENT PROCESS]()

    4.1. [Test Execution Process]()

    4.2. [Test Risks and Mitigation Factors]()

    4.3. [Communications Plan and Team Roster]()

    4.3.1. [Role Expectations]()

    • [Project Management]()

    • [Test Planning (Test Lead)]()

    • [Test Team]()

    •   [Test Lead]()

    • [Development Team]()

    4.4.[ Activities Cronogram]() 

5. [TEST ENVIRONMENT]()
6. [TESTS]()
7. [CONCLUSIONS]()
8. [APPROVALS]()
---

## 1. INTRODUCTION
### 1.1. Purpose
This document will describe the reasoning behind the testing approach and general planning for the
development of Datamatics. In particular it includes:

● Testing Strategy for each aspect of the application and why it was chosen

● The application’s scope and reach

● Acceptance criteria for each aspect of the application and its tests

● The execution strategy describing how each test will transpire and what will be done to
identify and document defects, along with the implementation of fixes

● The test management plan to help understand what to do in the case of test failure, along
with a schedule to maintain control over when specific tests should be held and repeated
if necessary

● Scenario description to fully understand the members of the testing team, their role in the
process and what equipment and software will be used for testing purposes

### 1.2. Project Overview
Datamatics is a web application that provides a call center the unique tool to keep track of their agents’
calls and easily identify their key characteristics. This includes the client satisfaction of a call, its
duration, and the topic discussed.
It is especially useful for a call center to train its agents through previously successful calls, along with
easily identifying agents who are doing well along with those who might need some help.
Agents will not have to worry about intrusive software stopping their work, as Datamatics works in the
background and only requires opening on startup, while their supervisors will be able to enjoy their
personalized dashboard showcasing statistical information from all their agents, along with the ability
to view their recordings with ease.

### 1.3. Audience
-  The document will be viewed primarily by the project team members, along with the stakeholders
and other such participants

i. The document is a guideline for the project team members, providing the tasks they should be
conducting for the purpose of successful testing and development

ii. The project manager will use the document to adhere to the schedule agreed upon, along with
constant monitoring of progress based on what is expected and written below. They are
accountable for the results and performance of each test

iii. The stakeholders or their representatives may monitor the document to ensure the development is
adhering to the s requirements and their interests

iv. The development team must ensure that the test plan and deliverables stated within the document are
the same that were previously agreed upon during the design phase, along with fixing any defects of
failed tests that are stated

v. The Business analyst will provide inputs on functional changes and ensure the stakeholders are
informed and agree with any potential changes

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

### 2.6. Levels of Testing

#### ■ Unit Testing

**PURPOSE**: Unit testing will allow each section of the software to be fully tested. Allows the
testers to know whether a requirement will be fulfilled.

**SCOPE**: All sections of the software will be unit tested.

**TESTERS:** Testing team.

**METHOD:**User stories, use cases, and input-output sections. Should the testing fail, white box
will be implemented

**TIMING:** at the beginning of each cycle.

#### ■ Integration Testing

**PURPOSE:** Integration testing will allow testers to know if the software works together. In this
case, for example, does the video finish recording, and the agent can rate and grade, then the
video saves for the supervisor to see?

**SCOPE:** All sections of the software will be tested this way.

**TESTERS:** Testing team.

**METHOD:** Bottom-top.

**TIMING:** when we have two individual components to see if there is no error to be able to
integrate them

#### ■ Validation Testing

**PURPOSE:** Validation testing will allow the team to check with the clients to see if it is to their
liking. Does it comply with their needs, and makes it simple?

SCOPE: All sections of the software will be validation tested. This means that the design will be
tested to see if it’s according to the client’s likings, and the functionality of the software will be
tested to see if it complies with the requirements set up by our stakeholders.

**TESTERS:** Testing team with Amazon

**METHOD:** Showing the software, minimum viable product, beta testing.

**TIMING:** by having the necessary components integrated to meet a requirement to validate its
correct implementation

#### ■ System Test

**PURPOSE:** Be confident about functionality, performance, and user experience

**SCOPE:** Since this is a system test, all the software will be tested. This will be done in order to
validate that the system was integrated correctly and that a regular activity flow can be
accomplished from start to finish.

**TESTERS:** Testing team.

**METHOD:** Black box run of the entire software through different entrances.

**TIMING:** After validating all funcional requests with Amazon, the System Test will be done.

### 2.7. Test acceptance criteria
#### Unit Test

● Login Functionality: This functionality should never fail. All tests must either deliver
the correct user and home page, or it should send an error message displaying that
the user doesn’t exist.

● Video Recording: This functionality should, at the very minimum, record the entire
screen and audio of the call. It also needs to start and end automatically, depending
on the Amazon Connect condition.

● Video Saving: The video needs to be saved to the correct database, and needs to be
retrievable from said location. Name, time, and datetime should be saved
automatically.

● Analysis Functionality: There should be different options for analysis. Rating, day of
the week, monthly view, section, etc. The display should show problematic ratings
with a different color from the rest.

#### Integration Test

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

#### Validation Test

● The clients and stakeholders are satisfied with the functionalities.

#### System Test

● The basic flow is able to be completed in one run, from log in to log out. Agents are
able to log in, record a video, save it, and log out; while Administrators and
Supervisors can log in, see their analysis, and log out.

### 2.8. Test Deliverables
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

### 2.9. Milestone List
The milestone list is tentative and may change due to below reasons

a) Any issues in the System environment readiness

b) Any change in scope/addition in scope

c) Any other dependency that impacts efforts and timelines

|  | Test Type | Test Example (SUT) | Dependency (DOC) |
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

### 2.10. Test Effort Estimate

This document lists out all the activities that have to be performed by the QA team and estimates how
many man-hours each activity is going to take.

QA DEPARTMENT IMAGE

The document can be visualized here and in the appendix
Note: this estimate is for the TCOE team only Testing Schedule

## 3. EXECUTION STRATEGY

### 3.1. Entry and Exit Criteria
- The entry criteria refer to the desirable conditions in order to start test execution; only the
migration of the code and fixes need to be assessed at the end of each cycle.

i. The exit criteria are the desirable conditions that need to be met in order proceed with the
implementation.
ii. Entry and exit criteria are flexible benchmarks. If they are not met, the test team will assess the
risk, identify mitigation actions and provide a recommendation. All this is input to the project
manager for a final “go-no go” decision.
iii. Entry criteria to start the execution phase of the test: the activities listed in the Test Planning
section of the schedule are 100% completed.
iv. Entry criteria to start each cycle: the activities listed in the Test Execution section of the schedule
are 100% completed at each cycle.
Exit Criteria 
Test Team
Technical Team 
Notes
100% Test Scripts executed
95% pass rate of Test Scripts
No open Critical and High severity defects
95% of Medium severity defects have been closed
All remaining defects are either canceled or
documented as Change Requests for a future release
All expected and actual results are captured and
documented with the test script
4. TEST MANAGEMENT PROCESS
4.1. Test Execution Process
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
4.2. Test Risks and Mitigation Factors
Risk Prob. Impact Mitigation Plan
Database Stops Working Low High The maintenance team should
constantly do data debugging to
ensure the database works correctly.
Database saturation of entry Medium High A backend function that analyzes all of
the input data before sending it to the
database.
Abuse of application in unintended
ways
Medium High Create a cybersecurity team, which
function would be to determine the
security risks in order to mitigate
them.
Recordings sent to database with
wrong tags
High Medium The administrators will be instructed
to keep constant attention in the
agents uploads.
Too many Requests at Once High High Create monitoring protocols to always
make sure that the application is
working within the resource utilization
limits.
Wrong People Access Recordings Low High Continuous monitoring to make sure
the application is working according to
the requirements.
Desync of recording components Low Low The testing team should make sure the
application records the screen
correctly.
Recordings take up too much
storage
Medium High The technical lead should choose a
video format that satisfies the
requirements.
Data takes too long to send Medium Medium The testing team should do both
performance and load tests.
4.3. Communications Plan and Team Roster
Role Expectations
The following list defines in general terms the expectations related to the roles directly involved in the
management, planning or execution of the test for the project.
Roles Description
1. Project Manager These members are in charge of directing a team to complete a specific
project. They should both organize and plan the tasks required for the
project to be successful, making sure they are all delivered according to
the deathline, budget and requirements.
2. Test Lead A test lead is responsible for directing the testing team. He should take
into consideration the necessities of all the stakeholders to do all of the
required tests to deliver a product that fits the requirements, time and
budget given.
3. Business Analyst They have a key role in the project, since they have to understand the
business necessities (which are defined by the client) and transmit them
to the development team. They should perfectly understand both the
business and the system.
4. Development Lead The lead developer(s) are in charge of designing, at least at a base level,
the software architecture. They also are in charge of directing and
organizing the development team to make sure the architecture is
implemented correctly.
5. Testing Team Led by the test lead, they should make sure the software is developed
according to the required quality standards. They should make tests
before, while and after the development is done.
6. Development Team They should follow the architecture proposed by the development lead,
and work continuously with the development team and the business
analyst to make sure the system is being developed according to all the
requirements.
7. Technical Lead This member is in charge of the most technical part of the project. He
should also be part of the software architecture design, to ensure all of
the technical aspects are taken into consideration. He mainly works with
the development team.
Project Management
● Project Manager: reviews the content of the Test Plan, Test Strategy and Test Estimates
signs off on it.
Test Planning (Test Lead)
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
Test Team
● Develop test conditions, test cases, expected results, and execution scripts.
● Perform execution and validation.
● Identify, document and prioritize defects according to the guidance provided by the Test
lead.
● Re-test after software modifications have been made according to the schedule.
● Prepare testing metrics and provide regular status.
Test Lead
● Acknowledge the completion of a section within a cycle.
● Give the OK to start the next level of testing.
● Facilitate defect communications between testing team and technical / development
team.
Development Team
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
Activities Cronogram
5. TEST ENVIRONMENT
The testing environment will consist of at minimum a windows environment, an intel i7 1.8 GHz core, 8GB
RAM, along with Google Chrome version 99 at minimum.
The application will be hosted through two instances, one to host the website and code, and another to
host the database, both utilizing AWS instances.
All testers will have access to the same version of the database and all necessary software
6. TESTS
7. CONCLUSIONS
The successful implementation of this test plan will greatly benefit the elaboration and future of the project.
The tests will be conducted continuously during the entirety of the project’s development and will help
identify potential problems and mitigate them before they can get out of hand. It is expected that this
document will be accessed when need be, to help clarify any potential doubts about the tests and to find
templates when applicable. It is expected that both the testers and developers that have helped shape this
document and agreed to the contents within will do their best to adhere to it. All of these things should help
the development run smoothly and fit the plans made prior to its implementation.
8. APPROVALS
The Names and Titles of all persons who must approve this plan.
Signature:
Name:
Role:
Date:
Signature:
Name:
Role:
Date: