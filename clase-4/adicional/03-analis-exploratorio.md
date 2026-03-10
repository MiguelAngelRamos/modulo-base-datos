```sql
SELECT * FROM gestion.departamentos;
SELECT * FROM gestion.empleados;

-- 1. INNER JOIN (Solo muestra coincidencias)

SELECT e.nombre, d.nombre_depto FROM gestion.empleados e 
INNER JOIN gestion.departamentos d ON e.id_depto = d.id_depto;

-- 2. OBTENER CUANTOS EMPLEADOS QUE PERTENECEN A UN DEPARTAMENTO ESPECÍFICO
SELECT COUNT(*), d.nombre_depto
FROM gestion.empleados e 
INNER JOIN gestion.departamentos d ON e.id_depto = d.id_depto
GROUP BY d.nombre_depto
ORDER BY COUNT(*) DESC;

--  Vert todos los empleados y todos los departamentos, aunque no tengan relacion

SELECT e.nombre, d.nombre_depto FROM gestion.empleados e 
FULL JOIN gestion.departamentos d ON e.id_depto = d.id_depto;

SELECT COUNT(*) AS "Cantidad de Departamentos" FROM gestion.departamentos;
SELECT COUNT(*) AS "Cantidad de Empleados" FROM gestion.empleados;

-- LEFT JOIN (Todo de A = empleados(es la tabla de la izquierda) y B = departamentos (departamentos es la tabla de la derecha)
-- Todos los empleados, indicando su departamento (si tienen)
SELECT e.nombre, d.nombre_depto FROM gestion.empleados e
LEFT JOIN gestion.departamentos d ON e.id_depto = d.id_depto;

-- LEFT JOIN EXCLUSIVO
SELECT e.nombre, d.nombre_depto FROM gestion.empleados e
LEFT JOIN gestion.departamentos d ON e.id_depto = d.id_depto
WHERE d.id_depto IS NULL;

-- RIGHT JOIN (Todo lo B = departamentos (tabla de la derecha) y A = empleados (tabla de la izquierda)
--  Todos los departamentos, con sus empleados asignados
SELECT e.nombre, d.nombre_depto 
FROM gestion.empleados e
RIGHT JOIN gestion.departamentos d ON e.id_depto = d.id_depto;

-- La función COALESCE devuelve el primer valor no nulo de la lista de argumentos. En este caso, si e.nombre es nulo (lo que significa que no hay un empleado asignado al departamento), se mostrará 'Sin empleado' en su lugar.
SELECT COALESCE(e.nombre, 'Sin empleado') nombre, d.nombre_depto 
FROM gestion.empleados e
RIGHT JOIN gestion.departamentos d ON e.id_depto = d.id_depto;

SELECT e.nombre, d.nombre_depto 
FROM gestion.empleados e
RIGHT JOIN gestion.departamentos d ON e.id_depto = d.id_depto;

-- RIGHT JOIN EXCLUSIVO (Solo de B que no están en A)
SELECT COALESCE(e.nombre, 'Sin empleado') nombre, d.nombre_depto 
FROM gestion.empleados e
RIGHT JOIN gestion.departamentos d ON e.id_depto = d.id_depto
WHERE e.id_depto IS NULL;


``` 