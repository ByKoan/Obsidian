Loggearemos como SYSTEM y lanzaremos lo siguiente:

```sql
ALTER SESSION SET "_ORACLE_SCRIPT" = TRUE;
```

Nos iremos al usuario SYSTEM -> Agregar nuevo usuario
- Nombre en mayusculas
- Permisos:
	- DBA
	- CONNECT
	- RESOURCE