# Clase 1

¿Que es un control de versiones?
es un sitema que registra cada cambio en el codigo de un proyecto

¿por que es importante?
.Rendimiento: solo guarda lo necesario
.Seguridad: conserva toda accion
.Flexibilidad:no es necesario un desarrollo lineal

¿Que es git?
un controlador de versiones

¿Que es un repositorio?
es una carpeta donde se guardan todos las versiones hechas en el proyecto 

¿para que sirve el comando git init?
$ git init ---> inicia el repositorio

¿para que sirve el comando git --help?
$ git --help ---> muestra los comandos que se puede usar


# clase 2

¿Que es un commit?
un commit registra cambios que se hicieron en el repositorio

¿Como hacer hago Commit?
$ git commit ---> para guardar los cambios en el area de staging
$ git commit -m "añadir mensaje"---> el mensaje añadido se usara como titulo en tu commit

¿Que es el HEAD?
el HEAD es un puntero que apunta al repositorio actual donde se esta trabajando

¿Que es una rama?
es un nuevo apuntador hacia una de las confirmaciones, 
es como una division que creara "una copia" del repositorio donde se podra hacer cambios

# clase 3
¿Para que sirven las ramas?
permiten un desarrollo no lineal y colaborativo donde otras paersonas puedan colaborar


¿Como fusionar ramas?
nos referimos a que los cambios de la rama se integran en otra rama 
$ git merge ---> comando para fusionar ramas

acabamos de fusionar un archivo c++ de rama_c a la rama principal master

¿por que eliminar ramas?
por buena practica y las ramas tienen un proposito unico de corto periodo

comandos sobre ramas
$ git branch ---->ver ramas
$ git switch nombreRama ---> cambiar de rama
$ git checkout nombreRama ---> cambiar de rama
$ git checkout -b nombreRama -----> creamos una rama

## conflictos en git?????
eso sucede cuando se ha realizado cambios en las mismas lineas en un fichero
## ¿Como resolver?
nos quedamos con los cambios de la rama main
nos quedamos con los cambios de la rama changes
modificamos para hacer una fusion personalizada

# clase 4
## ¿git y github son lo mismo?
no, git es un control de versiones 
github es un servicio de alojamiento en la nube basado en el sistema git

## git es unico?
no, existe Bitcket, GitLab

$ git remote add origin linkDeGit ----> para conectar git y github
$ git clone <url>  ----> descargar un repositorio

comandos git push 
$ git push -----> enviar los cambios
$ git pull -----> desarga y fusiona los cambios del repositorio remoto

¿Que es una pull Request?
es una peticion para cambios 
¿Como se hace un pr?
subir nuestra rama con git push y
1 la rama que se subio recientemente tendra la opcion en github >code
o
2 ir al apartado Pull Request
## prueba de imagen
![imagen](img/desastre9.jpg)