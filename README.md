## 🧪 Prueba Técnica – API de Gestión de Atenciones Médicas

### ⏱ Duración:

* **2 días para desarrollo**


---

### 🎯 Objetivo:

Desarrollar una API REST para gestionar las atenciones médicas realizadas a pacientes en una clínica u hospital.

La evaluación busca observar:

* Dominio de .NET 8 (sin forzar stack específico)
* Buenas prácticas, arquitectura limpia y organización
* Uso de **servicios inyectables** (IService, DI nativo de .NET) cuando sea necesario
* Dominio de SQL Server (SPs, joins, relaciones, filtros)
* Capacidad de análisis y resolución en tiempo limitado
* Seguridad básica y documentación

---

## 📦 Requisitos Técnicos
### Frontend 
* Razor / Blazor  (.NET 8)
* Cubrir los módulos Pacientes y Doctores consumiendo la API protegida por API Key.
* CRUD completo para ambos modulos.

### Backend

* Lenguaje: C# (.NET 8)
* Arquitectura organizada (modular, capas, patrones si aplica)
* Código limpio, mantenible, comentado cuando sea necesario
* Exposición de endpoints RESTful
* Uso de Dapper (o similar) para consultas y SPs
* Implementación de **servicios (clases con lógica de negocio) inyectables** con el contenedor de DI de .NET

### Seguridad

* Los endpoints deben requerir autenticación por **API Key** (por header)

### Base de Datos

* SQL Server (se entregará un script `.sql` base)
* Puedes **crear tablas adicionales** si las consideras necesarias
* Puedes y debes **crear procedimientos almacenados** si aplican

### Documentación

* Swagger UI habilitado y funcional
* README con instrucciones de ejecución

### Testing

* Pruebas unitarias **opcionales**, pero valoradas si se incluyen (mínimo una capa)

---

## 🧱 Modelo de Dominio Inicial

Tablas entregadas:

* `Paciente(PacienteId, Nombre, RUT, FechaNacimiento)`
* `Doctor(DoctorId, Nombre, EspecialidadId)`
* `Especialidad(EspecialidadId, Nombre)`
* `Atencion(AtencionId, PacienteId, DoctorId, FechaHoraInicio, FechaHoraFin, Diagnostico)`

Puedes agregar más tablas si lo consideras útil para separar lógicas o relaciones.

---

## 🔧 Requerimientos Funcionales

### 1. Pacientes

* CRUD completo
* Buscar por RUT, nombre o rango de edad
* Validar que no se repita RUT

### 2. Doctores

* CRUD completo
* Relacionar con especialidades

### 3. Especialidades

* CRUD básico

### 4. Atenciones Médicas

* Registrar atención (doctor + paciente + diagnóstico + duración)
* Consultar atenciones por:

  * Fecha
  * Doctor
  * Paciente
  * Especialidad
* Obtener duración promedio de atenciones por especialidad
* Validar que una atención no se solape en el tiempo para un mismo doctor

---

## 📤 Entregables

1. Código fuente completo (idealmente en un solo repo)
2. Backup SQL o scripts para base de datos y objetos nuevos
3. Archivo `.http` o colección de Postman para probar los endpoints
4. README con:

   * Instrucciones de setup y ejecución
   * Explicación general del enfoque usado
   * Consideraciones especiales o decisiones técnicas

---
