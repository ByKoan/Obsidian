Las funciones de agregación dependen de que se agrupe la sentencia por un campo para ello usamos el **GROUP BY**

```SQL
SELECT CAMPOM, COUNT(*)
FROM TABLA
GROUP BY CAMPO; -- Abra que poner tantos campos como haya en la SELECT
```
