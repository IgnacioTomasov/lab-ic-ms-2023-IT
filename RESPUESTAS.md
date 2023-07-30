# Respuestas

Indica tu nombre a continuación: 

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

## ETAPA 1

¿Cuál es la diferencia entre los archivos con el verbo `Create` con los archivos con el verbo `Add`?

Create crea tablas, Add inserta contenido.

¿Cómo se llama el servicio que se declara en el archivo `docker-compose.yml`?

flyway

¿Cuál es el comando que se ejecuta en el servicio declarado?

-locations=filesystem:/flyway/sql -connectRetries=60 migrate

## ETAPA 2

¿Qué pasa si cambias el nombre del servicio de `postgres` a `db`? ¿Qué otros cambios tendrías que hacer?

-Cambiar el nombre de la variable de entorno: POSTGRES_SERVER=db
-Cambiar valor de la sección "depends_on" en el servicio flyway, esto para asegurar que el servicio "db" se inicialice antes que flyway.

## ETAPA 3

¿Cómo se relacionan el archivo `docker-compose.yml` y el archivo `movies-api/Dockerfile`?

-El contenedor 'movies-api' instanciado en docker-compose lo hace en base a la imagen declarada en movies-api/Dockerfile. 

¿Qué crees que hace el atributo `context` debajo de `build` (está en la linea 6 del archivo `docker-compose.yml`)?

-Define la ruta donde encontrar el archivo dockerfile

## ETAPA 4

Compara el atributo `build` del servicio `movies-api` con el de `movies-front`. 

¿Cuál es la diferencia? 

La diferencia es que un servicio identifica su archivo Dockerfile mediante `context` y otro mediante `build`

¿Qué pasa si los dejas iguales?

Si se utiliza "build: movies-front" y "build: movies-api", los contenedores se instanciarán correctamente.  


