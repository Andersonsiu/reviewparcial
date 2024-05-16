**DOCKERFILE**

 -CREA EL DOCKERFILE, ASÍ: 

FROM ubuntu:20.04
RUN apt-get update && \ 
apt-get install -y python
 COPY hola.py . 
 ENTRYPOINT ["python", "hola.py"]


- Construyendo la imagen
Ahora, podemos construir la imagen exactamente de la misma manera que lo hicimos antes, de la siguiente manera: 

$ docker build -t hola-python .

- Ejecutando la aplicación Ejecutamos la aplicación ejecutando el contenedor, así: 

$ docker run hola-python

- Este comando inició el contenedor de Ubuntu pero no le adjuntó la consola. Podemos ver que se está ejecutando usando el siguiente comando: 

$ docker ps

- Este comando imprime todos los contenedores que se encuentran en estado de ejecución. ¿Qué pasa con nuestros contenedores viejos, ya salidos? Podemos encontrarlos imprimiendo todos los contenedores, así: $ docker ps -a 

- Por ejemplo, podemos dejar de ejecutar el contenedor de Ubuntu, como se muestra aquí: 

$docker stop 13181f811922 


- Necesitamos iniciar el contenedor, especificando la asignación de puertos con el indicador p (--publish), de la siguiente manera: - p, --publish 

- Entonces, primero detengamos el contenedor en ejecución y comencemos uno nuevo, así: 

-$ docker stop 9b92be34d101
-$ docker run -d -p 8080:8080 tomcat
