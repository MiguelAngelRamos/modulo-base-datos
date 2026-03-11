```sql

SELECT COUNT(*) AS total_users FROM users;

SELECT
	first_name, 
	last_name, 
	last_connection 
FROM 
	users 
WHERE 
	last_connection LIKE '221.%.%.%';

-- toda la informacion
SELECT * FROM users;

-- Obtener el nombre, apellido y cantidad de seguidores (followers) que esten entre mayor o igual a 4600 y menor o igual a 4700
-- >=  <=
SELECT 
  first_name, 
  last_name, 
  followers 
FROM users
WHERE followers >= 4600 AND followers <= 4700
ORDER BY followers DESC;

--* 4600 se incluye y se incluye 4700 es decir se consideran los extremos.

SELECT 
  first_name, 
  last_name, 
  followers 
FROM users
WHERE followers BETWEEN 4600 AND 4700
ORDER BY followers DESC;

-- follwers de los usuarios
SELECT COUNT(*) as Total_users, MIN(followers) FROM users; -- FAIL NO LOGRE SABER CUANTOS SON LOS USUARIOS CON LA CANTIDAD MINIMA DE SEGUIDORES

SELECT MIN(followers) FROM users; -- LA MININA CANTIDAD DE SEGUIDORES es 4
SELECT MAX(followers) FROM users; -- LA MAXIMA CANTIDAD DE SEGUIDORES es 4999

-- CONSULTAS COMPUESTAS 
SELECT  
  first_name, 
  last_name,
  followers
FROM users
WHERE followers = (SELECT MIN(followers) FROM users);

-- AHORA YA NO TENEMOS UN FAIL LO HEMOS LOGRADO YA SABEMOS QUIEN ES EL USUARIO CON LA CANTIDAD MINIMA DE SEGUIDORES Y LA MAXIMA CANTIDAD DE SEGUIDORES, DE FORMA DINAMICA GRACIAS A LAS CONSULTAS COMPUESTAS

SELECT  
  first_name, 
  last_name,
  followers
FROM users
WHERE followers = (SELECT MAX(followers) FROM users);

```