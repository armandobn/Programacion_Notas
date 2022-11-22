# Git


### git init
Sirve para Inicializar un proyecto nuevo
```bash
git init
```
### git add
Pasar los archivos al staging area o agregar los archivos para ser procesados posteriormente
```bash
git add archivo
git add .
git add -A
```
### git status
El estado de nuestros archivos, si ya estan dados de alta o no
```bash
git status
```
### git commint
Creamos un estado del desarrollo
```bash
git commit -m 'mensaje del commit'
```

### git log

```bash
git log
```

### git push
Para subir el proyecto a un repositorio remoto
```bash
git push
```
### git pull
Para poder bajar cambios de un repositorio
```bash
git pull
```

### git clone
Para clonar un proyecto existente a local
```bash
git clone <https://link-con-nombre-del-repositorio>
```

### git checkout
Revertir cambios antes de un commit
```bash
git checkout -- index.html
```

### git diff


git help branch
Ayuda de lo mas destacado que se puede hacer con las ramas.
```bash
git help branch
```

u* git branch -m master main : Cambiar el nombre de la rama de forma local.


u* git config –global init.defaultBranch <nombre de la rama> : Cambiar el nombre de la rama de forma global.

u* git branch <nombre de la rama> : Crear una nueva rama.

u* git checkout <nombre de la rama> :  Cambiarse de rama.

u* git branch –list : Ver las ramas que existen.

u* git branch -la : Ver todas las lista que existen.

u* git branch <nombre de la rama> -d : Eliminar rama.

u*git branch <nombre de la rama> -D : Eliminación forzada.

u* git merge <nombre de la rama> : Unión de ramas.
	
	u  * Fast-forward ==> cuando la rama no a sufrido cambios y al unirlos no hay problemas con la rama main (Master)

u  * Uniones automáticas ==> cuando hubo cambios en ciertos lugares pero que no afectan a la rama main(Master) o que no hay lineas entrelazadas.

u  * Unión Manual ==> cuando git no puede hacerlo de forma autoamtica. Para ello ocupamos un commit nuevo llamado Merge commit.

Para deshacer un `git add` antes de un commit,
git reset HEAD

La operativa de publicar una rama en remoto la haces mediante el comando `push`, indicando la opción "-u" y el nombre de la rama que deseas subir. Por ejemplo de esta manera:

```git
git push -u origin experimental
```