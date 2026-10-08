# Sistema de Gestión de una Clínica Médica

## Miembros del grupo LX-XXX-X

1. Pérez Ulgar, Francisco Javier
2. Osuna de Alba, Alejandro
3. Sanchez Corujo, Ivan
4. Utrera Nieto, Leo

---

# 1. Introducción al problema

El proyecto consiste en el desarrollo de un sistema de información para la gestión integral de una clínica médica privada.

Actualmente, la clínica necesita gestionar una gran cantidad de información relacionada con sus pacientes, empleados, médicos, especialidades, citas, consultas, diagnósticos, recetas, medicamentos, departamentos, servicios, pruebas médicas y habitaciones.

La información se encuentra habitualmente repartida entre diferentes medios de almacenamiento, como documentos, hojas de cálculo o aplicaciones independientes. Esta situación dificulta el acceso centralizado a la información y puede provocar problemas como:

- Duplicidad de información de pacientes y empleados.
- Dificultad para consultar el historial de un paciente.
- Errores en la gestión de citas.
- Problemas para controlar qué médico atiende a cada paciente.
- Dificultad para consultar diagnósticos y patologías.
- Falta de control sobre las recetas y medicamentos prescritos.
- Dificultad para gestionar los servicios y pruebas disponibles.
- Falta de información centralizada sobre las habitaciones disponibles.

El cliente del sistema es la propia clínica, que necesita disponer de una base de datos centralizada que permita almacenar y consultar toda esta información de manera estructurada.

Los principales usuarios del sistema serán el personal administrativo de la clínica y el personal sanitario.

El sistema deberá permitir mantener la información actualizada y facilitar las tareas de gestión diaria de la clínica.

El alcance inicial del proyecto contempla una única clínica, por lo que no es necesario almacenar información sobre distintas clínicas o centros.

---

# 2. Glosario de términos

Los términos utilizados en el dominio del problema son los siguientes, ordenados alfabéticamente:

**Cita:** Reserva de una fecha y hora para que un paciente sea atendido por un médico.

**Consulta:** Acto médico realizado por un médico a un paciente en el contexto de una cita.

**Contacto:** Medio mediante el cual se puede contactar con una persona, como un teléfono, un correo electrónico o una dirección.

**Departamento:** Unidad organizativa de la clínica a la que pertenecen los empleados y que ofrece determinados servicios.

**Diagnóstico:** Resultado de la evaluación médica realizada sobre un paciente durante una consulta.

**Empleado:** Persona que trabaja para la clínica.

**Especialidad:** Área de conocimiento médico en la que está especializado un médico.

**Estado de la cita:** Situación en la que se encuentra una cita, por ejemplo pendiente, confirmada o cancelada.

**Estado de habitación:** Situación actual de una habitación, pudiendo estar libre, ocupada, en limpieza o en mantenimiento.

**Forma farmacéutica:** Presentación de un medicamento, como comprimido, cápsula, jarabe o inyectable.

**Habitación:** Espacio de la clínica destinado a la hospitalización o alojamiento temporal de pacientes.

**Medicamento:** Producto farmacéutico que puede ser prescrito por un médico.

**Médico:** Profesional sanitario encargado de atender a los pacientes y realizar consultas y diagnósticos.

**Paciente:** Persona que recibe atención médica en la clínica.

**Patología:** Enfermedad o afección médica que puede ser diagnosticada en un paciente.

**Prueba:** Prueba o procedimiento médico que puede formar parte de los servicios ofrecidos por la clínica.

**Receta:** Prescripción realizada por un médico como resultado de una consulta.

**Servicio:** Servicio sanitario ofrecido por un departamento de la clínica.

---

# 3. Visión general del sistema

## 3.1. Requisitos generales

El sistema deberá permitir gestionar de forma centralizada la información de la clínica.

Los principales requisitos generales del sistema son:

1. Gestionar la información personal de pacientes y empleados.
2. Gestionar diferentes medios de contacto asociados a las personas.
3. Gestionar los departamentos de la clínica.
4. Gestionar los empleados pertenecientes a cada departamento.
5. Gestionar la información de los médicos y sus especialidades.
6. Gestionar las citas de los pacientes.
7. Registrar las consultas realizadas por los médicos.
8. Registrar diagnósticos y patologías.
9. Gestionar las recetas y los medicamentos prescritos.
10. Gestionar los servicios y pruebas médicas disponibles.
11. Gestionar las habitaciones de la clínica.
12. Mantener la integridad y coherencia de la información almacenada.

