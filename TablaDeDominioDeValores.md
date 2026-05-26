# Tabla de Dominio de Valores

A continuación se presentan las tablas de dominio de valores estructuradas para su documentación técnica.

## 1. Tabla: DEPARTAMENTOS

| Atributo | Tipo de Dato (Oracle) | ¿Admite Nulos? | Dominio de Valores / Restricciones Lógicas |
| :--- | :--- | :--- | :--- |
| **DEPT_NO** | `NUMBER(2)` | NO (PK) | Números enteros positivos de solo dos dígitos. Clave Primaria. |
| **DNOMBRE** | `VARCHAR2(14)` | SÍ | Cadena de caracteres alfanuméricos de longitud variable (máximo 14 caracteres). |
| **LOC** | `VARCHAR2(14)` | SÍ | Cadena de caracteres alfanuméricos de longitud variable (máximo 14 caracteres). Ciudad o sede donde se ubica dicho departamento. |

---

## 2. Tabla: PRESUPUESTO

| Atributo | Tipo de Dato (Oracle) | ¿Admite Nulos? | Dominio de Valores / Restricciones Lógicas |
| :--- | :--- | :--- | :--- |
| **ANIO** | `NUMBER(4)` | NO (PK) | Clave Primaria Compuesta (PK). Indica el año del ejercicio presupuestario en formato de 4 dígitos. |
| **IMPORTE** | `NUMBER(10,2)` | NO | Valor numérico mayor que 0. Cuantía del presupuesto anual expresado en miles de euros. |

---

## 3. Tabla: EMPLEADO

| Atributo | Tipo de Dato (Oracle) | ¿Admite Nulos? | Dominio de Valores / Restricciones Lógicas |
| :--- | :--- | :--- | :--- |
| **EMP_NO** | `NUMBER(4)` | NO (PK) | Números enteros positivos de solo 4 dígitos. Identifica de forma única a cada trabajador. Clave Primaria. |
| **APELLIDO** | `VARCHAR2(10)` | SÍ | Cadena de caracteres (máximo 10). Primer apellido del empleado en mayúsculas. Restricción `UNIQUE` (no se pueden repetir apellidos en el sistema). |
| **OFICIO** | `VARCHAR2(10)` | SÍ | Cadena de caracteres alfanuméricos (máximo 10). Puesto o categoría profesional del trabajador (Ej: 'DIRECTOR', 'EMPLEADO', 'VENDEDOR'). |
| **DIR** | `NUMBER(4)` | NO | Números enteros positivos de 4 dígitos. Código del jefe directo del empleado. Clave Foránea (`FK`), debe existir previamente en `EMP_NO`. |
| **FECHA_ALT** | `DATE` | SÍ | Fecha completa (Día, Mes, Año) en la que el empleado ingresó en la empresa. |
| **SALARIO** | `NUMBER(7,2)` | SÍ | Número entero positivo. Representa el salario mensual expresado en pesetas. |
| **COMISION** | `NUMBER(7,2)` | SÍ | Número entero positivo. Representa los ingresos extra por ventas en pesetas. Admite valores nulos si el oficio no comisiona. |
| **TIPO** | `VARCHAR2(30)` | SÍ | Restricción Check: El tipo de empleado debe ser únicamente 'COORDINADOR', 'TESORERO' o nulo (ninguno), pero nunca ambos a la vez. |