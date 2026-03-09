## Estos son los Insert de la base de datos del ejercicio 02 (DATA)


### Géneros (20 Registros)

```SQL
INSERT INTO library.genres (name) VALUES
  ('Ficción'),
  ('No ficción'),
  ('Ciencia'),
  ('Historia'),
  ('Fantasía'),
  ('Biografía'),
  ('Misterio'),
  ('Romance'),
  ('Aventura'),
  ('Filosofía'),
  ('Arte'),
  ('Economía'),
  ('Poesía'),
  ('Teatro'),
  ('Humor'),
  ('Autoayuda'),
  ('Política'),
  ('Psicología'),
  ('Tecnología'),
  ('Naturaleza');
```

## Autores (20 Registros)

```sql
INSERT INTO library.authors (author_code, full_name, nationality) VALUES
  ('AUT-001', 'Gabriel García Márquez',  'Colombiana'),
  ('AUT-002', 'Isabel Allende',           'Chilena'),
  ('AUT-003', 'Mario Vargas Llosa',       'Peruana'),
  ('AUT-004', 'Jorge Luis Borges',        'Argentina'),
  ('AUT-005', 'Julio Cortázar',           'Argentina'),
  ('AUT-006', 'Carlos Fuentes',           'Mexicana'),
  ('AUT-007', 'Laura Esquivel',           'Mexicana'),
  ('AUT-008', 'Pablo Neruda',             'Chilena'),
  ('AUT-009', 'Octavio Paz',              'Mexicana'),
  ('AUT-010', 'Arturo Pérez-Reverte',    'Española'),
  ('AUT-011', 'Stephen King',             'Estadounidense'),
  ('AUT-012', 'J.K. Rowling',             'Británica'),
  ('AUT-013', 'George Orwell',            'Británica'),
  ('AUT-014', 'Albert Camus',             'Francesa'),
  ('AUT-015', 'Franz Kafka',              'Checa'),
  ('AUT-016', 'Fiódor Dostoyevski',       'Rusa'),
  ('AUT-017', 'León Tolstói',             'Rusa'),
  ('AUT-018', 'Ernest Hemingway',         'Estadounidense'),
  ('AUT-019', 'Virginia Woolf',           'Británica'),
  ('AUT-020', 'Chimamanda Ngozi Adichie', 'Nigeriana');
```

## Libros (25 Registros)

```sql
INSERT INTO library.books (isbn, title, published_year, genre_id, author_id) VALUES
  ('ISBN-001', 'Cien años de soledad',               1967,  1,  1),
  ('ISBN-002', 'La casa de los espíritus',            1982,  1,  2),
  ('ISBN-003', 'La ciudad y los perros',              1962,  1,  3),
  ('ISBN-004', 'El aleph',                            1949,  1,  4),
  ('ISBN-005', 'Rayuela',                             1963,  1,  5),
  ('ISBN-006', 'El coronel no tiene quien le escriba',1961,  7,  1),
  ('ISBN-007', 'Como agua para chocolate',            1989,  8,  7),
  ('ISBN-008', 'Veinte poemas de amor',               1924, 13,  8),
  ('ISBN-009', 'El laberinto de la soledad',          1950, 10,  9),
  ('ISBN-010', 'El capitán Alatriste',                1996,  9, 10),
  ('ISBN-011', 'It',                                  1986,  5, 11),
  ('ISBN-012', 'Harry Potter y la piedra filosofal',  1997,  5, 12),
  ('ISBN-013', '1984',                                1949, 17, 13),
  ('ISBN-014', 'El extranjero',                       1942, 10, 14),
  ('ISBN-015', 'La metamorfosis',                     1915,  1, 15),
  ('ISBN-016', 'Crimen y castigo',                    1866,  7, 16),
  ('ISBN-017', 'Anna Karenina',                       1878,  8, 17),
  ('ISBN-018', 'El viejo y el mar',                   1952,  9, 18),
  ('ISBN-019', 'La señora Dalloway',                  1925,  1, 19),
  ('ISBN-020', 'Americanah',                          2013,  1, 20),
  ('ISBN-021', 'Ficciones',                           1944,  1,  4),
  ('ISBN-022', 'Bestiario',                           1951,  1,  5),
  ('ISBN-023', 'Rebelión en la granja',               1945, 17, 13),
  ('ISBN-024', 'Guerra y paz',                        1869,  4, 17),
  ('ISBN-025', 'La tabla de Flandes',                 1990,  7, 10);
```

## Socios (Members 25 registros)

