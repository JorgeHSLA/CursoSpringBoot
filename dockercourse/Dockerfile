##########################################################

                        #Docker

##########################################################



#recordar tener docker abierto

#vamos a crear la imagen


#este from nos sirve para reutlizar una imagen ya creada antes, en este caso es la imagen de nginx:alpine, nginx es el nombre de la imagen y el alpine es la etiqueta

FROM nginx:alpine

#copiar algo de nuestra memoria a la imagen en un destino, (en este caso el index.html es el algo de nuestra memoria y 
#/usr/share/nginx/html/index.html  es la ruta donde se va a colocar nuestro archivo en la imagen)
COPY index.html /usr/share/nginx/html/index.html


## En la terminal:

    #################################
    ###### Contruir la imagen #######
    #################################

    #docker build -t my-first-img:1.0 . 

    #-t: indica que vas a ponerle una etiqueta a la imagen.

    #my-first-img: es el nombre de la imagen.

    #1.0 : es la etiqueta o versión de la imagen (por convención, como un número de versión).

    #. : indica que el contexto de construcción (es decir, el directorio donde está el Dockerfile), al ser punto es el directorio actual.

    ##

    ### POSIBLE ERROR ES QUE TU ARCHIVO NO SE LLAME Dockerfile, SE TENDRIA QUE: docker build -t my-first-img:1.0 -f MiDockerfile .  (MiDockerfile seria el nombre del archivo docker)

    ##


    # docker images en el terminal para saber imagenes que tenemos y sus IDs


    ##############################################################################
    #####         Crear y ejecutar contenedor a partir de esa imagen         #####
    ##############################################################################


    #docker run --name mt-first-container -p 8080:80 -d my-first-img:1.0 

    #--name Asigna un nombre personalizado al contenedor
    #-p hace un enlace con el puerto de la maquina actual con el contenedor, en este caso mi maquina usa el 8080 y el del contenedor el 80
    #-d se ejecuta en segundo plano y luego se pone el nombre de la imagen o el id de esta 


    # docker ps en el terminal para saber que contenedores tenemos activos

    # docker stop containerId para parar un contenedor, (podria ser una base de datos o en este caso el html)
    # docker start containerId para iniciar un contenedor ya creado 


    #######################################################################################
    #####         Crear y ejecutar contenedor a partir de la imagen de postgres       #####
    #######################################################################################

    #docker run --name mt-first-conatiner -p 5432:5432 -e POSTGRES_DB=test -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=secret -v ./sql:/var/lib/postgresql/data -d postgres:16.1

    #--name mt-first-postgres \                 # Asigna el nombre "mt-first-postgres" al contenedor
    #-p 5432:5432 \                             # Mapea el puerto 5432 del contenedor al 5432 de tu máquina (host)
    #-e POSTGRES_DB=test \                      # Crea una base de datos inicial llamada "test"
    #-e POSTGRES_USER=admin \                   # Crea un usuario llamado "admin"
    #-e POSTGRES_PASSWORD=secret \              # Le asigna la contraseña "secret" al usuario "admin"
    #-v ./sql:/var/lib/postgresql/data \        # Crea un volumen: guarda los datos del contenedor en tu carpeta local "./sql" lo que hace que aunque se caiga un contenedor este tenga persistencia de datos
    #-d \                                       # Ejecuta el contenedor en segundo plano (modo "detached")
    #postgres:16.1                              # Imagen usada: PostgreSQL, versión 16.1

    ## DATA: postgres siempre usa el puerto 5432