# Consola
1. [[#Funciones de conteo]]
 - [[#assert]]
 - [[#clear]]
 - [[#error]]
 - [[#info]]
 - [[#log]]
 - [[#table]]
 - [[#warn]]
 - [[#dir]]
2. [[#Funciones de conteo]]
 - [[#count]]
 - [[#countReset]]
3. [[#Funciones de agrupacion]]
 - [[#group]]
 - [[#grupEnd]]
 - [[#groupCollapsed]]
4. [[#Funciones de temporizacion]]
 - [[#time]]
 - [[#timeEnd]]
 - [[#timeLog]] 
 
## Funciones de Registro
### assert()
Aparece un mensaje de error en la consola si la afirmacion es falsa.Si la afirmacion es verdaderam no aparecera nada.(NO ESTANDAR)

```js
console.assert()
```

### clear() 
Limpia la consola
```js
console.clear();
```

### error()
Muestra un mensaje de error en la consola web
```js
console.error();
```

### info()
(Mensaje Informativo) Emite un mensaje informativo a la consola web. En firefox y Chrome, se muestra un pequeño icono "i" junto a estos elementos en el registro de la consola web.
```js
console.info();
```

### log()
(mensaje de depuracion) Muestra un mensaje en la consola web (o del interprete JavaScript).
```js
console.log();
```

### table()
Esta funcion toma un argumento obligatorio: data, que debe ser un array o un objeto y un parametro adicional: columns y nos muestra una tabla en consola.
```js
console.table();
```

### warn()
Imprime un mensaje de advertencia en la consola web.
```js
console.warn();
```

### dir()
Despliega una lsita interactiva de las propiedades del objeto JavaScript especificado.[NO ESTANDAR]
```
console.dir();
```

## Funciones de conteo
### count()
Registra el numero de veces que se llama a count(). Esta funcion toma como argumento opcional una etiqueta.
```js
console.count();
```

### countReset()
Resetea el contador console.count()
```js
console.countReset()
```

## Funciones de agrupacion
### group()
Crea un nuevo grupo en linea en el registro de la consola web.
```js
console.group();
```

### grupEnd()
Remueve un grupo en linea en el registro de la consola web.
```js
console.grupEnd()
```

### groupCollapsed()
Crea un grupo en linea pero contraido, el usuario debe expandirlo para verlo.
```js
console.groupCollapsed()
```

## Funciones de temporizacion
### time() 
Inicia un temporizador
```
console.time();
```

### timeEnd()
Registra el valor actual de un temporizado.
```
console.timeEnd();
```

### timeLog()
Detiene un temporizador
```
console.timeLog() ;
```