# Metodos
1. [[#Contatename]]
2. [[#Metodos Cadena]]
   1. [[#concat]]
   2. [[#startsWith]]
   3. [[#endsWith]]
   4. [[#includes]]
   5. [[#indexOf]]
   6. [[#lastIndexOf]]
   7. [[#padStart]]
   8. [[#padEnd]]
   9. [[#repeat]]
   10. [[#split]]
   11. [[#substring]]
   12. [[#toLowerCase]]
   13. [[#toUpperCase]]
   14. [[#toString]]
   15. [[#trim]]
   16. [[#trimEnd]]
   17. [[#trimStart]]
   18. [[#valueOf]]
3. [[#Metodos Array]]
   - [[#Transdormadores]] 
       1. [[#pop]] 
       2. [[#shift]]
       3. [[#push]]
       4. [[#reverse]]
       5. [[#unshift]]
       6. [[#sort]]
       7. [[#splice]]
   - [[#Accesores]]
     1. [[#join]] 
     2. [[#slice]]
     3. [[#Metodos vistos]]
   - [[#Repeticion]]
     1. [[#filter]]
     2. [[#forEach]] 

## Contatename
```js
numero1.concat(numero2);
```

Convierte en tipo numero
```js
numero = parseInt(numero);
```

## Metodos Cadena
### concat()
Junta dos o mas cadenas y retorna una nueva.
```js
concat();
```

### startsWith()
Si una cadena comienza con los caracteres de otra cadena, devuelve true, sino devuelve false.
```js
startsWith(); 
```

### endsWith()
Si una cadena termina con los caracteres de otra cadena, devuelve true, si no devuelve false.
```js
endsWith();
```

### includes()
 Si una cadena puede encontrase dentro de otra cadena, devuelve true, si no devuelve false.
```js
includes();
```

### indexOf()
 Devuelve el indice del primer caracter de la cadena, si no existe, devuelve -1.
```js
indexOf();
```

### lastIndexOf()
 Devuelve el ultimo indice del primer caracter de la cadena, si no existe, devuelve -1
```js
lastIndexOf();
```

### padStart()
Rellenar cadena al principio con los caracteres deseados.
==propuesta de Estandar== 
```js
padStart(); 
```
### padEnd()
 Rellenas cadena al final con los caracteres deseados
 ==propuesta de ECMA==
```js
padEnd();
```

### repeat()
Devuelve la misma cadena pero reperita la cantidad que le indiquemos.
```js
repeat();
```

### split()
Divide la cadena como le pidamos
```js
split();
```

### substring()
 Nos retorna un pedazo de la cadena que seleccionamos
```js
substring();
substring(inicio_0,final_3);
```

### toLowerCase()
Convierte una cadena a minuscula
```js
toLowerCase();
```

### toUpperCase()
Convierte una cadena a mayuscula
```js
toUpperCase();
```

### toString()
Metodo devuelve una cadena que representa al objeto especificado
```js
toString();
```

### trim()
Elimina los espacions en blanco al principio y al final de una cadena.
```js
trim();
```

### trimEnd()
Elimina los espacios en vlanco al comienzo de una cadena.
```js
trimEnd();
```

### trimStart()
Elimina los espacios en blanco al comienzo de una cadena.
```js
trimStart();
```

###  valueOf()
Retorna el valor primitivo de un objeto string
```js
valueOf();
```

## Metodos Array

### Transdormadores
#### pop()  
Elimina el ultimo elemento de un array y lo devuelve. 
```js
pop();
```

#### shift()
Elimina el primer elemento de un array y lo devuelve.
```js
shift();
```

#### push()
push("gola) Agrega un elemento al array al final de la lista.
```js
push();
```

#### reverse()
Invierte el orden de los elementos de un array
```js
reverse();
```

#### unshift()
Agrega uno o mas elementos al inicio del array, y vuelve la nueva longitud del array.
```js
unshift();
```

#### sort()
Ordena los elementos de un arreglo(array) localmente y devuelve el arreglo ordenado.
```js
sort();
```

#### splice()
Cambia el contenido de un array eliminado elementos existentes y/o agregando nuevos elementos.
Agrega elementos infinitos separados por comas
```js
splice();
splice(0(posicion),3(elementos a eliminar);
splice(0,0,"dd"); //agrega al principio
splice(-1,0,"dd"); //agrega al final
	
```
### Accesores
####  join()
Une todos los elementos de una matriz(u objeto similar) en una cadena(texto o String) y la devuelve.
```js
join();
```

#### slice()
 Devuelve una parte del array dentro de un nuevo array empezando por inicio hasta fin (fin no incluido).
 Tambien existe poner el -1 para que nos muestre el ultimo elemento
```js
slice()
slice(0,3); 
slice(inicio,final);
```

#### Metodos vistos
Metodos ya vistos en cadenas: [[#toString]], [[#indexOf]], [[#lastIndexOf]], [[#includes]].

### Repeticion
#### filter()
 Crea un nuevo array con todos los elementos que cumplan la condicion.
```js
filter();
```
Recorrer con filter()
```js
let numeros = ["abecedario","manzana","pedro","dedo","bobo","pedro"];
numeros.filter( numero=> document.write(numero + "<br>"));
```
Condicion con filter()
```js
let numeros = ["abecedario","manzana","pedro","dedo","bobo","pedro"];
resultado= numeros.filter( numero=> numero.length >5);
document.write(resultado);
```

#### forEach()
 Ejecuta la funcion indicada una vez por cada elemento del array
```js
forEach();
let numeros = ["abecedario","manzana","pedro","dedo","bobo","pedro"];
numeros.forEach( numero => document.write(numero + "<br>"));

```


#### find() 
Visita el valor de cada posicion
- da true datos de la posicion
- da false sigue buscando


#### Extra

Saber el tipo de variable
```js
console.log(typeof varible); //Saber el tipo de variable
```




