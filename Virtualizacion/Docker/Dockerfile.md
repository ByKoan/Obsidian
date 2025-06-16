Son los archivos que indicaran a **docker** como crear una imagen

Para correr un **dockerfile** usaremos:

```bash
docker build -t dockerfile
docker run dockerfile
```

### Estructura básica de un **dockerfile**:

- `FROM` Especifica la imagen base
- `RUN` Ejecuta comandos dentro de la imagen (por ejemplo instalar cosas)
- `COPY` Copiar archivos del host al contenedor 
- `ADD` Igual que `COPY` pero mas avanzada (Puede descargar URLs o extraer .tar)
- `WORKDIR` Define el directorio de trabajo dentro del contenedor
- `CMD` Comando que se ejecuta cuando se inicia el contenedor
- `ENTRYPOINT` Similar a `CMD` pero fija el punto de entrada principal
- `EXPOSE` Informa que puerto usara la APP (Documentación, no abre el puerto)
- `ENV` Define variables de entorno
