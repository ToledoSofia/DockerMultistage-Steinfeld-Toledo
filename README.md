#build de una imagen docker:

sudo docker build -t NOMBRE_IMAGEN -f NOMBRE_DOCKERFILE .
#-t : tag, nombre de la imagen que se quiere crear
#-f archivo dockerfile que contiene la imagen
#. directorio, en este caso es el actual

#run

sudo docker run -p 3000:80 NOMBRE_IMAGEN
#-p puertos
#nombre de la imagen creada en el build
