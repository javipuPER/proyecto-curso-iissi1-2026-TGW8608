# Sistema de Gestión de una Clínica Médica

## Miembros del grupo LX-XXX-X

1. Pérez Ulgar, Francisco Javier
2. Osuna de Alba, Alejandro
3. Sánchez Corujo, Iván
4. Utrera Nieto, Leo

---

# 1. Introducción al problema

El proyecto consiste en el desarrollo de un sistema de información para la gestión de una clínica médica. Su finalidad es centralizar y organizar la información necesaria para administrar los pacientes, los profesionales sanitarios, los empleados, los departamentos, las citas y la actividad médica realizada en la clínica.

Actualmente, una clínica necesita gestionar una gran cantidad de información relacionada con las personas que reciben atención médica y con los profesionales que trabajan en ella. La falta de una estructura adecuada para almacenar y relacionar estos datos puede provocar duplicidades, errores en la gestión de las citas y dificultades para consultar el historial de atención de los pacientes.

El cliente del sistema es una clínica médica que necesita disponer de una herramienta que facilite la gestión de su actividad diaria. Los principales usuarios serán el personal administrativo y los médicos.

Entre los problemas que se pretenden solucionar se encuentran:

- La dificultad para mantener organizados los datos personales de pacientes y empleados.
- La duplicación de información y los errores en la identificación de las personas.
- La dificultad para gestionar las citas y conocer su estado.
- Los problemas derivados de la asignación de citas a los médicos.
- La necesidad de registrar y consultar las consultas realizadas a los pacientes.
- La dificultad para mantener información sobre los diagnósticos médicos.
- La necesidad de disponer de información organizada sobre los medicamentos.
- La dificultad para gestionar los empleados y su pertenencia a los distintos departamentos de la clínica.

Para responder a estas necesidades, el sistema permitirá registrar, consultar y modificar la información de las personas, los pacientes, los empleados, los médicos, los departamentos, las citas, las consultas, los diagnósticos y los medicamentos.

El sistema también permitirá mantener la información necesaria para identificar a los pacientes, conocer las características de los profesionales sanitarios y consultar los datos relacionados con la atención médica prestada.

El alcance del proyecto se centra en la gestión básica de la información de una clínica. No se pretende desarrollar un sistema hospitalario completo, sino una solución proporcionada a la magnitud del proyecto académico.

---

# 2. Glosario de términos

Los siguientes términos describen los principales conceptos del dominio del problema. Se presentan ordenados alfabéticamente.

**Forma farmacéutica:** Forma en la que se presenta un medicamento para su administración, como comprimido, cápsula, jarabe o inyectable.

---

# 3. Visión general del sistema

## 3.1. Requisitos generales

El sistema permitirá gestionar de forma centralizada la información necesaria para el funcionamiento de la clínica médica.

Los requisitos generales del sistema son los siguientes:

1. Registrar, consultar y modificar los datos personales de las personas.
2. Gestionar la información específica de los pacientes.
3. Gestionar los empleados y sus datos laborales.
4. Organizar los empleados en departamentos.
5. Gestionar la información específica de los médicos.
6. Registrar y gestionar las citas de los pacientes.
7. Controlar los estados de las citas.
8. Registrar las consultas realizadas durante la atención médica.
9. Mantener información sobre los diagnósticos médicos.
10. Gestionar la información de los medicamentos.
11. Garantizar la coherencia y la integridad de los datos almacenados.
12. Evitar duplicidades y errores en la identificación de las personas.

El sistema utilizará tipos enumerados para representar determinados valores controlados. En concreto, el estado de las citas se representará mediante `EstadoCita` y la forma farmacéutica de los medicamentos mediante `FormaFarmaceutica`.

## 3.2. Usuarios del sistema

### Personal administrativo

El personal administrativo será responsable de las tareas relacionadas con la organización y gestión de la clínica.

Entre sus funciones se encuentran:

- Registrar y actualizar los datos de las personas.
- Gestionar la información de los pacientes.
- Registrar y actualizar los empleados.
- Gestionar los departamentos de la clínica.
- Mantener la información de los médicos.
- Crear y modificar citas.
- Consultar el estado de las citas.

### Médico

El médico será el usuario encargado de las tareas relacionadas con la atención sanitaria.

Entre sus funciones se encuentran:

