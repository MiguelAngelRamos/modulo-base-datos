## Diseño Final en 3FN

### Tabla 1: `departments`

| department_id | name          |
|---------------|---------------|
| 1             | Matemáticas   |
| 2             | Humanidades   |
| 3             | Ciencias       |

### Tabla 2: `professors`

| professor_id | professor_code | full_name     | email                 | department_id |
|--------------|----------------|---------------|-----------------------|---------------|
| 1            | PROF-2024-001  | Dr. López     | lopez@academia.edu    | 1             |
| 2            | PROF-2024-002  | Dra. Ruiz     | ruiz@academia.edu     | 1             |
| 3            | PROF-2024-003  | Prof. Vargas  | vargas@academia.edu   | 2             |

### Tabla 3: `courses`

| course_id | course_code | name     | credits | professor_id |
|-----------|-------------|----------|---------|--------------|
| 1         | MATH-101    | Álgebra  | 3       | 1            |
| 2         | MATH-102    | Cálculo  | 4       | 2            |
| 3         | HUM-101     | Historia | 3       | 3            |

### Tabla 4: `students`

| student_id | student_code | full_name    | email             | city   |
|------------|--------------|--------------|-------------------|--------|
| 1          | EST-2024-001 | María García | maria@uni.edu     | Madrid |
| 2          | EST-2024-002 | Carlos Soto  | carlos@uni.edu    | Madrid |
| 3          | EST-2024-003 | Ana Torres   | ana@uni.edu       | Lima   |

### Tabla 5: `enrollments`

| enrollment_id | student_id | course_id | enrollment_date | grade |
|---------------|------------|-----------|-----------------|-------|
| 1             | 1          | 1         | 2024-03-01      | 88    |
| 2             | 1          | 2         | 2024-03-01      | 92    |
| 3             | 2          | 1         | 2024-03-01      | 75    |
| 4             | 2          | 3         | 2024-03-01      | 80    |
| 5             | 3          | 2         | 2024-03-01      | 95    |

---