El sistema estará orientado principalmente a operaciones de consulta, alta, modificación y baja de información, así como al registro de las actividades médicas realizadas.

## 3.2. Usuarios del sistema

### Personal administrativo

Responsable de la gestión administrativa de la clínica.

Podrá gestionar:

- Pacientes.
- Citas.
- Contactos.
- Empleados.
- Departamentos.
- Servicios.
- Habitaciones.

### Médico

Responsable de la atención sanitaria de los pacientes.

Podrá:

- Consultar información de pacientes.
- Gestionar consultas.
- Registrar diagnósticos.
- Registrar patologías diagnosticadas.
- Emitir recetas.
- Consultar medicamentos.
- Consultar sus citas y especialidades.

### Responsable de la clínica

Usuario encargado de tareas de supervisión y administración general.

Podrá consultar y gestionar:

- Empleados.
- Departamentos.
- Servicios.
- Habitaciones.
- Relaciones de supervisión entre empleados.

---

# 4. Catálogo de requisitos

## 4.1. Requisitos funcionales

### R.F.01. Gestionar pacientes

Como personal administrativo quiero registrar y actualizar pacientes para mantener actualizada la información de las personas atendidas por la clínica.

**Prueba de aceptación**

- Se debe poder registrar un nuevo paciente.
- Se debe poder modificar sus datos personales.
- Se debe poder consultar la información de un paciente.
- El paciente debe quedar asociado a una persona existente.
- Se debe aplicar la regla de negocio R.N.01.

### R.F.02. Gestionar contactos

Como personal administrativo quiero registrar los datos de contacto de una persona para poder localizarla mediante diferentes medios.

**Prueba de aceptación**

- Se debe poder registrar un contacto.
- Se debe indicar el tipo de contacto.
- Se debe almacenar su valor.
- Una persona puede tener varios contactos.
- Se debe aplicar la regla de negocio R.N.02.

### R.F.03. Gestionar empleados y departamentos

Como responsable de la clínica quiero gestionar empleados y departamentos para mantener organizada la estructura de la clínica.

**Prueba de aceptación**

- Se debe poder registrar un empleado.
- Cada empleado debe pertenecer a un departamento.
- Se debe poder consultar los empleados de un departamento.
- Se debe poder consultar la información de cada departamento.
- Se debe aplicar la regla de negocio R.N.03.

### R.F.04. Gestionar médicos y especialidades

Como responsable de la clínica quiero registrar las especialidades de los médicos para conocer las áreas médicas que puede cubrir cada profesional.

**Prueba de aceptación**

- Se debe poder registrar un médico.
- Se debe poder asociar un médico con una o varias especialidades.
- Se debe poder consultar los médicos de una especialidad.
- Se debe aplicar la regla de negocio R.N.04.

### R.F.05. Gestionar citas

Como personal administrativo quiero registrar y gestionar citas para organizar la atención de los pacientes.

**Prueba de aceptación**

- Se debe poder crear una cita.
- La cita debe indicar paciente, médico, fecha y hora.
- Se debe poder modificar el estado de una cita.
- Se debe poder cancelar una cita.
- Se debe evitar que un médico tenga dos citas simultáneas.
- Se debe aplicar la regla de negocio R.N.05.

### R.F.06. Registrar consultas

Como médico quiero registrar las consultas realizadas a los pacientes para mantener constancia de la atención médica.

**Prueba de aceptación**

- Una consulta debe estar relacionada con un paciente y un médico.
- Se debe almacenar la fecha y hora de la consulta.
- Se deben poder almacenar observaciones.
- Una cita atendida puede generar una consulta.
- Se debe aplicar la regla de negocio R.N.06.

### R.F.07. Registrar diagnósticos

Como médico quiero registrar diagnósticos durante una consulta para mantener el historial médico del paciente.

**Prueba de aceptación**

- Una consulta puede tener uno o varios diagnósticos.
- Cada diagnóstico debe corresponder a una patología.
- Se debe poder almacenar la fecha del diagnóstico.
- Se debe poder consultar el diagnóstico de un paciente.
- Se debe aplicar la regla de negocio R.N.07.

### R.F.08. Gestionar recetas y medicamentos

Como médico quiero emitir recetas con uno o varios medicamentos para establecer el tratamiento de un paciente.

**Prueba de aceptación**

