```sql
-- Ventas totales y promedio por país de origen del cliente
SELECT 
    c.country, 
    COUNT(s.id) AS cantidad_ventas,
    SUM(s.total_amount) AS venta_total,
    ROUND(AVG(s.total_amount), 2) AS promedio_por_venta
FROM electronica_store.customers c
INNER JOIN electronica_store.sales s ON c.id = s.customer_id
GROUP BY c.country
ORDER BY venta_total DESC;

-- Inventario: Valorización de stock por categoría

SELECT 
    cat.name AS categoria,
    COUNT(p.id) AS tipos_de_productos,
    SUM(p.stock) AS unidades_totales,
    SUM(p.stock * p.price) AS valor_inventario_total
FROM electronica_store.categories cat
LEFT JOIN electronica_store.products p ON cat.id = p.category_id
GROUP BY cat.name
ORDER BY valor_inventario_total DESC;

--  Filtro de Marcas "Premium" (Uso de HAVING)
SELECT 
    brand, 
    COUNT(id) AS cantidad_modelos,
    MIN(price) AS precio_entrada,
    MAX(price) AS precio_tope
FROM electronica_store.products
GROUP BY brand
HAVING MIN(price) > 300
ORDER BY precio_entrada ASC;

-- LEFT JOIN (Categorías y sus productos, incluso si no tienen)

SELECT 
    cat.name AS categoria, 
    p.name AS producto
FROM electronica_store.categories cat
LEFT JOIN electronica_store.products p ON cat.id = p.category_id;

-- INNER JOIN (Ventas con Nombres de Clientes)

SELECT 
    s.id AS sale_id, 
    c.full_name, 
    s.total_amount
FROM electronica_store.sales s
INNER JOIN electronica_store.customers c ON s.customer_id = c.id;

```