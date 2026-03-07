```sql
CREATE DATABASE libreria_test;
 
-- Esquema de la base de datos
CREATE SCHEMA libreria;
 
--  usuarios
CREATE TABLE libreria.usuarios (
  usuario_id INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
  nombre VARCHAR(100) NOT NULL
);
-- CON UN SEED "SEMILLA " EL AUTOINCREMENTAL
-- CREATE TABLE libreria.usuarios (
--   usuario_id INT GENERATED ALWAYS AS IDENTITY (START WITH 100 INCREMENT BY 1) PRIMARY KEY,
--   nombre VARCHAR(100) NOT NULL
-- );
 
 
CREATE TABLE libreria.libros (
  libro_id INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
  titulo VARCHAR(200) NOT NULL,
  autor VARCHAR(150) NOT NULL
);
 
SELECT * FROM libreria.libros;
 
--
CREATE TABLE libreria.prestamos(
  prestamo_id INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
  libro_id INT NOT NULL,
  usuario_id INT NOT NULL,
  fecha_prestamo DATE NOT NULL,
  CONSTRAINT fk_prestamos_libros FOREIGN KEY (libro_id) REFERENCES libreria.libros(libro_id),
  CONSTRAINT fk_prestamos_usuarios FOREIGN KEY (usuario_id) REFERENCES libreria.usuarios(usuario_id)
);
 
-- INSERT INTO
INSERT INTO libreria.usuarios (nombre) VALUES ('Ana Pérez');
INSERT INTO libreria.usuarios (nombre) VALUES ('Juan López');
INSERT INTO libreria.usuarios (nombre) VALUES ('María Gómez');
 
SELECT * FROM libreria.usuarios;
 
INSERT INTO libreria.libros (titulo, autor) VALUES
    ('Cien Años de Soledad', 'Gabriel García Márquez'),
    ('El Señor de los Anillos', 'J.R.R. Tolkien'),
    ('1984', 'George Orwell'),
    ('El Principito', 'Antoine de Saint-Exupéry');
 
SELECT * FROM libreria.libros;
 
INSERT INTO libreria.prestamos (libro_id, usuario_id, fecha_prestamo) VALUES
    (1, 1, '2024-03-01'),
    (3, 2, '2024-03-05'),
    (2, 3, '2024-03-10');
 
 
 
--  usuarios
-- CREATE TABLE libreria.usuarios (
--   usuario_id INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
--   nombre VARCHAR(100) NOT NULL
-- );
 
SELECT * FROM libreria.prestamos;
```