Los **CREATE TABLE AS** son una forma de crear tabla mediante tablas existentes

```sql
CREATE TABLE tabla AS 
SELECT *
FROM tablaExistente;
```

**También podemos crear tablas mediante archivos .csv**

```sql
CREATE OR REPLACE DIRECTORY dir_read AS  'C:\app\usuario\product\21c\dbhomeXE\data';  
GRANT ALL ON DIRECTORY dir_read TO PUBLIC;   

DROP TABLE PRUEBA_EXT CASCADE CONSTRAINTS;

CREATE TABLE PRUEBA_EXT  
(  
  nombre VARCHAR2(20),  
  edad NUMBER  
)  
  ORGANIZATION EXTERNAL  
  ( TYPE ORACLE_LOADER  
  DEFAULT DIRECTORY DIR_READ  
  ACCESS PARAMETERS  
  ( RECORDS DELIMITED BY NEWLINE  
  --LOGFILE 'PRUEBA_EXT.log'  
  --BADFILE 'PRUEBA_EXT.bad'  
  --DISCARDFILE 'PRUEBA_EXT.dsc'  
  FIELDS TERMINATED BY ";" OPTIONALLY ENCLOSED BY '"' LRTRIM  
  (  
  nombre CHAR,  
  edad CHAR  
  )  
  )  
  LOCATION (DIR_READ:'Libro1.csv')  
)  
REJECT LIMIT 100  
--NOPARALLEL  
--NOMONITORING  
;
```