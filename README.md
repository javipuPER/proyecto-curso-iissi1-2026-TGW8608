# Proyecto IISSI-1: Sistema de Gestión para Servicio Sanitario Privado

## Miembros del grupo LX-XXX-X (sustituir)

1. Pérez Ulgar, Francisco Javier
2. Osuna de Alba, Alejandro
3. Sanchez Corujo, Ivan
4. Utrera Nieto, Leo

## 1. Introducción al problema

### Descripción del problema

*Hospital Quirónsalud Sagrado Corazón* es una entidad de asistencia sanitaria privada que ofrece consultas de atención primaria y especialidades médicas (Cardiología, Traumatología, Pediatría, etc.), así como pruebas diagnósticas.

Actualmente, la gestión de citas, el registro de historiales médicos, la asignación de consultas a los facultativos y la facturación de servicios (tanto a clientes privados como a mutualidades/aseguradoras) se realiza mediante procesos semiautomáticos y hojas de cálculo dispersas. Esta situación genera los siguientes problemas:
* **Falta de coordinación en agendas:** Duplicidad accidental de citas para un mismo médico o sala de consulta.
* **Tiempos de espera excesivos:** Ausencia de un control de disponibilidad en tiempo real para los pacientes.
* **Dificultad en el seguimiento clínico:** Dificultad para consultar el historial de consultas previas de un paciente de forma centralizada.
* **Gestión ineficiente de cobros:** Errores en la liquidación con las compañías aseguradoras médicas.

El objetivo del proyecto es desarrollar un Sistema de Información centralizado que permita gestionar eficientemente todo el ciclo de vida de la asistencia médica privada.

*(Se valorará la inclusión de diagramas, fotos o esquemas ilustrativos del flujo del centro médico).*
hay que meter modelado vaya

## 2. Glosario de términos

* **Aseguradora:** Compañía de seguros de salud privada que mantiene convenios con la clínica para cubrir el coste total o parcial de los servicios prestados a sus asegurados.
* **Cita Médica:** Reserva de una franja horaria en la que un paciente es atendido por un médico especialista en un centro o consulta concreta.
* **Consulta / Gabinete:** Espacio físico o sala asignada dentro de la clínica para llevar a cabo la atención al paciente o prueba médica.
* **Especialidad:** Rama de la medicina (ej. Dermatología, Oftalmología) en la que está acreditado un médico.
* **Factura:** Documento emitido por la clínica tras la prestación de un servicio, dirigido al paciente privado o a su entidad aseguradora.
* **Historial:** Registro de los diagnósticos, recetas, observaciones y tratamientos aplicados a un paciente durante una cita.
* **Médico:** Profesional sanitario colegiado contratado por la clínica para prestar servicios médicos.
* **Paciente:** Usuario receptor de los servicios sanitarios del centro, el cual puede ser privado o estar cubierto por una aseguradora.

## 3. Visión general del sistema

### 3.1. Requisitos generales

El sistema debe permitir gestionar de forma integral el flujo de atención en la clínica privada, abarcando desde el alta de personal médico y pacientes, la programación y gestión de citas en tiempo real, hasta la generación de informes clínicos y el registro de la facturación derivada de cada consulta.

### 3.2. Usuarios del sistema

### Usuarios del sistema

1. **Administrador del Centro:**
   * Gestiona el cuadro médico (médicos, especialidades y horarios de trabajo).
   * Gestiona la estructura física del centro (consultas disponibles).
   * Configura las tarifas y acuerdos con aseguradoras médicas.
2. **Personal de Recepción / Admisión:**
   * Alta y modificación de datos de Pacientes.
   * Agendamiento, modificación y cancelación de citas médicas.
   * Registro de llegada de pacientes a la sala de espera.
   * Emisión de facturas y cobro de consultas privadas.
3. **Médico:**
   * Consulta de su agenda diaria/semanal de citas.
   * Registro del informe clínico de la consulta (diagnóstico, receta, observaciones).
   * Solicitud de pruebas diagnósticas complementarias.
4. **Paciente (Cliente):**
   * Acceso a su portal privado para consultar su historial de citas.
   * Solicitud de citas online según especialidad, médico o fecha.
   * Descarga de facturas e informes de salud.

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Gestión y reserva de citas médicas

Como Paciente  
quiero consultar la agenda de huecos libres y solicitar una cita con un médico  
para ser atendido en la especialidad y fecha requeridas.

**Prueba de aceptación**
- El paciente selecciona la especialidad, el médico deseado y la fecha. El sistema muestra los huecos de tiempo disponibles.
- El paciente confirma la reserva y la cita pasa al estado *Programada*.
- Se debe aplicar la regla de negocio R.N.01 (Ausencia de solape en agenda del médico).
- Se debe aplicar la regla de negocio R.N.02 (Disponibilidad de la consulta/sala).

#### R.F.02. Registro de llegada de pacientes en recepción

Como Personal de Recepción  
quiero marcar la llegada de un paciente citado  
para notificar al médico que el paciente se encuentra en la sala de espera.

**Prueba de aceptación**
- El recepcionista busca la cita del día mediante el DNI del paciente y cambia su estado a *En Espera*.
- La pantalla de la agenda del médico se actualiza mostrando qué pacientes han llegado a la sala de espera.