- Consultar la información de los pacientes.
- Consultar las citas relacionadas con su actividad.
- Registrar las consultas realizadas.
- Registrar y consultar los diagnósticos.
- Consultar la información de los medicamentos disponibles.

El acceso a la información deberá adecuarse a las funciones de cada usuario y respetar la confidencialidad de los datos personales y médicos.

---

# 4. Catálogo de requisitos

## 4.1. Requisitos funcionales

### R.F.01. Gestionar personas

Como personal administrativo quiero registrar y actualizar los datos personales de las personas para mantener correctamente identificados a los individuos relacionados con la clínica.

**Prueba de aceptación**

- Se debe poder registrar una persona.
- Se deben poder consultar los datos de una persona.
- Se deben poder modificar los datos personales almacenados.
- Cada persona deberá disponer de un identificador.
- No podrán existir dos personas diferentes con el mismo DNI.
- Se deben almacenar el nombre, los apellidos, el DNI, la fecha de nacimiento, el correo electrónico, el teléfono y la dirección.
- Se debe aplicar la regla de negocio R.N.01.

### R.F.02. Gestionar pacientes

Como personal administrativo quiero registrar y actualizar los pacientes para mantener organizada la información necesaria para su atención médica.

**Prueba de aceptación**

- Se debe poder registrar un paciente asociado a una persona.
- Se debe poder consultar y modificar la información de un paciente.
- Cada paciente deberá disponer de un identificador propio.
- Cada paciente deberá disponer de un número de historia clínica.
- Se podrán registrar las alergias y observaciones del paciente.
- Se podrá indicar si el paciente necesita habitación.
- Se debe garantizar que cada paciente corresponda a una única persona.
- Se debe aplicar la regla de negocio R.N.02.

### R.F.03. Gestionar empleados y departamentos

Como personal administrativo quiero gestionar los empleados y los departamentos para mantener organizada la estructura de la clínica.

**Prueba de aceptación**

- Se debe poder registrar un empleado.
- Se deben poder consultar y modificar sus datos laborales.
- Se debe poder registrar un departamento.
- Se deben poder consultar y modificar los datos de los departamentos.
- Se almacenarán la fecha de alta, el salario y el estado del empleado.
- Cada empleado deberá pertenecer a un único departamento.
- Se deberá poder consultar qué empleados pertenecen a un departamento.
- Se debe aplicar la regla de negocio R.N.03.

### R.F.04. Gestionar médicos

Como personal administrativo quiero gestionar la información de los médicos para conocer los profesionales sanitarios de la clínica y facilitar la organización de su actividad.

**Prueba de aceptación**

- Se debe poder registrar un médico asociado a un empleado.
- Se deben poder consultar los datos de un médico.
- Se deberán almacenar la especialidad, el número de colegiado y el turno.
- Cada médico deberá corresponder a un empleado de la clínica.
- Se deberán poder consultar las citas asignadas a un médico.
- Se debe aplicar la regla de negocio R.N.04.

### R.F.05. Gestionar citas

Como personal administrativo quiero gestionar las citas para organizar la atención de los pacientes y conocer cuándo serán atendidos.

**Prueba de aceptación**

- Se debe poder crear una cita.
- Cada cita deberá disponer de un identificador.
- Cada cita deberá estar asociada a un paciente y a un médico.
- Se almacenarán la fecha y hora, el estado, el motivo y las observaciones.
- Se podrá modificar el estado de una cita.
- El estado deberá pertenecer al enumerado `EstadoCita`.
- Un médico no podrá tener dos citas distintas a la misma fecha y hora.
- Se deberá poder consultar la agenda de un médico.
- Se debe aplicar las reglas de negocio R.N.05 y R.N.06.

### R.F.06. Registrar consultas

Como médico quiero registrar las consultas realizadas para mantener un registro de la atención médica prestada a los pacientes.

**Prueba de aceptación**

- Se debe poder registrar una consulta.
- Cada consulta deberá disponer de un identificador.
- Se almacenarán la fecha y hora, el diagnóstico y las observaciones.
- Cada consulta deberá estar asociada a una cita.
- Se deberá poder identificar al médico que realiza la consulta.
- Se deberán poder consultar las consultas relacionadas con la atención de un paciente.
- Se debe aplicar la regla de negocio R.N.07.

### R.F.07. Gestionar diagnósticos

