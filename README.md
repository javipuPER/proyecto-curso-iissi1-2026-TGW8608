# Sistema de Gestión de una Clínica Médica

## Miembros del grupo LX-XXX-X

1. Pérez Ulgar, Francisco Javier
2. Osuna de Alba, Alejandro
3. Sanchez Corujo, Ivan
4. Utrera Nieto, Leo

---

# 1. Introducción al problema

El proyecto consiste en el desarrollo de un sistema de información para la gestión de una clínica médica.

El cliente del sistema es una clínica que necesita organizar y centralizar la información relacionada con las personas que forman parte de ella, sus empleados, los médicos, los departamentos, los pacientes, las citas, las consultas, las recetas y los medicamentos.

La clínica necesita disponer de una forma estructurada de gestionar la información de sus pacientes y profesionales sanitarios, así como de las distintas actividades médicas que se realizan.

Entre los principales problemas que se pretenden solucionar se encuentran:

- La dificultad para mantener organizada la información de pacientes y empleados.
- La dificultad para gestionar las citas de los pacientes.
- La posibilidad de producir errores al asignar citas a médicos.
- La dificultad para consultar las consultas realizadas a un paciente.
- La necesidad de mantener información sobre las recetas y los medicamentos prescritos.
- La falta de una estructura centralizada para relacionar empleados con departamentos.

El sistema permitirá centralizar esta información y facilitar su consulta y mantenimiento.

Los principales usuarios del sistema serán el personal administrativo de la clínica y los médicos.

El personal administrativo será responsable principalmente de la gestión de pacientes, empleados, departamentos y citas.

Los médicos utilizarán el sistema para consultar la información de los pacientes y registrar las consultas y recetas correspondientes.

---

# 2. Glosario de términos

**Cita:** Reserva de una fecha y hora para que un paciente sea atendido por un médico.

**Consulta:** Atención médica realizada por un médico a un paciente en el contexto de una cita.

**Departamento:** Unidad organizativa de la clínica a la que pertenece un empleado.

**Empleado:** Persona que trabaja para la clínica.

**Estado de cita:** Situación en la que se encuentra una cita. Puede ser pendiente, confirmada o cancelada.

**Forma farmacéutica:** Forma en la que se presenta un medicamento, como comprimido, cápsula, jarabe o inyectable.

**Medicamento:** Producto que puede ser incluido en una receta médica.

**Médico:** Empleado de la clínica encargado de atender a los pacientes y realizar consultas.

**Paciente:** Persona que recibe atención médica en la clínica.

**Persona:** Individuo cuyos datos personales son gestionados por el sistema.

**Receta:** Prescripción médica que contiene uno o varios medicamentos.

---

# 3. Visión general del sistema

## 3.1. Requisitos generales

El sistema permitirá gestionar de forma centralizada la información necesaria para el funcionamiento de la clínica.

Los principales requisitos generales son:

1. Gestionar la información de las personas, pacientes y empleados.
2. Gestionar los departamentos y los empleados pertenecientes a ellos.
3. Gestionar los médicos de la clínica.
4. Gestionar las citas de los pacientes con los médicos.
5. Registrar las consultas realizadas por los médicos.
6. Registrar las recetas generadas durante las consultas.
7. Gestionar los medicamentos incluidos en las recetas.
8. Mantener la coherencia e integridad de la información.

## 3.2. Usuarios del sistema

### Personal administrativo

El personal administrativo será responsable de las tareas de gestión de la clínica.

Podrá gestionar:

- Personas.
- Pacientes.
- Empleados.
- Departamentos.
- Médicos.
- Citas.

### Médico

El médico será el usuario encargado de las tareas relacionadas con la atención sanitaria.

Podrá:

- Consultar pacientes.
- Consultar sus citas.
- Registrar consultas.
- Generar recetas.
- Consultar medicamentos.

---

# 4. Catálogo de requisitos

## 4.1. Requisitos funcionales

### R.F.01. Gestionar personas

Como personal administrativo quiero registrar y actualizar los datos de las personas para mantener correctamente identificados a pacientes y empleados.

**Prueba de aceptación**

- Se debe poder registrar una persona.
- Se deben poder modificar sus datos personales.
- Se debe poder consultar la información almacenada de una persona.
- No podrá existir más de una persona con el mismo DNI.
- Se debe aplicar la regla de negocio R.N.01.

### R.F.02. Gestionar pacientes

Como personal administrativo quiero registrar pacientes para poder gestionar su atención médica.

**Prueba de aceptación**

- Se debe poder registrar un paciente asociado a una persona.
- Se debe poder consultar la información del paciente.
- Se debe poder modificar la información del paciente.
- El paciente debe poder tener una o varias citas.
- Se debe aplicar la regla de negocio R.N.02.

