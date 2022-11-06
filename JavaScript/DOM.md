# DOM(Document Objet Model/Modelo de Objeto de Documento)
## Nodo
**¿Que es un nodo?**
Un nodo en el DOM es cualquier etiqueta del cuerpo, como un parrafo, el mismo body o incluso las etiquetas de una lista.
Los nodos no siempre son etiquetas, aveces suelen ser otro tipo de elementos.

### Tipos de Nodo
- Document: el nodo document es el nodo raiz, a partir del cual derivan el resto de nodos
- Element: nodos definidos por etiquetas html
- Text: el texto dentro de un nodo element se considera un nuevo nodo hijo de tipo text(texto)
- Attribute: los atributos de las etiquetas definen nodos, (en JavaScritpt no lo veremos como nodos, si no como informacion asociada al nodo del topo element)
- Comentarios y otros: los comentarios y otros elementos como las declaraciones doctype en cabecera de los documentos HTML generan nodos

#### Document
##### Metodos de seleccion de elementos

###### Index
1. [[#getElementById]]
2. [[#getElementsByTagName]]
3. [[#querySelector]]
4. [[#querySelectorAll]]
5. [[#Nota]]

###### getElementById()
Seleccion un elemento por ID
```html
<div id="parrafo"></div>
```

```js
//document.getElementById();
let parrafo= document.getElementById("parrafo");
document.write(parrafo);
```

###### getElementsByTagName()
Selecciona todos los elementos que coincidan con el nombre de la etiqueta especifica

```html
<div name="p"></div>
```

```js
//getElementsByTagName();
let parrafo= document.getElementsByTagName("p"); //devuelve una lista de coleccion *no un array*
 document.write(parrafo);
```

###### querySelector()
Devuelve el primer elemento que coincida con el grupo especificado de los selectores
```js
//querySelector();
parrafo= document.querySelector(".parrafo"); 
document.write(parrafo);
```

###### querySelectorAll();
Devuelve todos los elementos que coincidan con el grupo especificado de selectores
```js
//querySelectorAll();
parrafo= document.querySelectorAll(".parrafo"); 
 document.write(parrafo[0]);
```


###### Nota
- El document.getElementById es el mas optimo cuando se trata de seleccionar por ID
- Para seleccionar un elemento por su ID #
- Para seleccionar un elemento por su CLASS .

##### Metodos para Definir, Obtener y Eliminar valores de atributos

###### index
1. [[#setAttribute]]
2. [[#getAttribute]]
3. [[#removeAttribute]]

###### setAttribute()
Agrega o Modifica el valor de un atributo
```js
//setAttribute();
const rangoEtario = document.querySelector(".rangoEtario");                     
rangoEtario.setAttribute("type","text");//atributo,valor
```

```html
<input class="rangoEtario">
```

###### getAttribute()
Obtiene el valor de un atributo
```js
//getAttribute();
const rangoEtario = document.querySelector(".rangoEtario");        
valorDelAtributo= rangoEtario.getAttribute("type");
document.write(valorDelAtributo);
```

```html
<input type="text" class="rangoEtario">
```

###### removeAttribute()
Remueve el valor de un atributo
```js
//removeAttribute();
const rangoEtario = document.querySelector(".rangoEtario");        
valorDelAtributo= rangoEtario.removeAttribute("type");
document.write(valorDelAtributo);
```

```html
<input type="text" class="rangoEtario">
```

##### Atributos Globales

Se pueden aplicar a todos los elementos porque son atributos globales 

**class:** Lista de clases del elemento separadas por espacios
**contenteditable:** Indica si el elemento puede ser modificable por el usuario(bool)
**dir:** Indica la direccionalidad del texto
**hidden:** Indica si el elemento aun no es, o ya no es, relevante.
**tabindex:** Indica si el elemento puede obtener un focus de input
**title:** Contiene un texto con informacion relacionada al elemento al que pertenece
**id:** Define un identificador unico (No hay informacion aun definida)
**style:** Contiene declaraciones de estilo css para ser aplicadas al elemento[[#Atributos de style]]

###### index

1. [[#contentEditable]]
2. [[#dir]]
3. [[#hidden]]
4. [[#tabindex]]
5. [[#title]]

###### contentEditable
Pude editar el contenido dependiendo del valor que le pasen
```js
 const titulo = document.querySelector(".titulo");
 titulo.setAttribute("contentEditable","false");//valor: true(editable),false(no editable)
```

```html
<h1 class="titulo">Este es un titulo</h1>
```

###### dir
Indica la direccionalidad del texto
```js
 const titulo = document.querySelector(".titulo");
 titulo.setAttribute("dir","rtl");/*left to right(rtl),rigth to left(rtl)*/
```

```html
<h1 class="titulo">Este es un titulo</h1>
```

###### hidden
Indica si el elemento aun no es, o ya no es, relevante.
```js
 const titulo = document.querySelector(".titulo");
 titulo.setAttribute("hidden","false");//valor: true,false
```

```html
<h1 class="titulo">Este es un titulo</h1>
```

###### tabindex

`Que es tabindex:`
Por medio del tabuladore recorre los elementos deacuerdo al orden del atributo del tabindex.
Tiene dos usos:
- Indica si el elemento puede obtener un focus de input
- Poder cambiar el orden del tabindex

Focus
```js
 const titulo = document.querySelector(".titulo");
 titulo.setAttribute("tabindex","0");

/*
'' - colocas otra cosa no lo permita
0  - permite hacer un foucus
*/
```

```html
<a class="titulo">Este es un titulo<a/>
```

Orden del tabulador deacuerdo al elemento
```js
 const titulo = document.querySelector(".titulo");
 titulo.setAttribute("tabindex","0");

/*
Por medio del tabulador recorre el orden del tabindex, deacuerdo
al tributo del tabindex.
*/
```

```html
<a class="titulo" tabindex="1">Este es un titulo<a/>
<a class="titulo" tabindex="3">Este es un titulo<a/>
<a class="titulo" tabindex="2">Este es un titulo<a/>
```

###### title
Contiene un texto con informacion relacionada al elemento al que pertenece
```js
 const titulo = document.querySelector(".titulo");
 titulo.setAttribute("title","jajaj xd");//Atributo,valor
```

```html
<h1 class="titulo" title="titulo normal">Este es un titulo</h1>
```

##### Atributos de Inputs

###### index
1. [[#className]]
2. [[#value]]
3. [[#type]]
4. [[#accept]]
5. [[#form]]
6. [[#minLength]]
7. [[#placeholder]]
8. [[#required]]

###### className
Acceder directamente al atributo className(nombre del atributo class) y obtiene el valor
```js
const input = document.querySelector(".input-normal");
document.write(input.className);
```

```html
<input type="text" class="input-normal">
```

###### value
Acceder directamente al atributo value y obtiene el valor
```js
const input = document.querySelector(".input-normal");
document.write(input.value);
```

```html
<input type="text" class="input-normal" value="123">
```
###### type
Acceder directamente al atributo type deacuerdo al valor dado y obtiene el valor
```js
const input = document.querySelector(".input-normal");
document.write(input.type="text");
//document.write(input.type="color");
```

```html
<input type="text" class="input-normal">
```
###### accept 
Solo acepta un tipo de formato de imagen deacuerdo al que le indiquemos, ejemplo:
- png
- gif

```js
const input = document.querySelector(".input-normal");
input.accept="image/png";
//input.accept="image/gif";
```

```html
<input type="file" class="input-normal">
```
###### form 
//Aun no le entiendo del todo

No se actualiza porque no esta enviando los datos del formulario
Justamente porque no forma parte de ningun formulario
```html
<form name="formulario">
    <input type="text" name="">
    <input type="submit" name="">
</form>
<input type="submit" name=""> 
```

Aqui si lo envia y se utiliza el ID: asocia el submit al formulario apesar de que no forma parte del form
```html
<form id="formulario">
    <input type="text" name="">
    <input type="submit" name="">
 </form>
 <input type="submit" name="" form="formulario"> 
```

###### minLength
Le indicamos cuantos caracteres como minimo debe contener para poder ser enviado
```js
const input = document.querySelector(".input-normal");
input.minLength=4;
```

```html
<form id="formulario">
    <input type="text" class="input-normal">
    <input type="submit">
 </form>
```

Lo mismo pero ahora con setAtributte
```js
const input = document.querySelector(".input-normal");
input.setAtribute('minlength','5');
```

```html
<form id="formulario">
    <input type="text" class="input-normal">
    <input type="submit">
 </form>
```
###### placeholder
Le damos valor al placeholder
```js
const input = document.querySelector(".input-normal");
input.placeholder="que pasa mami";
```

```html
<form id="formulario">
    <input type="text" class="input-normal">
    <input type="submit">
 </form>
```
###### required
Permite indicar si es un campo requerido o no desde JS
```js
const input = document.querySelector(".input-normal");
input.required=" ";
input.required="required"; 
//poner cualquier cosa pide que es un campo requerido, incluso si solo
//le damos un espacio
```

```html
<form id="formulario">
    <input type="text" class="input-normal">
    <input type="submit">
 </form>
```

##### Atributos de style
Modificamos los atributos de Style
**id:** Define un identificador unico
**style:** Contiene declaraciones de estilo css para ser aplicadas al elemento

```js
const titulo = document.querySelector(".titulo");
titulo.style.backgroundColor="#32b";
//titulo.style.color="red";
//titulo.style.padding="30px";
```

```html
<h1 class="titulo">Elemento a Modificar</h1>
```

`Nota:` 
En la propiedad de ccs se maneja con un - pero aqui quitamos la - y utilizamos la notacion CameCase.

**Ejemplo:**
background-color //CCS
backgroundColor  //JAVASCRIPT


##### Clases, classList y Metodos de classList

###### index
1. [[#add]]
2. [[#remove]]
3. [[#contains]]
4. [[#toggle]]
5. [[#replace]]
6. [[#agregar varios]]

###### add()	
Añade una clase
```js
const titulo = document.querySelector(".titulo");
titulo.classList.add("grande");
```

```html
<h1 class="titulo">Elemento a Modificar</h1>
```

```css
.grande{
	fond-size: 50px;
}
```

###### remove()
Remueve una clase
```js
const titulo = document.querySelector(".titulo");
titulo.classList.remove("grande");
```

```html
<h1 class="titulo grande">Elemento a Modificar</h1>
```

```css
.grande{
	fond-size: 50px;
}
```

###### item()
Devuelve la clase del indice especificado
```js
const titulo = document.querySelector(".titulo");
let valor= titulo.classList.item(0);
```

```html
<h1 class="titulo grande gomita">Elemento a Modificar</h1>
```

###### contains() 
Verifica si ese elemento posee o no, la clase especificada
```js
const titulo = document.querySelector(".titulo");
let valor= titulo.classList.contains("grande");
document.write(valor);
```

```html
<h1 class="titulo grande">Elemento a Modificar</h1>
```

###### toggle()
Si no tiene la clase especificada, la agrega, si ya la tiene, la elimina
```js
const titulo = document.querySelector(".titulo");
let valor= titulo.classList.toggle("grande");
document.write(valor);
 
//Parametro Opcional para forzar siempre a la clase: true(muestra) false(elimina)
const titulo = document.querySelector(".titulo");
let valor= titulo.classList.toggle("grande", true);
document.write(valor);
```

```html
<h1 class="titulo grande">Elemento a Modificar</h1>
```

```css
.grande{
	fond-size: 50px;
}
```

###### replace() 
Remplaza una clase por otra y nos devuelve true, en caso de que no encuentre la clase devuelve false
```js
const titulo = document.querySelector(".titulo");
let valor= titulo.classList.replace("grande", "chico");
document.write(valor);
```

```html
<h1 class="titulo grande">Elemento a Modificar</h1>
```

```css
.grande{
	fond-size: 50px;
}
```

###### agregar varios
```js
div.classList.add(`item-${i}`,`flex-item`);	
```

##### Obtencion y Modificacion de elemento
textContent -Devuelve el texto de cualquier nodo
innerText -(no estandar)Devuelve el texto visible de un node element
outerText- -(no estandar)Devuelve el texto que de las etiquetas html incluidas las etiquetas

innerHTML -Devuelve el contenido html de un elemento
outerHTML -Devuelve el codigo HTML completo del elemento

###### index
1. [[#textContent]]
2. [[#innerHTML]]
3. [[#outerHTML]]
4. [[#Nota]]

###### textContent
Devuelve el texto de cualquier nodo
```js
const titulo = document.querySelector('.titulo');
let resultado = titulo.textContent;
document.write(resultado); 
```

```html
<h1 class="titulo">Elemento a <b style="visibility: hidden;">Modificar</b></h1>
```

###### innerHTML
Devuelve el contenido html de un elemento
```js
const titulo = document.querySelector('.titulo');
llet resultado = titulo.innerHTML;
document.write(resultado); 
alert(resultado);
```

```html
<h1 class="titulo">Elemento a <b style="visibility: hidden;">Modificar</b></h1>
```

###### outerHTML 
Devuelve el codigo HTML completo del elemento
```js
const titulo = document.querySelector('.titulo');
let resultado = titulo.outerHTML;
document.write(resultado); 
alert(resultado);
```

```html
<h1 class="titulo">Elemento a <b style="visibility: hidden;">Modificar</b></h1>
```

###### Nota
- Es visible ver el cambio atravez de un alert para: innerHTML y outerHTML

##### Creacion de Elementos

`createElement():`  Crea un nodo de elemento con el nombre especificado.
`createTextNode():` Crea un nodo de texto
`appendChild():` Agrega un nuevo nodo al final de la lista de un elemento hijo de un elemento padre especificado.
`createDocumentFragment():` Crea un nuevo DocumentFragment vacio, dentro del cual un nodo del DOM puede ser adicionado para construir un nuevo arbol DOM fuera de pantalla.

###### index
1. [[#createElement]]
2. [[#createTextNode]]
3. [[#appendChild]]
4. [[#createDocumentFragment]]


###### createElement()
Crea un nodo de elemento con el nombre especificado.
```js
const contenedor= document.querySelector(".contenedor");
const item = document.createElement("LI");//todo en mayuscula
document.write(item)
```

```html
<div class="contenedor"></div>
```
###### createTextNode()
Crea un nodo de texto
```js
const contenedor= document.querySelector(".contenedor");
const item = document.createElement("LI");//todo en mayuscula
const textDelItem = document.createTextNode("Esta es un item de la lista");
itme.innetHTML = textDelItem;
console.log(textDelItem);
```

```html
<div class="contenedor"></div>
```

###### appendChild() 
Agrega un nuevo nodo al final de la lista de un elemento hijo de un elemento padre especificado.
```js
const contenedor= document.querySelector(".contenedor");
const item = document.createElement("LI");//todo en mayuscula
const textDelItem = document.createTextNode("Esta es un item de la lista");
item.appendChild(textDelItem);//lo crea al item
contenedor.appendChild(item);//lo agrega al contenedor
console.log(item);
```

```html
<div class="contenedor"></div>
```
Otra forma de hacer para un appendChild, solo te devuelve en texto
```js
const contenedor= document.querySelector(".contenedor");
const item = document.createElement("LI");//todo en mayuscula
item.innerHTML="Esta es un item de la lista";
contenedor.appendChild(item);
console.log(item);
```

```html
<div class="contenedor"></div>
```
###### createDocumentFragment() 
Crea un nuevo DocumentFragment vacio, dentro del cual un nodo del DOM puede ser adicionado para construir un nuevo arbol DOM fuera de pantalla.

```js
//consume menos recursos al  crear una lista de appenchild
const contenedor= document.querySelector(".contenedor");
const fragmento = document.createDocumentFragment();
for(i=0; i<20; i++){
  const item = document.createElement("LI");//todo en mayuscula
  item.innerHTML="Esta es un item de la lista";
  fragmento.appendChild(item);
}
contenedor.appendChild(fragmento);
console.log(fragmento);
```

```html
<div class="contenedor"></div>
```


##### Obtencion y Modificacion de childs(Hijos)

`firstChild:` Encuentra el primer nodo hijo(importar quitar espacios)
`lastChild:` Encuentra el ultimo nodo hijo(importar quitar espacios)
`firsElementChild:` Encuentra el primer nodo hijo(sin importar espacios)
`lastElementChild:`  Encuentra el ultimo node hijo(sin importar espacios)
`chilNodes:` Devuelve toda la lista de los nodos hijos(NodeList)
`childen:` Devuelve toda la lista de los nodos hijos(HTMLCollection)

###### index
1. [[#firstChild]]
2. [[#lastChild]]
3. [[#firsElementChild]]
4. [[#lastElementChild]]
5. [[#chilNodes]]
6. [[#childen]]
7. [[#Nota]]

###### firstChild
Encuentra el primer nodo hijo(importar quitar espacios)
```js
const contenedor= document.querySelector(".contenedor");
const primerHijo = contenedor.firstChild;
console.log(primerHijo);
```

```html
<div class="contenedor">
	<h2>Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```

###### lastChild 
Encuentra el ultimo nodo hijo(importar quitar espacios)
```js
const contenedor= document.querySelector(".contenedor");
const primerHijo = contenedor.lastChild;
console.log(primerHijo);
```

```html
<div class="contenedor">
	<h2>Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```

###### firsElementChild
Encuentra el primer nodo hijo(sin importar espacios)
```js
const contenedor= document.querySelector(".contenedor");
const primerHijo = contenedor.firstElementChild;
console.log(primerHijo);
```

```html
<div class="contenedor">
	<h2>Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```
###### lastElementChild 
Encuentra el ultimo node hijo(sin importar espacios)
```js
const contenedor= document.querySelector(".contenedor");
const primerHijo = contenedor.lastElementChild;
console.log(primerHijo);
```

```html
<div class="contenedor">
	<h2>Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```

###### chilNodes 
Devuelve toda la lista de los nodos hijos(NodeList) (Esto es un NodeList)
```js
const contenedor= document.querySelector(".contenedor");
const hijos = contenedor.childNodes;
console.log(hijos);
hijos.forEach(hijo => console.log(hijo));
//De esta manera solo lo puedes recorrer
```

```html
<div class="contenedor">
	<h2>Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>
</div>
```

###### childen
Devuelve toda la lista de los nodos hijos(HTMLCollection)(HTMLCollection no se puede recorrer con un forEach)
```js
const contenedor= document.querySelector(".contenedor");
const hijos = contenedor.children;
console.log(hijos);
//De esta forma los puedes recorrer
for(hijo of hijos){ //devuelve el valor
 console.log(hijo);
}

for(hijo in hijos){ //devuelve los indices
 console.log(hijo);
}
```

```html
<div class="contenedor">
	<h2>Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```

###### Nota
- Es importante que no contengan especios entre los elementos.
##### Metodos de Childs(hijos)

`replaceChild():` Remplaza un elemento
`removeChild():` Remueve un elemento
`hasChildNodes():` Verifica si tiene un elemento hijo

###### index

1. [[#replaceChild]]
2. [[#removeChild]]
3. [[#hasChildNodes]]
###### replaceChild()
Remplaza un elemento
```js
const contenedor= document.querySelector(".contenedor");
const parrafo = document.createElement("P").innerHTML = "Parrafo";
const h2_nuevo = document.createElement("H2");
h2_nuevo.innerHTML= "Titulo";
const h2_antiguo = document.querySelector(".h2");
contenedor.replaceChild(h2_nuevo,h2_antiguo);
```

```html
<div class="contenedor">
	<h2 class="h2" >Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```
###### removeChild() 
Remueve un elemento
```js
const contenedor= document.querySelector(".contenedor");
const h2_antiguo = document.querySelector(".h2");
contenedor.removeChild(h2_antiguo);
```

```html
<div class="contenedor">
	<h2 class="h2" >Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```
###### hasChildNodes()
Verifica si tiene un elemento hijo
```js
const contenedor= document.querySelector(".contenedor");
const h2_antiguo = document.querySelector(".h2");
let respuesta = h2_antiguo.hasChildNodes();//No tiene Hijos
//let respuesta = contenedor.hasChildNodes();//Tiene Hijos
if(respuesta){
  document.write("el elemento tiene hijos");
}else{
  document.write("el elemento NO tiene hijos");
}
```

```html
<div class="contenedor">
	<h2 class="h2" >Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```

##### Metodos de parents(padres)

`parentElement:` busca una etiqueta html padre
`parentNode:` busca nodo padre

###### index
1. [[#parentElement]]
2. [[#parentNode]]

###### parentElement
busca una etiqueta html padre
```js
const h2_antiguo = document.querySelector(".h2");
console.log(h2_antiguo.parentElement);
```

```html
<div class="contenedor">
	<h2 class="h2" >Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```

###### parentNode
busca nodo padre
```js
const h2_antiguo = document.querySelector(".h2");
console.log(h2_antiguo.parentNode);
```

```html
<div class="contenedor">
	<h2 class="h2" >Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```




##### Propierdades de Siblings(hermanos)

Son los que estan bajo el mismo nivel
nextSibling
previousSibling
nextElementSibling: Muestra el siguiente elemento de la etiqueta
previousElementSibling: Muestra el anterior elemento de la etiqueta

###### Index
1. [[#nextSibling]]
2. [[#previousSibling]]
3. [[#nextElementSibling]]
4. [[#previousElementSibling]]

###### nextSibling
```js
const h2_antiguo = document.querySelector(".h2");
console.log(h2_antiguo.nextSibling);
```

```html
<div class="contenedor">
	<h2 class="h2" >Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```

###### previousSibling
```js
const h2_antiguo = document.querySelector(".h2");
console.log(h2_antiguo.previousSibling);
```

```html
<div class="contenedor">
	<h2 class="h2" >Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```

###### nextElementSibling
Muestra el siguiente elemento de la etiqueta
```js
const h2_antiguo = document.querySelector(".h2");
console.log(h2_antiguo.nextElementSibling);
```

```html
<div class="contenedor">
	<h2 class="h2" >Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```
###### previousElementSibling
Muestra el anterior elemento de la etiqueta
```js
const h2_antiguo = document.querySelector(".h2");
console.log(h2_antiguo.previousElementSibling);
```

```html
<div class="contenedor">
	<h2 class="h2" >Un h2 Comun<h2>
	<h4>Un h2 Comun</h4>
	<p>Un simple parrafo</p>	
</div>
```



##### Nodos Extra

###### index
1. [[#closest]]

###### closest()
Selecciona el elemento accendente mas sercano del contenerdor.
Selecciona el contenedor que contenga ese elemento mas sercano.
```js
const div= document.querySelector(".div-3");
console.log(div.closest(".div"));
```

```html
<div class="div">DIV 1
	<div class="div">DIV 2
		<div class="div-3"></div>
	</div>
</div>
```

