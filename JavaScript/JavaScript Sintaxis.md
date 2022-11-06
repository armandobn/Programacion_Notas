# JavaScript
## Declaracion de Variables

``` js
recipiente = "Barbijo";
var global; //alzance global
let interno; //alzance interno, alcance bloque
const definido; //no se puede cambiar su valor
```
## Contatenar
````js
let nombre = "armando";
let saludo = "hola " + nombre;
````

### Literal String (Backticks)
```js
let nombre = "armando";
let saludo = `hola ${nombre}`; //literal string (otra forma de llamar)
//backticks ``
```

Nota: La concatenacion correcta y solo funciona si tiene esas comillas especiales

## Funciones

Una funcion flecha se puede trabajar como una variable tipo objeto, la diferencia sera que no se puede poner parentesis de invocacion si no referirse solo por su nombre.

Funcion que no recibe nada, no contiene nada porque no tiene un return
```js
function f1(){console.log("hola")}; //cuerpo de la funcion es todo lo que este entre las llaves
```

function que recive pero no devuelve nada
```js
const f222 = (edad)=>{ console.log("Tu edad es: "+ edad) }; f222(32);
```

### Diferentes casos de return en las funciones flecha
Esto nos permite ver como se estructura en diferentes casos para poder simplicar y entender el comportamiento de cada caso diferente teniendo en cuanta que se deve devolver como solo 1 objeto para que pueda realizarse.

```js
const f1=()=>"Dias de la semana";
const f11=()=>({ nombre:'armando', edad: '12', estatura: 1.2})
const f111=()=>{return { nombre:'armando', edad: '12', estatura: 1.2}}

console.log('Primera Forma: '+f1());
console.log('Segunda Forma');
console.log(f11())
console.log('Tercera Forma')
console.log(f111());
```

**Nota**
Mantener como una solo una cosa o un solo objeto a la hora de devolver

### Version transitoria
```js
const f1 = function(){ console.log("hola"); }
```


### Funcion Flecha

Esqueleto
```js
const funcionFlecha = ()=>{  }; //Esqueleto
funcionFlecha(); //LLamarlo
```

```js
//funciones flecha
const saludar = (nombre) => {
  let frase =`!Hola ${nombre}! ¿Como estas? `;
  document.write(frase);
}
saludar(); //llamar funcion
```

## Destructuracion - Arreglos
```js
 const personajes = ['Goku', 'Saitama', 'Naruto'];
 console.log(personajes[0]);

 const [p1] = personajes;
 console.log(p1);

 const [,p2] = personajes; //por cada "," avanzas una posicion 
 console.log(p2);
```

```js
// hacer una funcion que retorne dos posiciones, otra funcion que
 // destruya esas dos posiciones
 //Entender este concepto a detalle
 const f1= () => (['Salior Moon', 'Super Campiones']);
 //() Lo envuele para que sea solo una intruccion
 const kill = ([valor1, valor2])=>{
	 console.log(valor1);
	 console.log(valor2);
 }
 console.log(f1());
 kill(f1());
```

```js
 // Otra forma de pensar y estruturar
 const numeros = [12, 34, 56];
 const funciones = [
	 ()=>{console.log("Funcion 1")},
	 ()=>{console.log("Funcion 2")}
 ];
 const a = funciones[1]; //Forma larga de hacerlo
 a();
 funciones[0](); //Forma mas corta
```

##  Dependencia o Independencia de las copias(spread)
Cuando creamos una copia y queremos cambiar el valor por alguna razon el cambio que le hacemos al original tambien se refleja en la copia, la cual deben estar ambios independientes sin importar los cambios que se hagan uno del otro.

Esqueleto
```js
spread (...) //Asi se le llama a estos ...  (Mi manera de identificar)
let frutas3 = [...frutas];
console.log(frutas3)
```

Arreglo
```js
const arreglo = ['agua', 'fruta', 'comida'];
let a = ["a", "b", "c"];

console.log('Aplicando la copia');
let b = a;
console.log(a);
console.log(a[0]);
console.log(b);

console.log('Aplicando la copia correctamente independiente');
let vocal = [...a]; //aplica
console.log(vocal);
a[0] = "armando";
console.log(b);
```

