```sql
CREATE TABLE libros (
	id 			SERIAL PRIMARY KEY,
	titulo  	VARCHAR(100) NOT NULL,
	autor       VARCHAR(100) NOT NULL,
	anio        INTEGER NOT NULL,
	disponible  BOOLEAN DEFAULT TRUE
);

-- CRUD CREATE, READ, UPDATED Y DELETE
-- Insertar datos (CREATE)
INSERT INTO libros(titulo, autor, anio, disponible) VALUES 
('Cien años de soledad', 'Gabriel García Márquez', 1967, TRUE);

INSERT INTO libros(titulo, autor, anio, disponible) VALUES 
('Don Quijote de la Mancha', 'Miguel de Cervantes', 1605, TRUE);

INSERT INTO libros(titulo, autor, anio, disponible) VALUES 
('El Señor de los Anillos', 'JRR Tolkien', 1954, FALSE);

INSERT INTO libros(titulo, autor, anio, disponible) VALUES 
('El Principito', 'Antonio de Saint-Seiya', 1954, TRUE);

INSERT INTO libros(titulo, autor, anio, disponible) VALUES 
('Harry Potter', 'J. K. Rowling', 1997, TRUE);

-- Consultar datos (READ)
SELECT * FROM libros;
SELECT * FROM libros WHERE disponible = TRUE;
SELECT * FROM libros WHERE disponible = FALSE;

-- Actualizar Datos (UPDATE)
UPDATE libros SET autor = 'Antoine de Saint-Exupéry' WHERE titulo='El Principito';

UPDATE libros SET anio = 1942 WHERE id=4;

-- Eliminacion DELETE 
DELETE FROM libros WHERE id=3;

```