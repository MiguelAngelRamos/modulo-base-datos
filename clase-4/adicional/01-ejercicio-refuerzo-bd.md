```sql
CREATE DATABASE empresa_db;

CREATE SCHEMA gestion;

CREATE TABLE gestion.departamentos (
    id_depto SERIAL PRIMARY KEY,
    nombre_depto VARCHAR(100) NOT NULL
);

CREATE TABLE gestion.empleados (
    id_empleado SERIAL PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    id_depto INT,
    CONSTRAINT fk_departamento FOREIGN KEY (id_depto) REFERENCES gestion.departamentos(id_depto)
);

```