Objeto
```js
const persona1 = {
  nombre: 'armando',
  covid: false,
  direccion: {
    calle: 'soledad',
    numero: 12
  }
}

console.log('Aplicando la copia');
const persona2=persona1;
console.log(persona1);
console.log(persona2);

console.log('Aplicando la copia correctamente independiente');
const persona22 = { ...persona1 }; //aplica
persona22.nombre = 'Daniela';
console.log(persona1);
console.log(persona22);
```

## Operadores
### Operador Ternario
Permite almacenar el retorno del valor dependiendo de la respuesta correcta, existen diferentes tipos de oprerador ternario donde podemos colocar dos respuestas, solo la respuesta correcta y hacer anañidciones entre.

// los if ternarios
```js
 let numero1 = 5;
 let numero2 = 9;

 let resp= numero1 > numero2 ? 'numero 1 es mayor' : 'numero 2 es mayor';
 let resp1= numero1 > numero2 ? 'numero 1 es mayor' : '';

 //if ternario alternativo (con and) and - if (El ampensor(&&) obliga a que ambos lados sean verdaderos para que se cumplan)
 //
 let resp1= numero1 > numero2 && 'numero 1 es mayor';
```


| | Operadores|
|-------|-----------------------------------|
|  a==b     |  Igual Igual (Equality) |
|  a!=b  		|  Es distinto de (Inequalty) |
| a===b | Si son igual igual igual al tipo de dato |
|  a!==b  | Si no es estrictamente igual(tipo de dato)(Estrictamente Diferente) (Non-identify) |
|  a>b   |  Es mayor a(greater than) |
|  a>=   |  Es mayor o igual (greater than or equal) |
|  a<b   |  Es menor que (less than) |
|  a<=b  |  Es menor o igual (less than or equal) |


|  |Operadores Logicos|
|------|---------------------|
| && 	| Si las dos condiciones se cumplen es verdadero |
| //  | Si solo una condicion es verdadero es verdadero |
| !	  | Te retorna el valor boelano contrario de la variable |
| +=	|  Añade a si mismo |

https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Operators/Conditional_Operator
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator

ghosting: reaccionando el mismo bloque de trabajo, querera algo que aun no existia 



## Estrutura de Condicionales
Estructura condicional(if)(Referente solo al else)
Es un artículo de if,va a buscar a su par jerárquico.
## Promesas
Son de naturaleza asincrona. Una promesa puede hacer su trabajo o No hacerlo
Js esta diselado para ejecutar primero las instrucciones sincronas y despues las instrucciones asincronas.

`resolve:` Siempre funciona parte la parte positiva.
`reject:` Siempre funciona para la parte negativa.

```js
const promesa = new Promise(
	//Funcion callback
	(resolve,reject)=>{
	//este bloque indica que quieres que haga
	//setTimeout es una funcion asincrona
	setTimeout(
	()=> console.log('20 seconds to mars'), 5000
	);
	}
);

 
promesa.then(
	console.log('La promesa funciona correctamente')
).catch(
	()=>{
	console.warn('Something worng !!!');
	}
);
```

### Promesa con paso de Parametros

```js

const heroes = [
  {
    id: 1,
    name: 'Batman',
    owner: 'DC'
  }, {
    id: 2,
    name: 'Spiderman',
    owner: 'Marvel'
  }, {
    id: 3,
    name: 'Superman',
    owner: 'DC'
  }, {
    id: 4,
    name: 'Flash',
    owner: 'DC'
  }, {
    id: 5,
    name: 'Wolverine',
    owner: 'Marvel'
  }
]

const getHeroeById = (id) => {
  return new Promise(
    (resolve, reject) => {
      resolve(heroes.find((heroe) => heroe.id === id));
    }
  );
}

  
getHeroeById(4).then(
  (resiviendo_heroe) => {
    console.log('Heroe recibido', resiviendo_heroe);
  }
).catch(
    ()=>{
      console.warn('Something worng !!!');
    }
);
```


