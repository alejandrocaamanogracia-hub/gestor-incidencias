# Laboratorio: Despliegue de una aplicación web con Docker Compose

** 1. ¿Por qué el frontend no necesita conectarse a PostgreSQL? **

El frontend no necesita conectarse a la base de datos porque los datos los recibe de la API que proporciona el backend.

** 2. ¿Por qué el backend pertenece a dos redes? **

Porque se tiene que comunicar con la base de datos para obtener los mismos y tiene que comunicarse con el frontend para suministrarle los datos.

** 3. ¿Qué servicio necesita publicar un puerto en el anfitrión? ** 

El servicio que necesita publicar el puerto en el anfitrión es el frontend.

** 4. ¿Por qué publicar PostgreSQL hacia fuera no es la solución adecuada para un fallo de comunicación interno? ** 

Porque no necesitas acceder a los datos desde tu maquina sino que se tiene que conectar la base de datos con el backend mediante su propia red interna.

** 5. ¿Qué ventaja ofrece Docker Compose respecto a ejecutar los tres contenedores manualmente? ** 

Permite configurar y levantar todos los contenedores necesarios para el proyecto en un único archivo, crear redes entre los distintos contenedores para que se comuniquen entre sí y establecer el orden de inicio de los contenedores.

** 6. ¿Por qué hemos dividido la arquitectura en dos redes? ** 

La arquitectura se divide en dos redes dado que en una se comunican el backend con la base da datos y en la otra el frontend con el backend de manera que nunca para comunicar el backend con los datos se use de puente el backend.

** 7. ¿Por qué el backend utiliza `db` como dirección de PostgreSQL? ** 

Se utiliza db porque es el nombre del contenedor que contiene la base de datos.

** 8. ¿Qué diferencia existe entre detener un proyecto y eliminar sus volúmenes? ** 

Si detienes el proyecto y lo vuelves a levantar la información se mantiene porque se guarda en el volumen, sin embargo, si borras el volumen, la información se pierde.

** 9. ¿Qué consecuencias tendría para la empresa perder el volumen de PostgreSQL? ** 

La empresa perdería todos sus datos.