Como médico quiero registrar y consultar diagnósticos para mantener organizada la información clínica relacionada con las enfermedades o condiciones identificadas durante la atención médica.

**Prueba de aceptación**

- Se debe poder registrar un diagnóstico.
- Cada diagnóstico deberá disponer de un identificador.
- Se almacenarán la fecha y las observaciones del diagnóstico.
- Se deberá poder consultar la información de un diagnóstico.
- Se deberá poder mantener la información diagnóstica relacionada con la atención médica del paciente.

### R.F.08. Gestionar medicamentos

Como usuario autorizado quiero registrar y consultar los medicamentos para disponer de información organizada sobre los productos farmacéuticos utilizados en la clínica.

**Prueba de aceptación**

- Se debe poder registrar un medicamento.
- Se debe poder consultar la información de un medicamento.
- Cada medicamento deberá disponer de un identificador.
- Se almacenarán el nombre, la dosis, la forma farmacéutica y el precio.
- La forma farmacéutica deberá pertenecer al enumerado `FormaFarmaceutica`.
- Se deberá poder modificar la información de un medicamento.
- Se debe aplicar la regla de negocio R.N.08.

---

## 4.1.1. Requisitos de información

### R.I.01. Información de personas

Como usuario autorizado quiero almacenar los datos personales de las personas para poder identificarlas correctamente dentro del sistema.

**Prueba de aceptación**

- Cada persona tendrá un identificador `idPersona`.
- Se almacenarán el nombre y los apellidos.
- Se almacenará el DNI.
- Se almacenará la fecha de nacimiento.
- Se almacenarán el correo electrónico, el teléfono y la dirección.
- El DNI deberá ser único.

### R.I.02. Información de pacientes

Como usuario autorizado quiero almacenar la información específica de los pacientes para gestionar adecuadamente su atención médica.

**Prueba de aceptación**

- Cada paciente tendrá un identificador `idPaciente`.
- Cada paciente tendrá un número de historia clínica.
- Se podrán almacenar las alergias.
- Se podrán almacenar las observaciones.
- Se podrá indicar si necesita habitación.
- El paciente estará asociado a una persona.

### R.I.03. Información de empleados

Como usuario autorizado quiero almacenar los datos laborales de los empleados para gestionar la plantilla de la clínica.

**Prueba de aceptación**

- Cada empleado tendrá un identificador `idEmpleado`.
- Se almacenará la fecha de alta.
- Se almacenará el salario.
- Se almacenará el estado laboral.
- El empleado estará asociado a una persona.
- Se conocerá el departamento al que pertenece cada empleado.

### R.I.04. Información de departamentos

Como usuario autorizado quiero almacenar la información de los departamentos para representar la organización de la clínica.

**Prueba de aceptación**

- Cada departamento tendrá un identificador `idDepartamento`.
- Cada departamento tendrá un nombre.
- Cada departamento podrá tener una descripción.
- Se podrá consultar la información de los departamentos.

### R.I.05. Información de médicos

Como usuario autorizado quiero almacenar la información específica de los médicos para identificar a los profesionales sanitarios de la clínica.

**Prueba de aceptación**

- Cada médico tendrá un identificador `idMedico`.
- Se almacenará la especialidad.
- Se almacenará el número de colegiado.
- Se almacenará el turno.
- Cada médico estará asociado a un empleado.

### R.I.06. Información de citas

Como usuario autorizado quiero almacenar los datos de las citas para conocer cuándo y con quién será atendido cada paciente.

**Prueba de aceptación**

- Cada cita tendrá un identificador `idCita`.
- Se almacenará la fecha y hora.
- Se almacenará el estado de la cita.
- Se podrá almacenar el motivo.
- Se podrán almacenar observaciones.
- Cada cita estará asociada a un paciente y a un médico.

### R.I.07. Información de consultas

Como médico quiero almacenar la información de las consultas para mantener un registro de la atención médica realizada.

**Prueba de aceptación**

- Cada consulta tendrá un identificador `idConsulta`.
- Se almacenará la fecha y hora.
- Se almacenará el diagnóstico.
- Se podrán almacenar observaciones.
- Cada consulta estará asociada a una cita.
- Se podrá identificar al médico responsable de la consulta.

### R.I.08. Información de diagnósticos

Como médico quiero almacenar los diagnósticos para mantener un registro de la información clínica correspondiente.

