fuction vs metodo
ambas estructuras hacen lo mismo
ambas
- recibir/enviar informacion
Se diferencian con: 
function - las defines tu
method - son llamados por JS (Ya estan definicas por JS)

funcion que no recibe nada, no contiene nada porque no tiene un return
function f1(){console.log("hola")}; (cuerpo de la funcion es todo lo que este entre las llaves)

version transitoria
const f1 = function(){ console.log("hola"); }

version function flecha
const f111 = ()=>{ console.log("hola") }; f111();

Notacion correcta para nombrar las funciones
hola_mundo

function que recive pero no devuelve nada
const f222 = (edad)=>{ console.log("Tu edad es: "+ edad) }; f222(32);

spread (...)
let frutas3 = [...frutas];
console.log(frutas3)

*functional component*

preconstruccion
nombre
objeto
añidacion del array

```js
const persona = {
 id: 01, //id(se le llama llave), 01(se le llama valor)
 nombre: 'armando',
 covid: false,
	 direccion: {
	 calle: 'soledad',
	 numero: 12
	 }
 }

console.log(persona.nombre);
console.log({mascota:'perro'});
```

son un valor discreto (switch)
son casos que ya conoces las posibles respuestas
__

Callback (funcion adentro de otra)
definir que quieres que haga la funcion padre


el flujo de trabajo por cada ves que veas esto '=' es de derecha a izquiera 
<- = <- = <-

Estructura condicional(if)(Referente solo al else)
Es un artículo de if,va a buscar a su par jerárquico.

Guardados
Permanente(Es guardado en una variable)
Temporal(No necesita ser aguardado dentro de una variable)

Una funcion flecha se puede trabajar como una variable tipo objeto, la diferencia sera que no se puede poner parentesis de
invocacion si no referirse solo por su nombre






