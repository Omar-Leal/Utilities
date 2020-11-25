CONFIGURAR VARIABLES DE ENTORNO
-> git config --global user.name "My name"
-> git config --global user.mail  "personalmail@mail.com"  
-> git config --list

CONTROL REPOSITORIO LOCAL
# Iniciar un repositorio local
-> git init
# Agregar un repositorio y sus cambios al stagging area
-> git add .  o git add archivo.txt
# Eliminar un repositorio del stagging area
-> git rm --cached archivo.txt
# Agregar archivos, cambios al repositorio local final
-> git commit -m "mensaje va aca"

REVISIÓN DEL ESTADO DEL REPOSITORIO Y COMMITS REALIZADOS
# Revisar el estatus de nuestro repostorio y area de trabajo
-> git status
# Mostrar el historial de commits hechos desde el primero al más reciente
-> git log
# Mostrar hilos de cambios de cada commit desde el reciente hasta el primero
-> git log --stat
# Mostrar los cambios efectuados a un archivo
-> git show archivo.txt
# Mostrar la diferencia entre dos versiones de commits
-> git diff #commit1 #commit2
# Mostrar la diferencia entre mi directorio local y mi repo local
-> git diff

VOLVER EN EL TIMEPO    
# Volver en el tiempo en GIT (GIT RESET SOFT) lo que está en stagging permanece allí
->  git reset #comit --soft
# Volver todo hacia atrás borrando cambios realizados (GIT RESET HARD) borra todo el stagging
-> git reset #commit --hard
# Para ver un cambio especifico de commit anterior
-> git checkout #commit archivo.txt  
   Este git checkout mantiene los cambios del último commit al master.
   Si se hace un commit de este checkout regreso al estado del commit llamado en el checkout.
# Para regresar al estado de último commit solo llamamos a  master que es donde apunta el HEAD
-> git checkout master archivo.txt


Flujo de trabajo básico con un repositorio remoto
#Crear una rama a partir de la rama actual (donde apunta el HEAD)
-> git branch nombre_rama
# Ver ramas creadas
-> git branch
# Borrar alguna rama
-> git branch -d nombre_rama
# Para movernos entre ramas
-> git checkout nombre_rama

CONEXIÓN CON REPOSITORIO REMOTO VIA HTTP (GITHUB)
# Conectar mediante https
-> git remote add origin https://url-del-RepositorioRemoto.com
# Para checar que origin fue creado
-> git remote    (El output debe arrojar "origin")
# Para ver el tipo de origin (fetch and push)
-> git remote -v
# Antes de hacer el primer envio al master remoto, debemos traernos lo que esta en remoto para integrarlo al local
-> git pull origin master
# Para forzar el merge del repositorio remoto con el local debido a historias no relacionadas
-> git pull origin --allow-unrelated-histories


GENERAR LLAVE SSH EN MI ENTORNO LOCAL
# Agregando la llave SSH al /home
ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
# Comprobar proceso del servidor de llaves(Linux/Windows)
-> eval $(ssh-agent -s)
# Agregar la llave a ese servidor
--> ssh-add ~/.ssh/id_rsa




