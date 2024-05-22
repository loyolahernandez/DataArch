Resumen de actividades en la terminal

1. Iniciar sesión y abrir bash:
   - Iniciar sesión y abrir la terminal, utilizando por defecto `zsh` en lugar de `bash`.

2. Comprobar contenedores Docker en ejecución:
   - Ejecutar `docker ps` para ver los contenedores en ejecución con la imagen `bitnami/spark:latest`.

3. Navegar al directorio de trabajo y levantar servicios:
   - Navegar a un directorio específico con un archivo `compose.yml`.
   - Ejecutar `docker compose up -d` para levantar los servicios definidos en `compose.yml`, encontrando una advertencia sobre la obsolescencia de la versión del archivo.

4. Ejecutar comandos en contenedores:
   - Volver a comprobar los contenedores en ejecución con `docker ps` y verificar que los contenedores `spark_worker` y `spark_master` estén en funcionamiento.
   - Ejecutar `docker exec -it spark_master bash` y acceder a una terminal bash dentro del contenedor `spark_master`.

5. Navegar y manipular archivos dentro del contenedor:
   - Cambiar al directorio `/opt/spark/` y listar su contenido, encontrando `compose.yml` y otros subdirectorios como `datasets`.
   - Navegar al subdirectorio `datasets` y listar los archivos, encontrando varios archivos CSV y `docker-compose.yml`.

6. Usar Spark Shell:
   - Ejecutar `spark-shell` y levantar un entorno interactivo de Spark.
   - Cargar exitosamente los archivos CSV desde `/opt/spark/datasets/*.csv` en un DataFrame `df`.
   - Imprimir el esquema del DataFrame y visualizar las primeras filas con las columnas `brand` y `price`.
   - Filtrar el DataFrame para mostrar solo las filas donde `brand` sea 'f.o.x'.
   - Listar los valores distintos de la columna `brand`.
   - Crear un nuevo DataFrame `precios_marcas` filtrando por `brand='jas'`.