**Prueba de aceptación**

- Cada diagnóstico tendrá un identificador `idDiagnostico`.
- Se almacenará la fecha.
- Se podrán almacenar observaciones.
- Se podrá consultar la información de cada diagnóstico.

### R.I.09. Información de medicamentos

Como usuario autorizado quiero almacenar la información de los medicamentos para poder consultarlos y mantener actualizados sus datos.

**Prueba de aceptación**

- Cada medicamento tendrá un identificador `idMedicamento`.
- Se almacenará el nombre.
- Se almacenará la dosis.
- Se almacenará la forma farmacéutica.
- Se almacenará el precio.
- La forma farmacéutica pertenecerá al enumerado `FormaFarmaceutica`.

---

## 4.1.2. Reglas de negocio

### R.N.06. Conflicto de citas

Un médico no podrá tener dos citas distintas en la misma fecha y hora.

### R.N.06. Cancelación de citas

Una cita no podrá ser cancelada en un plazo anterior a 24 horas de la cita asignada.

### R.N.07. Consulta asociada a una cita

Toda consulta registrada deberá estar asociada a una única cita. Además, se deberá poder identificar al médico responsable de su realización.

### R.N.09. Estado de las citas

El estado de una cita solo podrá tomar uno de los valores definidos por el enumerado `EstadoCita`: `PENDIENTE`, `CONFIRMADA` o `CANCELADA`.

---

## 4.2. Mapa de historias de usuario

Las historias de usuario se agrupan en tres épicas relacionadas con las principales funcionalidades del sistema.

### Épica 1. Gestión de personas y organización

- **HU01. Registrar persona:** Como personal administrativo quiero registrar personas para mantener sus datos personales.
- **HU02. Registrar paciente:** Como personal administrativo quiero registrar pacientes para gestionar su atención médica.
- **HU03. Registrar empleado:** Como personal administrativo quiero registrar empleados para mantener actualizada la plantilla de la clínica.
- **HU04. Gestionar departamentos:** Como personal administrativo quiero gestionar departamentos para organizar los empleados.
- **HU05. Gestionar médicos:** Como personal administrativo quiero gestionar médicos para conocer a los profesionales sanitarios de la clínica.

### Épica 2. Gestión de citas y consultas

- **HU06. Crear cita:** Como personal administrativo quiero crear citas para organizar la atención de los pacientes.
- **HU07. Modificar estado de cita:** Como personal administrativo quiero modificar el estado de una cita para mantener actualizada la agenda.
- **HU08. Consultar agenda médica:** Como médico quiero consultar mis citas para conocer la planificación de mi actividad.
- **HU09. Registrar consulta:** Como médico quiero registrar consultas para mantener un historial de la atención médica.
- **HU10. Gestionar diagnósticos:** Como médico quiero registrar y consultar diagnósticos para mantener organizada la información clínica.

### Épica 3. Gestión de medicamentos

- **HU11. Registrar medicamento:** Como usuario autorizado quiero registrar medicamentos para mantener actualizada la información farmacéutica.
- **HU12. Consultar medicamentos:** Como médico quiero consultar los medicamentos para disponer de información sobre sus características.

---

## 4.3. Requisitos no funcionales

### R.N.F.01. Seguridad

Como responsable de la clínica quiero que el acceso al sistema y a la información médica esté restringido según los permisos de cada usuario para proteger la confidencialidad de los datos de pacientes y empleados.

**Característica ISO/IEC 25010:** Seguridad.

**Pruebas de aceptación**

- El sistema deberá permitir el acceso únicamente a usuarios autenticados y autorizados.
- Las operaciones disponibles deberán corresponderse con los permisos asignados a cada usuario.
- Los usuarios sin permisos suficientes no deberán poder consultar ni modificar información médica restringida.
- El sistema deberá impedir el acceso a las funcionalidades protegidas cuando no exista una sesión autenticada válida.

### R.N.F.02. Fiabilidad

Como responsable de la clínica quiero que el sistema mantenga la integridad y coherencia de la información para evitar duplicidades, referencias incorrectas y datos incompatibles con las reglas establecidas.

**Característica ISO/IEC 25010:** Fiabilidad, concretamente tolerancia a fallos y capacidad de recuperación cuando sean aplicables, junto con la integridad de los datos como propiedad de calidad de la información.

**Pruebas de aceptación**

