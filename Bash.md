https://e-mc2.net/blog/bash-iii-variables-y-funciones/#definiendo-una-variable
# Bash (III) - Variables y funciones

 2006-09-03  
 Words: 804  
 Reading time: 4 min.

 [linux](https://e-mc2.net/tags/linux/) • [bash](https://e-mc2.net/tags/bash/) • [sysadm](https://e-mc2.net/tags/sysadm/) • [linux-es](https://e-mc2.net/tags/linux-es/) • [español](https://e-mc2.net/tags/espa%C3%B1ol/)

---

## Table Of Contents

-   [Variables](https://e-mc2.net/blog/bash-iii-variables-y-funciones/#variables)
    -   [Definiendo una variable](https://e-mc2.net/blog/bash-iii-variables-y-funciones/#definiendo-una-variable)
    -   [Usando variables de entorno](https://e-mc2.net/blog/bash-iii-variables-y-funciones/#usando-variables-de-entorno)
    -   [Asignado resultados de comandos a variables](https://e-mc2.net/blog/bash-iii-variables-y-funciones/#asignado-resultados-de-comandos-a-variables)
    -   [Usando caracteres especiales en variables](https://e-mc2.net/blog/bash-iii-variables-y-funciones/#usando-caracteres-especiales-en-variables)
    -   [Variables numericas](https://e-mc2.net/blog/bash-iii-variables-y-funciones/#variables-numericas)
-   [Funciones](https://e-mc2.net/blog/bash-iii-variables-y-funciones/#funciones)

En nuestra tercera entrega sobre el interprete de comandos Bash vamos a empezar a ver como podemos usar de forma practica la informacion que hemos visto en los articulos anteriores. Para empezar y antes de entrar en materia, nada mejor que un ejemplo del clasico [“Hola Mundo”](http://es.wikipedia.org/wiki/Hola_mundo) en Bash.

```bash
#!/bin/bash
#
# Esto es un ejemplo en Bash del clasico "Hola Mundo"
#

echo "Hola Mundo"
```

Como podeis ver, nada dificil para empezar. Empecemos a explicar un poco que significa cada linea:

_#!/bin/bash:_ Esta linea indica donde se encuentra el interprete de comandos en nuestro sistema. Por defecto todos los sistemas que tengan Bash instalado, lo tendran en el directorio /bin. Al utilizar esta linea, podremos ejecutar el script como un programa normal, ya que el sistema sabra que es un script en Bash y que tiene que hacer con el.

Si el script de ejemplo lo hubiesemos grabado como ejemplo.sh, lo podriamos ejecutar de la siguiente manera:

```bash
[ralfm@desktop]# chmod ugo+x ejemplo.sh
[ralfm@desktop]# ./ejemplo.sh 
Hola Mundo
```

_# Esto es un ejemplo en Bash del clasico “Hola Mundo”:_ Esto es un comentario. Todas las lineas que empiecen con el simbolo ‘#’ seran tratadas como comentarios y no se ejecutaran.

_echo “Hola Mundo”:_ Esto es el comando que imprime la cadena de texto en pantalla.

## Variables

En todo script tendreis que trabajar con variables, mas tarde o mas temprano. Vamos a ver como se definen y usan. Una buena costumbre cuando definamos variables en Bash es utilizar letras mayusculas, esto no es necesario, pero nos ayudara a tener un script mas facil de entender.

### Definiendo una variable

```bash
#!/bin/bash
#
# Esto es un ejemplo en Bash del clasico "Hola Mundo"
#

MENSAJE="Hola Mundo"
echo $MENSAJE
```

Hemos definido una variable llamada MENSAJE con el valor “Hola Mundo”, y la hemos usado con el comando echo para escribir el valor de la misma. Las variables en Bash se definen como NOMBRE=valor (sin espacios antes o despues del simbolo ‘=') y su valor se usa, poniendo el simbolo ‘$’ delante del nombre de la variable, $NOMBRE.

Si al utilizar el valor de una variable, el nombre de variable esta seguido de un caracter que sea otra letra, numero o el simbolo ‘_’, tendremos que utilizar los simbolos ‘{}’ alrededor del nombre de la variable.

```bash
#!/bin/bash

FICHERO="registro"
echo ${FICHERO}_2006.txt
```

### Usando variables de entorno

```bash
#!/bin/bash
echo "El usuario '$USERNAME' ha ejecutado el script $0, en el ordenador '$HOSTNAME'. "
```

Tambien se pueden usar en nuestro scripts, variables que no hemos definido nosotros. Estas variables son las llamadas ‘variables de entorno’ del sistema. Teneis una lista con las mas importantes por defecto, en el segundo articulo de esta serie, Bash (II) - Comandos, variables de entorno y combinaciones de teclas. En nuestro ejemplo hemos utilizado $USERNAME y $HOSTNAME para obtener el nombre de usuario y del ordenador. La variable $0 contiene el nombre del script, mas adelante explicaremos esto.

### Asignado resultados de comandos a variables

```bash
#!/bin/bash

ATRIBUTOS_SCRIPT=`/bin/ls -l $0`

echo "El usuario '$USERNAME' ha ejecutado el script $0, en el ordenador '$HOSTNAME'. "
echo "Los atributos del script son: "
echo $ATRIBUTOS_SCRIPT
```

Tambien podemos asignar la salida que producen los comandos del sistema a una variable. En nuestro ejemplo hemos asignado la salida del comando ‘ls -l a una variable llamada ATRIBUTOS_SCRIPT. Esto nos sera muy util en nuestros scripts para obtener informacion del sistema que podremos utilizar en nuestros scripts.

### Usando caracteres especiales en variables

Existen una serie de caracteres que tienen un significado especial en Bash, por ejemplo $ y “. Si queremos usar literalmente estos caracteres en el valor de una variable tendremos que usar el simbolo ‘' delante de ellos.

```bash
#!/bin/bash

MENSAJE="\"Hola Mundo ...\""
echo "El valor de la variable \$MENSAJE es $MENSAJE"
```

### Variables numericas

Si queremos definir variables numericas para su utilizacion en scripts Bash podemos utilizar el comando let. Nada mejor que un ejemplo para ver como se trabaja con variables numericas.

```bash
#!/bin/bash

let A=100
let B=200
let C=$A+$B

echo "A: $A | B: $B | C: $C"
```

## Funciones

En Bash se pueden definir funciones. Una funcion en Bash (denominada subrutina o procedimiento en otros lenguajes de programacion) se podria definir como un script dentro de un script. Sirve para organizar un script en unidades logicas de manera que sea mas facil mantenerlo y programarlo. En Bash las funciones se pueden definir de la siguiente manera:

```bash
function nombre_de_funcion(){
  comandos_del_shell
}
```

Un ejemplo de funcion en un script:

```bash
#!/bin/bash

let A=100
let B=200

#
# Funcion suma()
# Suma los variables A y B
#
function suma(){
 let C=$A+$B
 echo "Suma: $C"
}

#
# Funcion resta()
# Resta los variables A y B
#
function resta(){
 let C=$A-$B
 echo "Resta: $C"
}

suma
resta
```