## Configuración Básica

Configurar Nombre que salen en los commits
```bash
	git config --global user.name "dasdo"
```
Configurar Email
```bash	
	git config --global user.email dasdo1@gmail.com
```
Marco de colores para los comando
```bash
	git config --global color.ui true
```

## Iniciando repositorio

Iniciamos GIT en la carpeta donde esta el proyecto
```bash
	git init
```
Clonamos el repositorio de github o bitbucket
```bash
	git clone <url>
```
Añadimos todos los archivos para el commit
```bash
	git add .
```
Hacemos el primer commit
```bash
	git commit -m "Texto que identifique por que se hizo el commit"
```
subimos al repositorio
```bash
	git push origin master
```

## GIT CLONE
Clonamos el repositorio de github o bitbucket
```bash
	git clone <url>
```
Clonamos el repositorio de github o bitbucket ?????
```bash
	git clone <url> git-demo
```

## GIT ADD
Añadimos todos los archivos para el commit
```bash
	git add .
```
Añadimos el archivo para el commit
```bash
	git add <archivo>
```
Añadimos todos los archivos para el commit omitiendo los nuevos
```bash
	git add --all 
```
Añadimos todos los archivos con la extensión especificada
```bash
	git add *.txt
```
Añadimos todos los archivos dentro de un directorio y de una extensión especifica
```bash
	git add docs/*.txt
```
Añadimos todos los archivos dentro de un directorios
```bash
	git add docs/
```
## GIT COMMIT

Cargar en el HEAD los cambios realizados
```bash
	git commit -m "Texto que identifique por que se hizo el commit"
```
Agregar y Cargar en el HEAD los cambios realizados
```bash
	git commit -a -m "Texto que identifique por que se hizo el commit"
```
De haber conflictos los muestra
```bash
	git commit -a 
```
Agregar al ultimo commit, este no se muestra como un nuevo commit en los logs. Se puede especificar un nuevo mensaje
```bash
	git commit --amend -m "Texto que identifique por que se hizo el commit"
```
## GIT PUSH

Subimos al repositorio
```bash
	git push <origien> <branch>
```
Subimos un tag
```bash
	git push --tags
```
## GIT LOG

Muestra los logs de los commits
```bash
	git log
```
Muestras los cambios en los commits
```bash
	git log --oneline --stat
```
Muestra graficos de los commits
```bash
	git log --oneline --graph
```
## GIT DIFF

Muestra los cambios realizados a un archivo
```bash
	git diff
	git diff --staged
```
## GIT HEAD

Saca un archivo del commit
```bash
	git reset HEAD <archivo>
```
Devuelve el ultimo commit que se hizo y pone los cambios en staging
```bash
	git reset --soft HEAD^
```
Devuelve el ultimo commit y todos los cambios
```bash
	git reset --hard HEAD^
```
Devuelve los 2 ultimo commit y todos los cambios
```bash
	git reset --hard HEAD^^
```
Rollback merge/commit
```bash
	git log
	git reset --hard <commit_sha>
```
## GIT REMOTE

Agregar repositorio remoto
```bash
	git remote add origin <url>
```
Cambiar de remote
```bash
	git remote set-url origin <url>
```
Remover repositorio
```bash
	git remote rm <name/origin>
```
Muestra lista repositorios
```bash
	git remote -v
```
Muestra los branches remotos
```bash	
	git remote show origin
```
Limpiar todos los branches eliminados
```bash
	git remote prune origin 
```
## GIT BRANCH

Crea un branch
```bash
	git branch <nameBranch>
```
Lista los branches
```bash
	git branch
```
Comando -d elimina el branch y lo une al master
```bash
	git branch -d <nameBranch>
```
Elimina sin preguntar
```bash
	git branch -D <nameBranch>
```
## GIT TAG

Muestra una lista de todos los tags
```bash
	git tag
```
Crea un nuevo tags
```bash
	git tag -a <verison> - m "esta es la versión x"
```
## GIT REBASE

Los rebase se usan cuando trabajamos con branches esto hace que los branches se pongan al día con el master sin afectar al mismo

Une el branch actual con el mastar, esto no se puede ver como un merge
```bash
	git rebase
```
Cuando se produce un conflicto no das las siguientes opciones:

cuando resolvemos los conflictos --continue continua la secuencia del rebase donde se pauso
```bash	
	git rebase --continue 
```
Omite el conflicto y sigue su camino
```bash
	git rebase --skip
```
Devuelve todo al principio del rebase
```bash
	git reabse --abort
```
Para hacer un rebase a un branch en especifico
```bash	
	git rebase <nameBranch>
```
## OTROS COMANDOS

Lista un estado actual del repositorio con lista de archivos modificados o agregados
```bash
	git status
```
Quita del HEAD un archivo y le pone el estado de no trabajado
```bash
	git checkout -- <file>
```
Crea un branch en base a uno online
```bash
	git checkout -b newlocalbranchname origin/branch-name
```
Busca los cambios nuevos y actualiza el repositorio
```bash
	git pull origin <nameBranch>
```
Cambiar de branch
```bash
	git checkout <nameBranch/tagname>
```
Une el branch actual con el especificado
```bash
	git merge <nameBranch>
```
Verifica cambios en el repositorio online con el local
```bash
	git fetch
```
Borrar un archivo del repositorio
```bash
	git rm <archivo> 
```

## Fork

Descargar remote de un fork
```bash
	git remote add upstream <url>
```

Merge con master de un fork
```bash
	git fetch upstream
	git merge upstream/master
```