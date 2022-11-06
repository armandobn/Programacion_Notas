## Propiedades

   - data: datos que va a contener la aplicacion
   - methods 
   - props: Propiedades compartidas
   - mounted: es un evento
   - created: es un evento
   - computed
   - watch
   - destroyed

## Introduccion a VueJS
   
```html
<div id="app"><!-- Nuestro contenedor-->
	<!-- Para poder llamar a nuestros datos utilizamos las dobe llaves con respecto a su propiedad-->
	hola {{nombre}} estamos en el año {{anio}} 
 	{{meses[0]}}
</div>

<script src="https://unpkg.com/vue@3"></script>
<script>
//Propiedades
//Data, methods, props, mounted, created, computed, watch, destroyed
	
	const holaMundo = { 
    	data(){ //Creamos una propiedad data
			return{ //Retornamos el valor que le indiquemos
				nombre: 'jairo',
				anio: 2021,
				meses: ['Enero','Febrero']
			}
      	}
    }

var mountedApp = Vue.createApp(holaMundo).mount('#app');//Como tiene # accedemos por ID
//Creamos la aplicacion y la montamos en un contenedor(mount).

//Si solo cocolamos esto no podremos acceder a las propiedades desde la consola mas facilmente
//Vue.createApp(holaMundo).mount('#app');

	//De esta manera sera mas facil acceder a sus propiedades desde la consola
//var mountedApp = Vue.createApp(holaMundo).mount('#app');

</script>
```

## Llamada de Métodos y Manipulación de Datos: La Reactividad de Vue

```vue
<div id="app">
    Contador: {{contador}}
    <button type="button" v-on:click="stopInterval">{{btnMessage}}</button>
</div>

<script src="https://unpkg.com/vue@3"></script>

<script>

//Data, methods, props, mounted, created, computed, watch, destroyed
	const holaMundo = {
      data(){
        return{
         contador: 0,
         interval: null,
         isRunning: false,
         btnMessage: "Detener"
        }
      },mounted(){ //Montamos la aplicacion con mounted
          this.interval=setInterval(()=>{//llamamos a nuestro metodo
            this.contador++;
          }, 1000);
          this.isRunning=true;
        },methods: { //Definimos(crear) los metodos
          stopInterval(){
            if(this.isRunning){//Checamos estado
              clearInterval(this.interval);
              this.isRunning=false;
              this.btnMessage="Continuar";
            }else{
              this.interval=setInterval(()=>{
                this.contador++;
              }, 1000);
              this.isRunning=true;
              this.btnMessage="Detener";
            }
          }
        }
    }

	var mountedApp=Vue.createApp(holaMundo).mount('#app');

</script>
```

## Binding de Atributos HTML con v-bind

```vue
<div id="app"><!--Utilizamos el v-bind para llamar al objeto, data-hola (sin comprender aun)-->
    <label v-bind:title="titulo" v-bind:data-hola="titulo">Hola Mundo</label>
    <hr>
	<!--por medio del v-on le pasamos la propiedad click y llamamos el metodo a ejecutar con su debido parametro a pasar-->
    <button v-on:click="mostrarImagen('anime.jpg')">Imagen Anime</button>
    <button v-on:click="mostrarImagen('anime2.jpg')">Imagen Anime 2</button>
    <hr>
	<img v-bind:src="imagen"> <!--Se cargaran las imagenes-->
</div>

 <script src="https://unpkg.com/vue@3"></script>
 <script>
    
    const holaMundo = {
      data(){
        return{ //retornara la url de la imagen que queramos
          titulo: 'Este es un titulo dinamico',
          imagen: ""
		}
      },
      methods:{
		//utilizamos un metodo para cambiar la proiedad imagen
        mostrarImagen(imagen){ //pasamos por parametro el valor que indiquemos
          this.imagen=imagen; /*Hace referencia a la propiedad imagen metiante un this y le damos el valor pasado por parametro*/
        }
      }
    }

	var mountedApp=Vue.createApp(holaMundo).mount('#app');
</script>

```

