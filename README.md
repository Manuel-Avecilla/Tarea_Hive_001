# Tarea_Hive_001

### Levantar el docker
```bash
docker compose up -d
```
### Parar el docker 
```bash
docker compose down -v
```

### Copiar los CSV al docker
```bash
docker cp ventas.csv hive-server:/tmp/
docker cp vendedores.csv hive-server:/tmp/
```

---

### Acceso a la terminal interna de hive-server
```bash
docker exec -it hive-server bash
```

### Desde la terminal de hive-server, conexion a hive
```bash
beeline -u jdbc:hive2://localhost:10000 -n root
```

---

### Tarea

1. Crear base de datos y preparar tablas 
Crea una base de datos llamada empresaDB.
Crea las tablas de ventas y vendedores asociadas a los archivos adjuntos


2. Consultas y análisis

Realiza las siguientes consultas en orden. Copia los resultados o toma capturas de pantalla de cada una.

    Total de ventas por categoría y región.
    Vendedor con mayor volumen total de ventas.
    Comparación entre la media de ventas por categoría y la media global.
    Unión (JOIN) entre vendedores y ventas para analizar ventas y salario por empleado.
    Ranking de vendedores por volumen total de ventas (usa funciones de ventana).
    Top 2 productos más vendidos por región.
    Comparativa entre los ingresos generados por cada vendedor y su salario (ratio ventas/salario).

3. Responde brevemente en el documento o formulario que te entregue el profesor/a:

    ¿Qué diferencia hay entre agrupar con GROUP BY y usar funciones de ventana (OVER)?
    ¿Qué ventajas aporta el uso de RANK() o ROW_NUMBER() en lugar de un LIMIT simple?
    Si una categoría concentra la mayoría de las ventas, ¿qué impacto podría tener en el rendimiento (data skewing)?
    ¿Cómo podrías particionar la tabla ventas para mejorar el rendimiento de las consultas?
    ¿Qué tipo de consultas se beneficiarían más de aplicar bucketing?