### R.F.03. Gestionar empleados y departamentos

Como personal administrativo quiero gestionar empleados y departamentos para mantener organizada la estructura de la clínica.

**Prueba de aceptación**

- Se debe poder registrar un empleado.
- Se debe poder registrar un departamento.
- Cada empleado deberá pertenecer a un departamento.
- Se deberán poder consultar los empleados pertenecientes a un departamento.
- Se debe aplicar la regla de negocio R.N.03.

### R.F.04. Gestionar médicos

Como personal administrativo quiero gestionar los médicos para poder asignarlos a las citas de los pacientes.

**Prueba de aceptación**

- Se debe poder registrar un médico.
- El médico deberá estar asociado a un empleado.
- Se podrá consultar la información de un médico.
- Se podrán consultar las citas asignadas a un médico.
- Se debe aplicar la regla de negocio R.N.04.

### R.F.05. Gestionar citas

Como personal administrativo quiero gestionar las citas para organizar la atención de los pacientes.

**Prueba de aceptación**

- Se debe poder crear una cita.
- La cita debe estar asociada a un paciente.
- La cita debe estar asociada a un médico.
- Se debe almacenar su fecha y hora.
- Se debe poder modificar su estado.
- No se permitirá que un médico tenga dos citas simultáneas.
- Se debe aplicar la regla de negocio R.N.05.

### R.F.06. Registrar consultas

Como médico quiero registrar las consultas realizadas para mantener un historial de la atención médica de los pacientes.

**Prueba de aceptación**

- Una consulta debe estar asociada a una cita.
- Se debe almacenar la fecha y hora de la consulta.
- Se deberán poder almacenar las observaciones.
- Se deberá poder registrar el diagnóstico mediante el atributo correspondiente de la consulta.
- Una consulta deberá ser realizada por un médico.
- Se debe aplicar la regla de negocio R.N.06.

### R.F.07. Gestionar recetas

Como médico quiero generar recetas durante una consulta para registrar los medicamentos indicados al paciente.

**Prueba de aceptación**

- Una receta debe estar asociada a una consulta.
- Se debe almacenar la fecha de la receta.
- Se podrán almacenar observaciones.
- Una receta deberá incluir al menos un medicamento.
- Se debe aplicar la regla de negocio R.N.07.

### R.F.08. Gestionar medicamentos

Como médico quiero consultar los medicamentos disponibles para poder incluirlos en las recetas.

**Prueba de aceptación**

- Se debe poder registrar un medicamento.
- Se debe poder consultar un medicamento.
- Se debe almacenar su nombre.
- Se debe almacenar su forma farmacéutica.
- Se deberá poder utilizar un mismo medicamento en distintas recetas.
- La forma farmacéutica deberá pertenecer al tipo enumerado FormaFarmacia.

---

## 4.1.1. Requisitos de información

### R.I.01. Información de personas

Como usuario autorizado quiero almacenar los datos personales de una persona para identificarla correctamente.

**Prueba de aceptación**

- Se almacenará un identificador.
- Se almacenarán nombre y apellidos.
- Se almacenará el DNI.
- Se almacenará la fecha de nacimiento.
- El DNI será único.

### R.I.02. Información de pacientes

Como usuario autorizado quiero almacenar la información específica de los pacientes para gestionar su atención.

**Prueba de aceptación**

- Se almacenará el identificador del paciente.
- Se almacenará el número de historia clínica.
- Se podrán almacenar alergias.
- Se podrán almacenar observaciones.

### R.I.03. Información de empleados

Como usuario autorizado quiero almacenar la información de los empleados para gestionar la plantilla de la clínica.

**Prueba de aceptación**

- Se almacenará el identificador del empleado.
- Se almacenará la fecha de alta.
- Se almacenará el salario.
- Se almacenará su estado.
- Se conocerá el departamento al que pertenece.

### R.I.04. Información de departamentos

Como usuario autorizado quiero almacenar los departamentos para representar la organización de la clínica.

**Prueba de aceptación**

- Cada departamento tendrá un identificador.
- Cada departamento tendrá un nombre.
- Cada departamento podrá tener una descripción.

### R.I.05. Información de médicos

Como usuario autorizado quiero almacenar la información de los médicos para conocer los profesionales que atienden a los pacientes.

**Prueba de aceptación**

- Cada médico tendrá un identificador.
- Se almacenará su número de colegiado.
- Se almacenará la información necesaria para identificarlo.

### R.I.06. Información de citas

Como usuario autorizado quiero almacenar las citas para conocer cuándo y con qué médico será atendido cada paciente.

**Prueba de aceptación**

- Cada cita tendrá un identificador.
- Se almacenará la fecha y hora.
- Se almacenará su estado.
- Se podrá almacenar el motivo.
- Se podrán almacenar observaciones.
- Cada cita estará asociada a un paciente y a un médico.