## Binding de Doble Vía con v-model: Interacción del Usuario
El usuario cambie el valor de la propiedad en ambas direcciones, se hace con v-model
Hacer interaccion en ambas direcciones, donde se hace un cambio dentro de la propiedad se refleje en la aplicacion y viseversa.
El valor introducido por el utilizado se cambia en automatico
```vue
<div id="app">
    <label>Escribe tu nombre</label>
    <input type="text" v-model="nombre">
    <hr>
    <h5>Hola {{nombre}}</h5>
    <hr>
    <select v-model="fruta"><!--Indicas a la propiedad a la que quieres acceder y devuelve el valor seleccionado con el value-->
      <option value="1">Manzana</option>
      <option value="2">Pera</option>
      <option value="3">Uva</option>
    </select>
    Fruta seleccionada: {{fruta}} <!--Muestra el valor tomado-->
    <input type="checkbox" v-model="activo">
    {{activo}}
 </div>
 <script src="https://unpkg.com/vue@3"></script>
 	<script>
    
    //v-model=""
    const holaMundo = {
      data(){
        return{
          nombre: '',
          fruta:'',
          activo:false
        }
      }
    }
    var mountedApp=Vue.createApp(holaMundo).mount('#app');
 </script>
```

## Bucles: Estructura v-for, Recorrido de Arrays y Creación de Listas
v-for tiene que utilizarse en aquel objeto queremos que se repita
v-bing:key diferenciar de cada uno de los elementos(cuando utilicemos el v-for)

```vue
<div id="app">
	<ul>
      <li v-for="fruta in frutas" v-bind:key="fruta">{{fruta}}</li>
    </ul>
    <hr>
    <ul>
    	<li v-for="(fruta, index) in frutas_con_id" v-bind:key="fruta">
			Indice:{{index}} {{fruta.id}} - {{fruta.nombre}}</li>
    	</ul>
    <select v-model="frutaId">
		<!-- v-bind:value el valor que tendra y accedemos al valor definiendo como valor, el acceso al objeto englobado entre comillas-->	
		<option v-for="fruta in frutas_con_id" v-bind:value="fruta.id">	
			{{fruta.nombre}}	
		</option>
   </select>
</div>
  
<script src="https://unpkg.com/vue@3"></script>
<script>
    const holaMundo = {
		data(){
			return{
            	frutaId:2,
            	frutas: ['Manzana','Pera','Uva'],
            	frutas_con_id:[
					{
						id:1,
						nombre: 'Manzana'
					},
					{
						id:2,
						nombre: 'Pera'
					},
					{
						id:3,
						nombre: 'Uva'
					}
            	]
        	}
      	}
    }
    var mountedApp = Vue.createApp(holaMundo).mount('#app');
</script>
```

## Bucles Anidados con v-for, Obtener Índice, Bucles a Partir de Rangos

```vue
 <div id="app">
    <ul>
      <li v-for="(fruta, index) in frutas_con_id" v-bind:key="fruta">
        Indice: {{index}} {{fruta.id}} - {{fruta.nombre}}
      	<ul>
        	<ul>
          		<li v-for="pais in fruta.paises_origen"><!--Utilizamos la doble añidacion de- v-for para recorres la otra coleccion-->
					Pais: {{pais.id}} - {{pais.pais}
			 	</li>
			</ul>
        </ul>
      </li>
	</ul>
    <ul>
		<!---Definimos solo para recorrer las letras que contiene-->
      <li v-for="l in letras">{{l}}</li>
    </ul>
    <ul>
		<!---Definir hasta donde queremos que recorra-->
      <li v-for="numero in 100">{{numero / 2}}</li>
    </ul>
  </div>
  

  <script src="https://unpkg.com/vue@3"></script>
  <script>
    const holaMundo = {
      data(){
        return{
          letras: 'abcde',
            frutas_con_id:[
              {
                id:1,
                nombre: 'Manzana',
                paises_origen: [
                  {
                    id_pais: 1,
                    pais: 'El Salvador'
                  },
                  {
                    id_pais: 2,
                    pais: 'Guatemala'
                  }
                ]
              },
              {
                id:2,
                nombre: 'Pera',
                paises_origen: [
                  {
                    id_pais: 3,
                    pais: 'Honduras'
                  },
                  {
                    id_pais: 4,
                    pais: 'Nicaragua'
                  }
                ]
              },
              {
                id:3,
                nombre: 'Uva',
                paises_origen: null
              }
            ]
        }
      }
    }

  

    var mountedApp = Vue.createApp(holaMundo).mount('#app');
 </script>
```