# Transacciones en PostgreSQL

## ¿Que problema resuelven las transacciones?

- Sofia deposita $10000 pesos a Catalina
- Sofia se le descuenta los $10000 de su saldo
- Catalina aumenta su saldo en $10000 pesos

- Imagina que estas en app de banco y realizas estas dos cosas:

1.  Descontar $10000 de la cuenta de Sofia
2.  Acreditar $10000 en la cuenta de Catalina

Que pasa si el servidor se cae **entre el paso 1 y paso 2**

-> La cuenta de Sofia ya perdio $10000
-> La cuenta de Catalina nunca los recibio
-> El dinero desapareció.

Entonces este es exactamente el problema que resuelven las transacciones **asegurar que un conjunto de operaciones se ejecute con exito o no se ejecute ninguna**

## Definicion Simple

>Una **transaccion** es un bloque de operaciones SQL que se tratan como una unidadd, O todas tienen exito, o ninguna se aplica.

No hay cosas a medias. la base de datos siempre queda en estado consistente.


## CODIGO SQL 

```sql

-- Aqui iran tus operaciones
  INSERT INTO usuarios...
  INSERT INTO roles ...
  INSERT INTO atenciones ...

```
```sql
BEGIN; -- "Empieza a grabar todo lo que se haga desde este punto llamado BEGIN"

-- Aqui iran tus operaciones
  INSERT INTO usuarios...
  INSERT INTO roles ...
  INSERT INTO atenciones ...

COMMIT; -- "todo sale bien (happy path) los cambios se aplican"

``` 

## ROLLBACK

```sql
BEGIN;
  -- Aqui iran tus operaciones
    INSERT INTO usuarios...
    INSERT INTO roles ...
    INSERT INTO atenciones ...
ROLLBACK;

```

## USO PRACTICO DE ROLLBACK

```sql

BEGIN;
    DELETE FROM mascotas;
    SELECT * FROM mascotas;
ROLLBACK;

```