```sql
INSERT INTO library.members (member_code, full_name, email, joined_date) VALUES
  ('SOC-001', 'Ana González',     'ana.gonzalez@email.com',     '2024-01-15'),
  ('SOC-002', 'Carlos Pérez',     'carlos.perez@email.com',     '2024-02-20'),
  ('SOC-003', 'María Torres',     'maria.torres@email.com',     '2024-03-10'),
  ('SOC-004', 'Luis Rodríguez',   'luis.rodriguez@email.com',   '2024-03-25'),
  ('SOC-005', 'Carmen Sánchez',   'carmen.sanchez@email.com',   '2024-04-05'),
  ('SOC-006', 'Roberto Díaz',     'roberto.diaz@email.com',     '2024-04-18'),
  ('SOC-007', 'Patricia López',   'patricia.lopez@email.com',   '2024-05-02'),
  ('SOC-008', 'Jorge Martínez',   'jorge.martinez@email.com',   '2024-05-14'),
  ('SOC-009', 'Isabel Hernández', 'isabel.hernandez@email.com', '2024-06-01'),
  ('SOC-010', 'Miguel García',    'miguel.garcia@email.com',    '2024-06-20'),
  ('SOC-011', 'Laura Jiménez',    'laura.jimenez@email.com',    '2024-07-08'),
  ('SOC-012', 'Andrés Morales',   'andres.morales@email.com',   '2024-07-22'),
  ('SOC-013', 'Sofía Castro',     'sofia.castro@email.com',     '2024-08-05'),
  ('SOC-014', 'Diego Vargas',     'diego.vargas@email.com',     '2024-08-19'),
  ('SOC-015', 'Valentina Ramos',  'valentina.ramos@email.com',  '2024-09-03'),
  ('SOC-016', 'Sebastián Cruz',   'sebastian.cruz@email.com',   '2024-09-17'),
  ('SOC-017', 'Daniela Flores',   'daniela.flores@email.com',   '2024-10-01'),
  ('SOC-018', 'Mateo Moreno',     'mateo.moreno@email.com',     '2024-10-15'),
  ('SOC-019', 'Camila Ortega',    'camila.ortega@email.com',    '2024-11-02'),
  ('SOC-020', 'Alejandro Reyes',  'alejandro.reyes@email.com',  '2024-11-20'),
  ('SOC-021', 'Fernanda Núñez',   'fernanda.nunez@email.com',   '2025-01-10'),
  ('SOC-022', 'Nicolás Vega',     'nicolas.vega@email.com',     '2025-02-14'),
  ('SOC-023', 'Gabriela Mendoza', 'gabriela.mendoza@email.com', '2025-03-01'),
  ('SOC-024', 'Ricardo Aguilar',  'ricardo.aguilar@email.com',  '2025-04-05'),
  ('SOC-025', 'Mariana Ruiz',     'mariana.ruiz@email.com',     '2025-05-20');
```

## Prestamos (loans - 20 Registros)


```sql
INSERT INTO library.loans (book_id, member_id, loan_date, due_date, return_date) VALUES
  ( 1,  1, '2026-01-05', '2026-01-19', '2026-01-18'),  -- devuelto a tiempo
  ( 2,  2, '2026-01-10', '2026-01-24', '2026-01-25'),  -- devuelto con retraso
  ( 3,  3, '2026-01-15', '2026-01-29', '2026-01-28'),  -- devuelto a tiempo
  ( 4,  4, '2026-01-20', '2026-02-03', '2026-02-03'),  -- devuelto en la fecha límite
  ( 5,  5, '2026-01-25', '2026-02-08', NULL),           -- ACTIVO
  ( 6,  6, '2026-02-01', '2026-02-15', '2026-02-14'),  -- devuelto
  ( 7,  7, '2026-02-05', '2026-02-19', NULL),           -- ACTIVO
  ( 8,  8, '2026-02-10', '2026-02-24', '2026-02-22'),  -- devuelto
  ( 9,  9, '2026-02-15', '2026-03-01', NULL),           -- ACTIVO
  (10, 10, '2026-02-20', '2026-03-06', NULL),           -- ACTIVO (vence hoy)
  (11,  1, '2026-02-22', '2026-03-08', NULL),           -- ACTIVO (2do préstamo de Ana)
  (12,  2, '2026-02-25', '2026-03-11', NULL),           -- ACTIVO (2do préstamo de Carlos)
  (13, 11, '2026-01-08', '2026-01-22', '2026-01-20'),  -- devuelto
  (14, 12, '2026-01-12', '2026-01-26', '2026-01-26'),  -- devuelto
  (15, 13, '2026-01-18', '2026-02-01', '2026-01-30'),  -- devuelto
  (16, 14, '2026-02-02', '2026-02-16', '2026-02-15'),  -- devuelto
  (17, 15, '2026-02-08', '2026-02-22', '2026-02-20'),  -- devuelto
  (18, 16, '2026-02-12', '2026-02-26', NULL),           -- ACTIVO
  (19, 17, '2026-02-18', '2026-03-04', NULL),           -- ACTIVO
  (20, 18, '2026-02-22', '2026-03-08', NULL);           -- ACTIVO

```