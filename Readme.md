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

# clase 5
## ¿Que es un gitFlow?
es la manera en que un equipo de desarrollo utiliza Git

## git flow
es el flujo de trabajo mas antiguo, utiliza las ramas:
1 main o master: contener el codigo de produccion
2 develop: codigo que esta en desarrollo en pruebas y ser validada

![imagenGit](img/images.png)

## GitHub Flow
Rama main y yalquiera otra rama que quiera ser integrada da un Pull Request

![imagenGithub](img/gibhub.png)

## Trunk Based Development
solo la rama main y ramas auxiliares efimeras que quiera ser integrada por medio de una Pull Request
util si se cuenta cn un sistema CI/CD

## Ship/Show/Ask
1 ship: se fusiona una rama principal sin revision
2 show: abre una paticion de cambios para que sea revisado por CI
3 Ask: abre una P para discutir los cambios antes de fusionarlos
## Reglas de SSA
-tenemos un vuen sistema de CI/CD
-confiamos en el equipo y existen las buenas practicas de desarrollo
- Las revisiones de codigo no son requerimients
-Las ramas son lo mas pequeñas con un tiempo de vida corto y salen directaente de la rama principal
-El equipo sabe lidiar con el ego individual, las personas confian en el resto del equipo


# clase 6

## ¿Para que sirven las buenas practicas?
-es un estandar en los equipos de desarrollo
-al tener conflictos o problemas en el desarrollo se resuelve mas facil
-tu historial de commits es mas legible

## 1 ¿Cada cuanto hacer un commit?
a menudo, es mejor hacer commits pequeños agrupando pequeñas mejoras o acciones 
ojo, no significa que debas hacer commits sin sentido
Haz un commit cuando hay un cambio significatvo

![imgP](img/imagesGit.png)

## escribir buenos commits
-usar el verbo imperativo (Add, Change, Fix, Reove)
-Nouses puntos final ni suspensivos en los mensajes
-Usar como maximo 50 caracteres
-Añade todo el contexto que sea necesario
-Considera usar utilidades para hacer commit
-usa un prefijo para tus commits para hacerlos mas semanticos

![imagenPerrito](img/PerreteGit.png)

## Prefijo para commits

style: para cambios de formato, tabulaciones, espacios o puntos y coma, etc; no afectan al usuario.
test: para tests o refactorización de uno ya existente.

feat: para una nueva característica para el usuario.

fix: para un bug que afecta al usuario.

perf: para cambios que mejoran el rendimiento del sitio.

build: para cambios en el sistema de build, tareas de despliegue o instalación.

ci: para cambios en la integración continua.

docs: para cambios en la documentación.

refactor: para refactorización del código como cambios de nombre de variables o funciones

## ⚫Ejemplo
feat.(backend): add filter for cars
fix(web): remove wrong color


## Escribir un buen nombre de rama

-Sé consistente al nombrar tus ramas
-Usa los IDs de JIRA o el sistema de tickets que uses
-Usa el nombre de la acción que se realiza en la rama

## ⚫Ejemplos
bug/avoid-creating-lead-twice
feature/add-new-user-form
experiment/try-new-ui-design
hotfix/fix-typo-in-name

# clase 7

## ¿En qué casos deshacemos cambios?

-Dejó de funcionar el proyecto.
-Queremos recuperar una parte del código que eliminamos.
-Queremos recuperar archivos que eliminamos.

![reset](img/reset.png)

## git reset

Posee 2 opciones

-soft: Mantiene los cambios que ocurrieron antes de hacer commit desde donde apuntaba.
-hard: Descarta los cambios.

## git revert

Revierte los cambios que un commit introdujo, y crea un nuevo commit con los cambios revertidos

## git checkout

Nos permite recuperar código específico de commits.

# Clase 8

## ¿Qué es un Hook?

Un hook, o punto de enganche, es la posibilidad de ejecutar una acción o script cada vez que ocurre un evento determinado de Git.
Hay:
-Hooks del lado del cliente
-Hooks del lado del servidor

## Hooks del lado del cliente

Sólo afectan al repositorio local que los contiene.

⚫ pre-commit

Podrias comprobar si se está intentando hacer un commit de demasiados archivos Puede ser un buen sitio para ejecutar el linter sobre los archivos que han sido modificados.

prepare-commit-msg

Para modificar el mensaje del commit o añadir cualquier información extra.

⚫ commit-msg

Es el sitio perfecto para hacer todas las comprobaciones pertinentes al mensaje.

⚫ post-commit

Su uso principal es la de notificar por Slack.

⚫ pre-push

Para ejecutar una bateria de tests.

⚫ post-checkout y post-merge

Permite limpiar el directorio de trabajo, tras realizar un checkout, o el de limpiar las ramas que ya no se usah tras realizar un merge

## Hooks del lado del servidor

Es interesante conocerlos ya que páginas como GitHub o GitLab los usan intensivamente a la hora de construir.

⚫ pre-receive

Para comprobar que los commits que se quieren guardar están bien formados.

Verificar que el usuario que intenta grabar los commits tiene los permisos necesarios para hacerlo.

⚫ update

Puedes evitar de una forma granular cada actualización.

⚫ post-receive

Enviar un correo a todos los usuarios del repositorio que se han grabado nuevos cambios en el repositorio remoto

Reflejar en una UI las nuevas referencias, ramas a commits disponibles.

## Creando mi primer hook

Para crear un propio hook sólo tienes que crear un archivo nombre-del-hook en la carpeta .git/hooks y en él poner el código que quieras que se ejecute.

Puedes usar todo tipo de intérpretes de lenguaje de programación como bash, node, python, perl, etc.

## Trucos en Git

Guarda tus cambios temporalmente

-git stash

-git stash -u

-git stash pop

## Aplicar cambios de commits en específico

-git cherry-pick <SHA>

## Detectar qué commit es el que ha introducido un bug

-git bisect

-git bisect start

-git bisect bad

-git bisect good

-git bisect reset