Permitir crear aplicaciones _React_ con cero configuración
```text
npx create-react-app my-app
```

### ¿Qué incluye _create-react-app_?

Un proyecto creado con _create-react-app_ , además de React, incluye librerías como:

-   _**Webpack**_: que se encarga de procesar y empaquetar nuestro código _JavaScript_ (con sus dependencias), archivos _CSS_ y otros archivos estáticos como imágenes, vectores, fuentes, etc.
-   _**Babel**_: que nos permite usar nuevas características de _ECMAScript_.
-   _**PostCSS**_: que es una librería para el procesamiento de _CSS_.
-   _**Jest**_: que es una librería para _testing_.
-   etc.

Uno podría configurar un proyecto de _React_ manualmente e incluir cada una de estas librerías, pero es bastante engorroso, _create-react-app_ nos hace la vida más fácil.

### _Scripts_

En la carpeta del proyecto puedes ejecutar los siguientes comandos:

-   _**npm start**_ - inicia el servidor de desarrollo y abre un navegador con la aplicación.x
-   _**npm test**_ - ejecuta las pruebas.
-   _**npm run build**_ - empaqueta la aplicación para producción en la carpeta _**build**_.
-   _**npm run eject**_ - permite cambiar manualmente las librerías y configuración que utiliza _create-react-app_ por defecto. Ten cuidado con este comando, una vez que se expulsa la configuración inicial **no hay vuelta atrás**.

### Algunas reglas importantes:

-   Toda etiqueta debe cerrarse por ejemplo `<br>` debera cerrarse a `<br />`.
-   Los componentes deben devolver un sólo elemento padre.
-   Algunos atributos _HTML_ cambian como:
    -   _**class**_ por _**className**_.
    -   _**for**_ por _**htmlFor**_.
-   Los atributos de un elemento _JSX_ pueden aceptar valores de tipo _String_ entrecomillados o expresiones _JavaScript_ entre llaves, por ejemplo:
    -   `<img alt="Avatar" src={user.avatarURL} />`


### Sintaxis 
Llamar al componente
```jsx
//1 forma
<Componente></Componente>
//2 forma
<Componente/>
```

## Propiedades

Son valores que recibe un componente hijo de uno padre. Se agrupan en un objeto llamado _**props**_, el cual puede recibir diferentes tipos de datos, como:

-   _**Strings**_
-   _**Numbers**_
-   _**Booleans**_
-   _**Arrays**_
-   _**Objects**_
-   _**Functions**_
-   _**React Elements**_
-   _**React Components**_

Las _**props**_ son **inmutables**, es decir, son valores de **sólo lectura**, no se pueden modificar.

El componente las recibe como atributos que se pasan a través de _**JSX**_.

Crear propiedades por defecto
```js
Propiedades.defaultProps={

 porDefecto: "Las Props",

}
```

npm -i -S prop-types


## Estado

El _**state**_ son los valores internos que manejan la lógica y los datos de un componente, permite que éste reaccione a cualquier cambio lo que hará que se vuelva a renderizar en la interfaz.

El estado tiene 3 características importantes:

1.  Es inmutable.
2.  No se puede modificar directamente.
3.  Es asíncrono.

Para hacer cambios hay que hacer uso del método _**setState()**_.

El estado de un componente no es accesible desde otro componente excepto de aquel que lo posee y lo asigna.

La **propagación del estado** fluye de forma **unidireccional** y **descendiente** (hacia abajo), esto significa que un componente padre puede pasar valores de su estado a componentes hijos que lo recibirán como propiedades.

En el momento que los valores del estado del padre sufran cambios esto causará que tanto el padre como los hijos que recibieron esos valores como propiedades se rendericen nuevamente y reaccionen a dicho cambio.

Cada componente que se defina como una clase cuenta con un objeto para almacenar información llamado _**state**_.

Cada vez que cambia el _**state**_ _React_ vuelve a renderizar (pintar) el componente en la vista.