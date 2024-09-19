
<table>
<tr>
    <td colspan=3 style="text-align: center; font-weight: bold;">
        DDL (Lenguaje de definición de datos)
    </td>
</tr>
<tr>
    <td style="font-weight: bold;">
        CREATE
    </td>
    <td>Crear tabla.</td>
    <td>
<pre><code>CREATE TABLE NombreTabla (
Columna1 INT PRIMARY KEY,
Columna2 VARCHAR(50),
Columna3 DATE
);</code></pre>
    </td>
</tr>
<tr>
    <td style="font-weight: bold;">
        ALTER
    </td>
    <td>
        Modificar tabla (añadir columna).
    </td>
    <td>
<pre><code>ALTER TABLE NombreTabla
ADD Columna4 BIT;
</code></pre>
    </td>
</tr>
<tr>
    <td style="font-weight: bold;">
        DROP
    </td>
    <td>
        Eliminar tabla.
    </td>
    <td>
<pre><code>DROP TABLE NombreTabla;
</code></pre>
    </td>
</tr>
  <tr>
    <td colspan=3 style="text-align: center;"><b>DML (Lenguaje de manipulación de datos)</b></td>
  </tr>
  <tr>
    <td><b>INSERT</b></td>
    <td>Insertar datos.</td>
    <td>
<pre><code>INSERT INTO NombreTabla (Columna1, Columna2, Columna3)
VALUES (1, 'Texto', '2024-09-16');
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>UPDATE</b></td>
    <td>Actualizar datos.</td>
    <td>
<pre><code>UPDATE NombreTabla
SET Columna2 = 'Nuevo Texto'
WHERE Columna1 = 1;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>DELETE</b></td>
    <td>Eliminar datos.</td>
    <td>
<pre><code>DELETE FROM NombreTabla
WHERE Columna1 = 1;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>SELECT</b></td>
    <td>Seleccionar datos (básico).</td>
    <td>
<pre><code>SELECT Columna1, Columna2
FROM NombreTabla;
</code></pre>
    </td>
  </tr>
  <tr>
    <td colspan=3 style="text-align: center;"><b>ALIAS</b></td>
  </tr>
  <tr>
    <td><b>AS<b></td>
    <td>El uso de AS es opcional, pero mejora la legibilidad cuando quieres dar nombres más descriptivos a columnas o tablas en las consultas.</td>
    <td>
<pre><code>SELECT Columna1 AS 'AliasColumna'
FROM NombreTabla;
</code></pre>
    </td>
  </tr>
  <tr>
    <td colspan=3 style="text-align: center;"><b>GROUP BY (Agrupar datos)<b></td>
  </tr>
  <tr>
    <td><b>GROUP BY<b></td>
    <td>Agrupar por una columna.</td>
    <td>
<pre><code>SELECT Columna2, COUNT(*)
FROM NombreTabla
GROUP BY Columna2;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>HAVING<b></td>
    <td>Agrupar y filtrar con HAVING.</td>
    <td>
<pre><code>SELECT Columna2, COUNT(*)
FROM NombreTabla
GROUP BY Columna2
HAVING COUNT(*) > 1;
</code></pre>
    </td>
  </tr>
  <tr>
    <td colspan=3 style="text-align: center;"><b>ORDER BY (Ordenar datos)<b></td>
  </tr>
  <tr>
    <td><b>ORDER BY (ASC)<b></td>
    <td>Seleccionar con ordenación ascendente.</td>
    <td>
<pre><code>SELECT * FROM NombreTabla
ORDER BY Columna2 ASC;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>ORDER BY (DESC)<b></td>
    <td>Seleccionar con ordenación descendente.</td>
    <td>
<pre><code>SELECT * FROM NombreTabla
ORDER BY Columna2 DESC;
</code></pre>
    </td>
  </tr>
  <tr>
    <td colspan=3 style="text-align: center;"><b>JOINS (Uniones entre tablas)<b></td>
  </tr>
  <tr>
    <td><b>INNER JOIN<b></td>
    <td>Devuelve filas coincidentes en ambas tablas.</td>
    <td>
