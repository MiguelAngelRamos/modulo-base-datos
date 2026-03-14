## HAPPY PATH

```sql
DO $$
BEGIN
  -- Descontar stock
  UPDATE tienda.productos SET stock = stock - 2 WHERE producto_id = 1;
  -- Registrar venta
  INSERT INTO tienda.ventas (producto_id, cantidad) VALUES (1, 2);
  -- Vendemos 2 unidades del producto con id 1
 
  -- Si las 2 operaciones anteriores se ejecutan correctamente, se hará un COMMIT automáticamente. es implicito, no es necesario escribirlo.
  RAISE NOTICE 'Venta registrada correctamente';
 
EXCEPTION
  WHEN OTHERS THEN
    -- Si ocurre cualquier error, se hará un ROLLBACK automáticamente. es implicito, no es necesario escribirlo.
    RAISE NOTICE 'Error: % - se deshizo todo.', SQLERRM;
    -- EL SQLERRM es una variable que contiene el mensaje de error específico que ocurrió.
END;
$$ LANGUAGE plpgsql;
 
-- DENTRO DE UN BLOQUE ANONIMO DO NO VA EL COMMIT EXPLICITO TAMPOCO EL ROLLBACK SE HACE DE FORMA IMPLICITA SI SE EJECUTA CORRECTAMENTE EL CODIGO SE HACE UN COMMIT SI HAY UN ERROR SE HACE UN ROLLBACK
 
SELECT * FROM tienda.productos WHERE producto_id = 1;
```

## CON ERROR:

```sql
DO $$
BEGIN
  -- Descontar stock
  UPDATE tienda.productos SET stock = stock - 1 WHERE producto_id = 1000;
  -- Registrar venta
  INSERT INTO tienda.ventas (producto_id, cantidad) VALUES (1000, 2);
 
  -- Si las 2 operaciones anteriores se ejecutan correctamente, se hará un COMMIT automáticamente. es implicito, no es necesario escribirlo.
  RAISE NOTICE 'Esto no se imprime si hay error arriba';
 
EXCEPTION
  WHEN foreign_key_violation THEN
    -- Si ocurre cualquier error, se hará un ROLLBACK automáticamente. es implicito, no es necesario escribirlo.
    RAISE NOTICE 'Error: el producto no existe. No se registro nada.';
    -- EL SQLERRM es una variable que contiene el mensaje de error específico que ocurrió.
  WHEN OTHERS THEN
    RAISE NOTICE 'Error: % - se deshizo todo.', SQLERRM;
END;
$$ LANGUAGE plpgsql;
```