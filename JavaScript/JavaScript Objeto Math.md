# Objeto Math

1. [[#Propiedades]]
2. [[#Metodos]]

## Propiedades
- **PI**: Radio de la circuferencia de un circlo respecto a su diametro, aproximadamente 3.14159
- **SQRT1_2**: Raiz cuadrada de 1/2; Equivalentemente, 1 sobre la raiz cuadrada de 2, aproximadamente 0.707
- **SQRT2:** Raiz cuadrada de 2, aproximadamente 1.414
- **E**: Constante de Euler, la base de los logaritmos naturales,
- **LN2**: Logaritmo natural de 2, aproximadamente 0.693
- **LN10**: Logaritmo natural de 10, aproximadamente 2.303
- **LOG2E**: Logaritmo de E con base 2, aproximadamente 1.443
- **LOG10E**: Logaritmo de E con base 10, aproximadamente 0.434


## Metodos

### sqrt()
Devuelve la raiz cuadrada positiva de un numero
```js
sqrt();
```

### cbrt()
Devuelve la raiz cubica de un numero
```js
cbrt();
```

### max()
Devuelve el mayor de cero o mas numeros
```js
max();
let numero = Math.max(4,1,6,13,534,442);
document.write(numero);
```

### min()
Devuelve el mas pequeño de cero o mas numeros.
```js
min();
let numero = Math.min(4,1,6,13,534,442);
document.write(numero);
```

### random()
Devuelve un numero pseudo-aleatorio entre 0 y 1
```js
random();
numero = Math.random()*100;
numero= Math.round(numero);
document.write(numero);
```

### round()
Devuelve el valor de un numero redondeado al numero entero mas cercano
```js
round();
```
### fround()
Devuelve la representacion flotante de precision simple mas cercana de un numero
```js
fround();
```

### floor()
Devuelve el mayor entero menor que o igual a un numero
```js
floor(); 
```

### trunc()
Devuelve la parte entera del numero x, la eliminacion de los digitos fraccionarios
```js
trunc();
```