<pre><code>SELECT A.Columna1, B.Columna2
FROM TablaA A
INNER JOIN TablaB B ON A.Id = B.Id;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>LEFT JOIN<b></td>
    <td>Devuelve todas las filas de la tabla izquierda y coincidentes de la derecha.</td>
    <td>
<pre><code>SELECT A.Columna1, B.Columna2
FROM TablaA A
LEFT JOIN TablaB B ON A.Id = B.Id;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>RIGHT JOIN<b></td>
    <td>Devuelve todas las filas de la tabla derecha y coincidentes de la izquierda.</td>
    <td>
<pre><code>SELECT A.Columna1, B.Columna2
FROM TablaA A
RIGHT JOIN TablaB B ON A.Id = B.Id;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>FULL JOIN<b></td>
    <td>Devuelve filas coincidentes o no de ambas tablas.</td>
    <td>
<pre><code>SELECT A.Columna1, B.Columna2
FROM TablaA A
FULL JOIN TablaB B ON A.Id = B.Id;
</code></pre>
    </td>
  </tr>
  <tr>
    <td colspan=3 style="text-align: center;"><b>FUNCTIONS (Funciones útiles)<b></td>
  </tr>
  <tr>
    <td><b>AVG<b></td>
    <td>Promedio de los registros.</td>
    <td>
<pre><code>SELECT AVG(Columna1)
FROM NombreTabla;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>SUM<b></td>
    <td>Sumar registros.</td>
    <td>
<pre><code>SELECT SUM(Columna1)
FROM NombreTabla;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>COUNT<b></td>
    <td>Contar registros.</td>
    <td>
<pre><code>SELECT COUNT(*)
FROM NombreTabla;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>MIN<b></td>
    <td>Mínimo de los registros.</td>
    <td>
<pre><code>SELECT MIN(Columna1)
FROM NombreTabla;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>MAX<b></td>
    <td>Máximo de los registros.</td>
    <td>
<pre><code>SELECT MAX(Columna1)
FROM NombreTabla;
</code></pre>
    </td>
  </tr>
  <tr>
    <td colspan=3 style="text-align: center;"><b>WHERE (Filtros)<b></td>
  </tr>
  <tr>
    <td><b>LIKE<b></td>
    <td>Busca patrones en las cadenas de texto.</td>
    <td>
<pre><code>SELECT * FROM NombreTabla
WHERE Columna1 LIKE 'Juan%';
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>IN<b></td>
    <td>Busca valores específicos dentro de un conjunto.</td>
    <td>
<pre><code>SELECT * FROM NombreTabla
WHERE Columna1 IN ('Activo', 'Inactivo');
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>BETWEEN<b></td>
    <td>Selecciona datos dentro de un rango de valores.</td>
    <td>
<pre><code>SELECT * FROM NombreTabla
WHERE Columna1 BETWEEN 100 AND 500;
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>ANY<b></td>
    <td>Compara un valor con cualquiera de los valores de un subconsulta.</td>
    <td>
<pre><code>SELECT * FROM NombreTabla1
WHERE Columna1 > ANY (SELECT Columna1 FROM NombreTabla2 WHERE Columna = 'Electrónica');
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>EXISTS<b></td>
    <td>Verifica si una subconsulta devuelve filas.</td>
    <td>
<pre><code>SELECT * FROM NombreTabla1 T
WHERE EXISTS (SELECT 1 FROM NombreTabla2 V WHERE V.Columna = T.Columna);
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>AND<b></td>
    <td>Combina condiciones, ambas deben ser verdaderas.</td>
    <td>
<pre><code>SELECT * FROM NombreTabla
WHERE Columna1 = 1 AND Columna2 = 'Activo';
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>OR<b></td>
    <td>Combina condiciones, al menos una debe ser verdadera.</td>
    <td>
<pre><code>SELECT * FROM NombreTabla
WHERE Columna1 = 1 OR Columna2 = 'Activo';
</code></pre>
    </td>
  </tr>
  <tr>
    <td><b>NOT<b></td>
    <td>Niega una condición, solo selecciona los registros que no cumplan con la condición.</td>
    <td>
<pre><code>SELECT * FROM NombreTabla
WHERE NOT Columna1 = 2;
</code></pre>
    </td>
  </tr>
</table>