- Cada registro deberá disponer de un identificador único que permita distinguirlo del resto.
- El sistema deberá impedir la existencia de dos personas con el mismo DNI.
- Las relaciones entre las entidades del sistema deberán respetar las restricciones de integridad referencial definidas.
- Los atributos definidos mediante tipos enumerados deberán admitir exclusivamente los valores establecidos en sus respectivas enumeraciones.
- El sistema deberá rechazar las operaciones que incumplan las restricciones de integridad definidas, informando del error producido.

### R.N.F.03. Capacidad de interacción

Como usuario de la clínica quiero que la interfaz permita realizar las operaciones habituales de forma comprensible y sencilla para gestionar la información con eficiencia y reducir los errores de uso.

**Característica ISO/IEC 25010:** Capacidad de interacción (*Interaction capability*), incluyendo la facilidad de aprendizaje, la operabilidad y la protección frente a errores de uso, según corresponda.

**Pruebas de aceptación**

- Las funcionalidades de consulta, alta y modificación de información deberán presentarse de forma clara y diferenciada.
- Los campos de entrada deberán identificarse mediante etiquetas comprensibles para el usuario.
- Cuando se introduzcan datos inválidos, el sistema deberá indicar el error y permitir su corrección.
- La información consultada deberá mostrarse organizada y con una estructura coherente en las distintas funcionalidades.
- Las operaciones habituales deberán poder realizarse sin necesidad de conocer detalles técnicos de la implementación.

### R.N.F.04. Mantenibilidad

Como responsable del sistema quiero que el software tenga una estructura organizada y comprensible para facilitar su corrección, adaptación y ampliación ante futuras necesidades de la clínica.

**Característica ISO/IEC 25010:** Mantenibilidad, incluyendo modularidad, analizabilidad, modificabilidad y capacidad de prueba.

**Pruebas de aceptación**

- El código deberá organizarse en módulos o componentes con responsabilidades diferenciadas.
- La estructura del software deberá mantener una correspondencia coherente con las entidades y responsabilidades definidas en el modelo conceptual.
- Las modificaciones de una funcionalidad deberán minimizar los cambios innecesarios en otras funcionalidades.
- Las principales reglas de negocio y restricciones de integridad deberán estar documentadas.
- Las funcionalidades deberán poder verificarse mediante pruebas que permitan detectar errores introducidos por modificaciones.

---

**-- FIN ENTREGABLE 1 --**

## 5. Modelo conceptual

Esta en el archivo Modelado conceptual3.png

### 5.1. Diagramas de clases UML

- con restricciones.

### 5.2. Escenarios de prueba

- con descripción textual y diagrama de objetos UML.

## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:------|:-----------|:-----------|:-----------|:-----------|
| RI-1  | X          | X          | X          | X          |
| RI-2  |            | X          |            | X          |
| RF-1  |            | X          |            | X          |
| RF-2  | X          |            | X          | X          |
| RN-1  |            | X          |            |            |
| RN-2  | X          | X          | X          |            |
| ...   |            |            |            |            |

-- fin entregable 2 --

## 7. Modelo relacional en 3FN

- Relaciones obtenidas al aplicar la transformación del modelo conceptual.

### 7.1.  Justificación de la estrategia de transformación de jerarquías

- si se identificaron jerarquías en el MC.


### 8. Matriz de trazabilidad MC/SQL (opcional):

- Restricciones sobre el MC / Elementos del modelo tecnológico (SQL) (Triggers, checks, etc.)
- Incluir Reglas de negocio — Constraints/Triggers en las matrices de trazabilidad para el entregable 3

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:-------|:-------|:-------|:-------|:-------|
| TABLA-1 |        |        |        |        |
| TABLA-2 |        |        |        |        |
| TABLA-3 |        |        |        |        |
| TABLA-4 |        |        |        |        |
| TRIG-1 |        |        |        |        |
| TRIG-2 | X      | X      |        | X      |
| TRIG-3 |        | X      |        | X      |
| TRIG-4 |        |        | X      |        |
| CONST-1 |        |        |        |        |
| CONST-2 | X      | X      |        | X      |
| CONST-3 |        | X      |        | X      |
| CONST-4 |        |        | X      |        |

Se consideran todo tipo de constraints declarativas (aquellas definidas durante el CREATE TABLE).
-- fin entregable 3 --

## Referencias


