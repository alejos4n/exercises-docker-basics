# 1. Comenzar desde la imagen base oficial de Ubuntu 24.04
FROM ubuntu:24.04

# 2. Evitar interrupciones de prompts interactivos durante la instalación
ENV DEBIAN_FRONTEND=noninteractive

# 3. Actualizar los repositorios e instalar curl limpiando la caché para reducir espacio
RUN apt-get update && apt-get install -y curl

# 4. Establecer un directorio de trabajo (buena práctica recomendada)
WORKDIR /app

# 5. Copiar el archivo del script desde tu máquina local al contenedor
# Reemplaza "mi_script.sh" por el nombre real de tu archivo
COPY script.sh /app/script.sh

# 6. Darle permisos de ejecución al script copiado
RUN chmod +x /app/script.sh

# 7. Configurar el comando predeterminado para ejecutar el script al iniciar el contenedor
CMD ["/app/script.sh"]
