## Departamentos

```sql
INSERT INTO gestion.departamentos (nombre_depto) VALUES 
('Desarrollo'), ('RRHH'), ('Ventas'), ('Marketing'), ('Soporte'), ('I+D'), ('Legal'), ('Finanzas'), 
('Logística'), ('Calidad'), ('Seguridad'), ('Diseño'), ('BI'), ('DevOps'), ('Cloud'), ('Mobile'), 
('UX/UI'), ('Data Science'), ('E-commerce'), ('Comunicaciones'), ('Auditoría'), ('Infraestructura'), 
('Sistemas'), ('Capacitación'), ('Compras'), ('Tesorería'), ('Fiscalía'), ('Prensa'), ('Innovación'), ('Strategy');

```

## Empleados

```sql
INSERT INTO gestion.empleados (nombre, id_depto) VALUES 
('Miguel Ramos', 1), ('Ana Pérez', 1), ('Luis Toro', 2), ('Carla Jara', 3), ('José Doe', 4),
('Elena Paz', 5), ('Mario Ross', 6), ('Julia Sans', 7), ('Pedro Via', 8), ('Sofía Luz', 9),
('Raúl Gil', 10), ('Inés Mar', 11), ('Hugo Rey', 12), ('Sara Sol', 13), ('Iván Rio', 14),
('Olga Van', 15), ('Kurt Cob', 16), ('Lana Del', 17), ('Mick Jag', 18), ('David Bo', 19),
('Juan Sin_Depto', NULL), ('Marta Libre', NULL), ('Lucas Solo', NULL), ('Dante Null', NULL), ('Beatriz N', NULL),
('Leo Dev', 1), ('Fanny Code', 1), ('Gaby QA', 10), ('Tom Data', 18), ('Rick Cloud', 15);

```