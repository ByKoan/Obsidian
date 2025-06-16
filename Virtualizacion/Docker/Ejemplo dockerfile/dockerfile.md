```dockerfile
# 1. Imagen base mínima con Python
FROM python:3.12-slim

# 2. Variable de entorno
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# 3. Directorio de trabajo dentro del contenedor
WORKDIR /app

# 4. Copiamos archivos al contenedor
COPY requirements.txt .

# 5. Instalamos dependencias
RUN pip install --no-cache-dir -r requirements.txt

# 6. Copiamos el resto del código
COPY . .

# 7. Exponemos el puerto (documentación, no lo abre)
EXPOSE 5000

# 8. Comando por defecto si no se indica otro
CMD ["python", "app.py"]

# 9. Punto de entrada (fijo, se ejecuta sí o sí)
# Puedes usarlo con scripts de inicialización si quieres.
# En este caso no lo necesitamos estrictamente, pero se muestra como ejemplo:
# ENTRYPOINT ["python"]
```