- Una consulta puede generar una o varias recetas.
- Una receta debe contener al menos un medicamento.
- Debe registrarse la dosis para cada medicamento prescrito.
- Debe registrarse la frecuencia de administración.
- Debe poder registrarse la duración del tratamiento.
- Se debe aplicar la regla de negocio R.N.08.

### R.F.09. Gestionar servicios y pruebas

Como responsable de la clínica quiero gestionar los servicios y pruebas ofrecidos para mantener actualizado el catálogo de prestaciones de la clínica.

**Prueba de aceptación**

- Se debe poder registrar un servicio.
- Un departamento debe poder ofrecer uno o varios servicios.
- Un servicio puede incluir una o varias pruebas.
- Se debe poder consultar las pruebas incluidas en un servicio.
- Se debe aplicar la regla de negocio R.N.09.

### R.F.10. Gestionar habitaciones

Como personal administrativo quiero gestionar las habitaciones para conocer su disponibilidad y características.

**Prueba de aceptación**

- Se debe poder registrar una habitación.
- Se debe indicar su número, tipo y estado.
- Se debe poder consultar si una habitación está disponible.
- El precio por día debe depender del tipo de habitación.
- Se debe aplicar la regla de negocio R.N.10.

### R.F.11. Gestionar supervisión de empleados

Como responsable de la clínica quiero registrar qué empleados supervisan a otros para mantener la estructura jerárquica de la organización.

**Prueba de aceptación**

- Un empleado puede supervisar a varios empleados.
- Un empleado puede tener como máximo un supervisor.
- Un empleado no puede supervisarse a sí mismo.
- Se debe aplicar la regla de negocio R.N.11.

---

## 4.1.1. Requisitos de información

### R.I.01. Información de personas

Como usuario autorizado quiero almacenar los datos personales de las personas para identificar correctamente a pacientes y empleados.

**Prueba de aceptación**

- Se almacenará el identificador de la persona.
- Se almacenarán nombre, apellidos, DNI y fecha de nacimiento.
- El DNI identificará unívocamente a una persona.

### R.I.02. Información de pacientes

Como usuario autorizado quiero almacenar la información específica de los pacientes para gestionar su atención médica.

**Prueba de aceptación**

- Se almacenará el identificador del paciente.
- Se almacenará el número de historia clínica.
- Se podrán almacenar alergias y observaciones.
- Se registrará si el paciente necesita habitación.

### R.I.03. Información de contactos

Como usuario autorizado quiero almacenar diferentes medios de contacto para poder comunicarse con una persona.

**Prueba de aceptación**

- Un contacto tendrá un tipo.
- Un contacto tendrá un valor.
- Una persona podrá tener varios contactos.
- Se podrá identificar un contacto principal.

### R.I.04. Información de empleados

Como responsable de la clínica quiero almacenar la información laboral de los empleados para gestionar la plantilla.

**Prueba de aceptación**

- Se almacenará la fecha de alta.
- Se almacenará el salario.
- Se almacenará el estado laboral.
- Cada empleado pertenecerá a un departamento.

### R.I.05. Información de departamentos

Como responsable de la clínica quiero almacenar los departamentos para representar la organización interna.

**Prueba de aceptación**

- Cada departamento tendrá un identificador.
- Cada departamento tendrá nombre y descripción.

### R.I.06. Información de servicios y pruebas

Como responsable de la clínica quiero almacenar los servicios y pruebas disponibles para conocer la oferta sanitaria de la clínica.

**Prueba de aceptación**

- Cada servicio tendrá nombre, descripción y precio.
- Cada prueba tendrá nombre, descripción, precio y tipo.
- Se podrán asociar pruebas a servicios.

### R.I.07. Información de médicos y especialidades

Como usuario autorizado quiero conocer las especialidades de cada médico para poder gestionar correctamente las citas.

**Prueba de aceptación**

- Cada médico tendrá un número de colegiado.
- Un médico podrá tener una o varias especialidades.
- Una especialidad podrá corresponder a varios médicos.

### R.I.08. Información de citas

Como usuario autorizado quiero almacenar las citas para poder conocer cuándo será atendido cada paciente.

**Prueba de aceptación**

- Cada cita tendrá fecha y hora.
- Cada cita tendrá un estado.
- Se podrá almacenar un motivo y observaciones.
- Cada cita estará asociada a un paciente y un médico.

### R.I.09. Información de consultas y diagnósticos