### R.I.07. Información de consultas

Como médico quiero almacenar las consultas realizadas para mantener información de la atención proporcionada.

**Prueba de aceptación**

- Cada consulta tendrá un identificador.
- Se almacenará la fecha y hora.
- Se almacenará el diagnóstico.
- Se podrán almacenar observaciones.
- La consulta estará asociada a una cita.

### R.I.08. Información de recetas

Como médico quiero almacenar las recetas para mantener un registro de las prescripciones realizadas.

**Prueba de aceptación**

- Cada receta tendrá un identificador.
- Se almacenará la fecha.
- Se podrán almacenar observaciones.
- Cada receta estará asociada a una consulta.

### R.I.09. Información de medicamentos

Como usuario autorizado quiero almacenar los medicamentos para poder utilizarlos en las recetas.

**Prueba de aceptación**

- Cada medicamento tendrá un identificador.
- Se almacenará su nombre.
- Se almacenará su dosis.
- Se almacenará su forma farmacéutica.
- Se almacenará su precio.

---

## 4.1.2. Reglas de negocio

### R.N.01. DNI único

No pueden existir dos personas diferentes con el mismo DNI.

### R.N.02. Identificación del paciente

Cada paciente debe corresponder a una única persona.

### R.N.03. Pertenencia a un departamento

Cada empleado debe pertenecer a un único departamento.

### R.N.04. Médico como empleado

Todo médico registrado en el sistema debe corresponder a un empleado de la clínica.

### R.N.05. Conflicto de citas

Un médico no puede tener dos citas distintas a la misma fecha y hora.

### R.N.06. Consulta asociada a una cita

Toda consulta registrada debe estar asociada a una única cita.

### R.N.07. Receta con medicamentos

Toda receta debe incluir al menos un medicamento.

### R.N.08. Estado de la cita

El estado de una cita solo puede tomar los valores definidos por el enumerado `EstadoCita`.

### R.N.09. Forma farmacéutica

La forma farmacéutica de un medicamento solo puede tomar uno de los valores definidos por el enumerado `FormaFarmacia`.

---

## 4.2. Mapa de historias de usuario

### Épica 1. Gestión de personas

- HU01. Registrar persona.
- HU02. Registrar paciente.
- HU03. Registrar empleado.
- HU04. Gestionar departamentos.

### Épica 2. Gestión de citas y consultas

- HU05. Crear cita.
- HU06. Modificar estado de cita.
- HU07. Registrar consulta.

### Épica 3. Gestión de recetas

- HU08. Crear receta.
- HU09. Consultar medicamentos.
- HU10. Añadir medicamentos a una receta.

---

## 4.3. Requisitos no funcionales

### R.N.F.01. Seguridad

Como usuario autorizado quiero que el sistema controle el acceso a la información para impedir que usuarios no autorizados consulten o modifiquen los datos de la clínica.

### R.N.F.02. Integridad

Como responsable de la clínica quiero que el sistema impida almacenar información incoherente para garantizar la integridad de los datos.

### R.N.F.03. Usabilidad

Como usuario quiero que las operaciones habituales del sistema sean sencillas de realizar para poder gestionar la información de la clínica de forma eficiente.

-- fin entregable 1 --

# 5. Modelo conceptual

## 5.1. Diagramas de clases UML

El modelo conceptual se representa mediante un diagrama de clases UML.

Las clases entidad que forman parte del modelo son:

- `Persona`
- `Paciente`
- `Empleado`
- `Medico`
- `Departamento`
- `Cita`
- `Consulta`
- `Receta`
- `Medicamento`

Además, se utilizan los siguientes tipos enumerados:

- `EstadoCita`
- `FormaFarmacia`

### Generalización Persona

La clase `Persona` se especializa en `Paciente` y `Empleado`.

Esta relación permite representar que tanto los pacientes como los empleados son personas.

La clasificación se considera incompleta, ya que una persona puede existir sin ser paciente ni empleado.

La clasificación se considera solapada, ya que una persona podría desempeñar simultáneamente los roles de paciente y empleado.

### Relaciones principales

`Empleado` trabaja en un `Departamento`.

Un `Paciente` solicita o tiene `Cita`.

Una `Cita` es atendida por un `Medico`.

Una `Cita` puede generar una `Consulta`.

Una `Consulta` es realizada por un `Medico`.

Una `Consulta` puede generar una o varias `Recetas`.

Una `Receta` contiene uno o varios `Medicamentos`.

Las asociaciones del modelo incluirán las multiplicidades correspondientes.

### Tipos enumerados

#### EstadoCita

Los posibles valores son:

```text
PENDIENTE
CONFIRMADA
CANCELADA
