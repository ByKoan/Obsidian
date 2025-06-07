La usaremos para seleccionar o rechazar un grupo de condiciones seleccionadas, normalmente la usaremos con la función **COUNT**

```SQL
SELECT CAMPO, CAMPO2, COUNT(*)
FROM TABLA 
GROUP BY CAMPO, CAMPO2
HAVING COUNT(*) > 1;
```