Como médico quiero almacenar las consultas y diagnósticos realizados para mantener el historial médico del paciente.

**Prueba de aceptación**

- Una consulta almacenará fecha y hora.
- Una consulta podrá contener observaciones.
- Cada diagnóstico tendrá una descripción y una fecha.
- Cada diagnóstico estará relacionado con una patología.

### R.I.10. Información de recetas y medicamentos

Como médico quiero almacenar las recetas y medicamentos prescritos para conocer los tratamientos indicados.

**Prueba de aceptación**

- Cada receta tendrá una fecha.
- Se podrán almacenar observaciones.
- Cada medicamento tendrá nombre, forma farmacéutica y precio.
- Para cada medicamento prescrito se almacenará la dosis, frecuencia y duración.

### R.I.11. Información de habitaciones

Como usuario autorizado quiero almacenar la información de las habitaciones para controlar su disponibilidad.

**Prueba de aceptación**

- Cada habitación tendrá un número.
- Cada habitación tendrá un tipo.
- Cada habitación tendrá un estado.
- El precio diario será derivado del tipo de habitación.

### R.I.12. Información de supervisión

Como responsable de la clínica quiero conocer las relaciones de supervisión entre empleados para representar la estructura jerárquica.

**Prueba de aceptación**

- Se podrá identificar al supervisor.
- Se podrá identificar al empleado supervisado.
- Un empleado podrá supervisar a varios empleados.

---

## 4.1.2. Reglas de negocio

### R.N.01. Identificación única de personas

No pueden existir dos personas con el mismo DNI.

### R.N.02. Contacto principal

Una persona podrá tener varios contactos, pero como máximo uno podrá estar marcado como contacto principal para cada tipo de contacto.

### R.N.03. Pertenencia a un departamento

Todo empleado debe pertenecer a exactamente un departamento.

### R.N.04. Especialidad médica

Todo médico debe tener al menos una especialidad y una especialidad puede corresponder a varios médicos.

### R.N.05. Conflicto de citas

Un médico no puede tener dos citas diferentes a la misma fecha y hora.

### R.N.06. Consulta asociada a cita

Toda consulta registrada debe corresponder a una cita atendida.

### R.N.07. Diagnóstico válido

Todo diagnóstico debe estar asociado a una patología existente.

### R.N.08. Tratamiento completo

Toda línea de receta debe contener una dosis, una frecuencia y una duración válidas.

### R.N.09. Servicios y pruebas

Una prueba puede formar parte de varios servicios y puede existir independientemente de un servicio concreto.

### R.N.10. Precio de habitación

El precio diario de una habitación se obtiene a partir de su tipo de habitación y no se introduce manualmente.

### R.N.11. Supervisión

Un empleado puede supervisar a cero o más empleados, pero cada empleado podrá tener como máximo un supervisor. Un empleado no puede supervisarse a sí mismo.

### R.N.12. Habitaciones

Una habitación no puede estar asignada simultáneamente a dos pacientes diferentes.

---

## 4.2. Mapa de historias de usuario

### Épica 1. Gestión de personas

- HU01. Registrar persona.
- HU02. Registrar paciente.
- HU03. Registrar empleado.
- HU04. Gestionar contactos.

### Épica 2. Gestión sanitaria

- HU05. Gestionar médicos.
- HU06. Gestionar especialidades.
- HU07. Registrar consultas.
- HU08. Registrar diagnósticos.
- HU09. Gestionar patologías.
- HU10. Emitir recetas.
- HU11. Gestionar medicamentos.

### Épica 3. Gestión administrativa

- HU12. Gestionar citas.
- HU13. Gestionar departamentos.
- HU14. Gestionar servicios.
- HU15. Gestionar pruebas.
- HU16. Gestionar habitaciones.
- HU17. Gestionar supervisión de empleados.

---

## 4.3. Requisitos no funcionales

### R.N.F.01. Seguridad

Como usuario autorizado quiero acceder al sistema mediante mecanismos de autenticación y autorización para impedir el acceso de personas no autorizadas a la información de la clínica.

### R.N.F.02. Rendimiento

Como usuario quiero que las operaciones habituales de consulta y modificación se realicen en un tiempo reducido para trabajar de forma eficiente.

### R.N.F.03. Integridad

Como responsable de la clínica quiero que el sistema impida introducir información incoherente para mantener la calidad de los datos almacenados.

### R.N.F.04. Disponibilidad

