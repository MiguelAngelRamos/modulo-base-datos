# Ejercicio — Sistema de Préstamos: `biblioteca_db`

> **Nivel:** Segunda clase de base de datos  
> **Objetivo:** Practicar DDL (CREATE TABLE) y todos los tipos de JOIN

---

## Contexto del negocio

La **Biblioteca Municipal de San Martín** necesita reemplazar sus hojas de cálculo por una base de datos relacional. El sistema debe registrar los géneros literarios, los autores, el catálogo de libros, los socios y el historial de préstamos.

**Base de datos:** `biblioteca_db`  
**Esquema:** `library`

---

## Diagrama de relaciones

```
library.genres            library.authors
──────────────            ───────────────────
genre_id  (PK)            author_id  (PK)
name                      author_code
                          full_name
      │                   nationality
      │ FK                      │ FK
      └───────────┬─────────────┘
                  ↓
           library.books
           ──────────────────
           book_id       (PK)
           isbn
           title
           published_year
           genre_id      (FK → genres)
           author_id     (FK → authors)
                  │
                  │ FK
                  ▼
library.members      library.loans
───────────────  ←── ──────────────────
member_id  (PK)      loan_id      (PK)
member_code          book_id      (FK → books)
full_name            member_id    (FK → members)
email                loan_date
joined_date          due_date
                     return_date   (NULL = no devuelto aún)
```

---

## Estructura de tablas

### `library.genres`
| Columna | Tipo | Restricciones |
|---------|------|---------------|
| `genre_id` | INT | PK, autoincremental |
| `name` | VARCHAR(100) | NOT NULL, UNIQUE |

### `library.authors`
| Columna | Tipo | Restricciones |
|---------|------|---------------|
| `author_id` | INT | PK, autoincremental |
| `author_code` | VARCHAR(20) | NOT NULL, UNIQUE |
| `full_name` | VARCHAR(150) | NOT NULL |
| `nationality` | VARCHAR(100) | — |

### `library.books`
| Columna | Tipo | Restricciones |
|---------|------|---------------|
| `book_id` | INT | PK, autoincremental |
| `isbn` | VARCHAR(20) | NOT NULL, UNIQUE |
| `title` | VARCHAR(200) | NOT NULL |
| `published_year` | INT | CHECK: debe ser mayor a 1800 |
| `genre_id` | INT | NOT NULL, FK → genres |
| `author_id` | INT | NOT NULL, FK → authors |

### `library.members`
| Columna | Tipo | Restricciones |
|---------|------|---------------|
| `member_id` | INT | PK, autoincremental |
| `member_code` | VARCHAR(20) | NOT NULL, UNIQUE |
| `full_name` | VARCHAR(150) | NOT NULL |
| `email` | VARCHAR(100) | NOT NULL, UNIQUE |
| `joined_date` | DATE | DEFAULT CURRENT_DATE |

### `library.loans`
| Columna | Tipo | Restricciones |
|---------|------|---------------|
| `loan_id` | INT | PK, autoincremental |
| `book_id` | INT | NOT NULL, FK → books |
| `member_id` | INT | NOT NULL, FK → members |
| `loan_date` | DATE | NOT NULL, DEFAULT CURRENT_DATE |
| `due_date` | DATE | NOT NULL, CHECK: debe ser posterior a `loan_date` |
| `return_date` | DATE | Puede ser NULL (libro aún prestado) |