#### R.F.03. Cumplimentación de informes clínicos

Como Médico  
quiero registrar el diagnóstico, tratamiento y prescripción de medicamentos tras la consulta  
para mantener actualizado el historial clínico del paciente.

**Prueba de aceptación**
- El médico abre la cita desde su agenda diaria y redacta el informe clínico.
- Al guardar el informe, la cita cambia automáticamente al estado *Realizada*.
- Se debe aplicar la regla de negocio R.N.04 (Obligatoriedad de informe clínico).

#### R.F.04. Cancelación de citas médicas

Como Paciente  
quiero solicitar la cancelación de una cita previamente reservada  
para liberar el hueco en caso de no poder asistir.

**Prueba de aceptación**
- El paciente selecciona una cita programada y confirma la cancelación.
- El sistema cambia el estado de la cita a *Cancelada* y libera la franja horaria.
- Se debe aplicar la regla de negocio R.N.03 (Antelación mínima de cancelación).

#### 4.1.1. Requisitos de información

##### R.I.01. Registro y consulta de información de pacientes

Como Personal de Recepción  
quiero almacenar y consultar la ficha personal y administrativa de los pacientes  
para identificar sus datos de contacto y su cobertura sanitaria.

**Prueba de aceptación**
- El sistema guarda DNI/NIE (identificador único), nombre, apellidos, fecha de nacimiento, teléfono, correo electrónico, dirección y datos de la aseguradora (compañía y número de póliza, si aplica).
- Permite buscar un paciente por DNI o apellidos para verificar o modificar su información.

##### R.I.02. Gestión de cuadro médico y especialidades

Como Administrador del Centro  
quiero mantener actualizada la información de los facultativos y las especialidades que ofertan  
para organizar las agendas del centro.

**Prueba de aceptación**
- El sistema guarda el número de colegiado (único), nombre, apellidos, teléfono, correo electrónico, especialidades médicas en las que está acreditado y la tarifa base por consulta.
- Se puede dar de alta a un nuevo médico asociándole al menos una especialidad válida.

##### R.I.03. Almacenamiento de historiales e informes clínicos

Como Médico  
quiero almacenar los registros médicos generados en cada atención  
para disponer de un histórico clínico detallado por cada paciente.

**Prueba de aceptación**
- Cada informe queda vinculado obligatoriamente a una Cita y a un Paciente.
- Se almacena la fecha de la consulta, motivo de consulta, diagnóstico principal, tratamiento recomendado, medicamentos recetados y observaciones privadas.

##### R.I.04. Registro y control de facturación de consultas

Como Personal de Recepción  
quiero emitir e inspeccionar la facturación resultante de los servicios sanitarios  
para llevar el control de los cobros a particulares y aseguradoras.

**Prueba de aceptación**
- Se guarda el número de factura, fecha de emisión, importe total, estado de pago (*Pendiente, Pagado, Facturado a Aseguradora*) y el concepto/servicio prestado.
- Se vincula la factura con el paciente o con la entidad aseguradora según la modalidad de pago.

#### 4.1.2. Reglas de negocio

##### R.N.01. Ausencia de solape en la agenda del médico
Un médico no puede tener dos citas programadas a la misma fecha y hora, ni en franjas temporales que se solapen dentro de su horario laboral.

##### R.N.02. Disponibilidad de la consulta/sala física
Una sala o gabinete de consulta no puede ser asignada a más de un médico dentro de la misma franja horaria.

##### R.N.03. Antelación mínima para cancelación de citas
Un paciente solo podrá cancelar una cita con un mínimo de 24 horas de antelación respecto a la hora fijada para la consulta. Pasado dicho plazo, la cita no podrá ser cancelada de forma automática desde el portal.

##### R.N.04. Obligatoriedad de informe clínico
Una cita médica no puede ser marcada con el estado de *Realizada* ni archivada si el facultativo asignado no ha redactado y guardado previamente el correspondiente informe clínico.

##### R.N.05. Cobertura de aseguradora válida
Para que una cita pueda ser cubierta por una aseguradora de salud, el paciente debe tener registrado un número de póliza activo y la compañía aseguradora debe tener un convenio vigente con el centro para la especialidad requerida.

### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

**R.N.F. 01. Protección de datos de salud (Seguridad y Privacidad)**  
Como Administrador del Centro  
quiero que los datos médicos y los historiales estén cifrados y restringidos según el rol del usuario  
para cumplir con la normativa LOPDGDD y el Reglamento General de Protección de Datos (RGPD).

**R.N.F. 02. Disponibilidad y rendimiento del portal de citas**  
Como Paciente  
quiero que el portal responda a la búsqueda de citas libres en menos de 2 segundos  
para disponer de una experiencia de reserva fluida y sin interrupciones.

**R.N.F. 03. Integridad y persistencia de la información**  
Como Personal de Recepción  
quiero que las transacciones de reserva y cobro sean atómicas  
para evitar duplicidades de citas o incoherencias en los registros del sistema.

-- fin entregable 1 --

## 5. Modelo conceptual

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