Como usuario quiero que el sistema esté disponible durante el horario habitual de funcionamiento de la clínica para poder realizar las tareas de gestión.

-- fin entregable 1 --

# 5. Modelo conceptual

## 5.1. Diagramas de clases UML

El modelo conceptual se ha desarrollado mediante un diagrama de clases UML.

El modelo contiene las siguientes entidades principales:

- Persona
- Paciente
- Empleado
- Contacto
- Departamento
- Servicio
- Prueba
- Médico
- Especialidad
- Cita
- Consulta
- Diagnóstico
- Patología
- Receta
- Medicamento
- Línea de receta
- Habitación

También se utilizan los tipos enumerados:

- EstadoCita
- TipoContacto
- TipoPrueba
- FormaFarmaceutica
- TipoHabitacion
- EstadoHabitacion

El modelo incorpora asociaciones con multiplicidades, generalizaciones, composiciones, agregaciones, una asociación recursiva y una clase asociación.

![Modelo conceptual UML](./Modelado%20conceptual1.drawio.png)

### Generalización

La clase `Persona` se especializa en:

- `Paciente`
- `Empleado`

Esta clasificación es:

`{incompleta, solapada}`

Una persona puede no ser ni paciente ni empleado y, además, una misma persona puede desempeñar ambos roles.

### Composición

Se utilizan composiciones en aquellas relaciones en las que la parte depende de la existencia del todo.

Ejemplos:

- Persona ◆── Contacto
- Cita ◆── Consulta
- Consulta ◆── Receta

### Agregación

Se utiliza agregación cuando la parte puede existir independientemente del agregado.

Ejemplo:

- Servicio ◇── Prueba

Una prueba puede existir independientemente de un servicio y puede utilizarse en más de un servicio.

### Clase asociación

La relación entre `Receta` y `Medicamento` utiliza la clase asociación `LineaReceta`, ya que existen datos que dependen de una prescripción concreta:

- dosis
- frecuencia
- duración
- indicaciones

### Asociación recursiva

Los empleados pueden supervisar a otros empleados:

`Empleado (supervisor) ── supervisa ── Empleado (supervisado)`

### Restricciones

El modelo incluye restricciones que no pueden expresarse únicamente mediante relaciones gráficas, entre ellas:

- Un médico no puede tener dos citas simultáneas.
- Una persona no puede tener dos contactos principales del mismo tipo.
- Un empleado puede tener como máximo un supervisor.
- Un empleado no puede supervisarse a sí mismo.
- Una habitación no puede estar ocupada simultáneamente por dos pacientes.
- El precio diario de una habitación depende de su tipo.

---

## 5.2. Escenarios de prueba

### Escenario 1. Paciente solicita una cita y es atendido

Un paciente llamado Laura García está registrado en el sistema.

La paciente solicita una cita con el médico Carlos López, especialista en Cardiología.

La cita queda registrada con estado `CONFIRMADA`.

Posteriormente la paciente acude a la clínica y la cita pasa al estado `ATENDIDA`.

El médico registra una consulta asociada a dicha cita, indicando la fecha y hora y unas observaciones.

Durante la consulta se registra un diagnóstico de una patología previamente existente.

La consulta genera además una receta con dos medicamentos.

Para cada medicamento se registra una línea de receta con su dosis, frecuencia y duración.

Este escenario permite comprobar:

- Persona
- Paciente
- Médico
- Especialidad
- Cita
- Consulta
- Diagnóstico
- Patología
- Receta
- Medicamento
- LíneaReceta

### Escenario 2. Gestión de una habitación

El paciente necesita hospitalización.

El sistema consulta las habitaciones disponibles y localiza una habitación individual en estado `LIBRE`.

La habitación se asigna al paciente.

El estado de la habitación pasa a `OCUPADA`.

El precio diario de la habitación se obtiene automáticamente a partir del tipo `INDIVIDUAL`.

Cuando el paciente abandona la habitación, su estado pasa nuevamente a `LIBRE`.

### Diagrama de objetos UML

Para validar el escenario 1 se utilizará un diagrama de objetos UML mostrando, por ejemplo:

```text
lauraGarcia : Paciente
carlosLopez : Medico
cardiologia : Especialidad
cita101 : Cita
consulta101 : Consulta
diagnostico101 : Diagnostico
hipertension : Patologia
receta101 : Receta
linea1 : LineaReceta
medicamento1 : Medicamento
