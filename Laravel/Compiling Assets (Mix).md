# Mix

**Videos Tutoriales**
https://www.youtube.com/watch?v=ROS2w7nyoFg  //Español
https://www.youtube.com/watch?v=mEE0FzQRwG //English+image

## Requisitos
Con **nodejs** lo obtienes todo
- node
- npm

### Instalar Laravel Mix
Se intala sobre la raiz del proyecto
Con el comando
```
npm install
```


### Running Mix
// Run all Mix tasks...
Compila en modo desarrollo
```
npm run dev
```

// Run all Mix tasks and minify output...
Compila en modo Produccion
```
npm run prod
```

**Watching Assets For Changes**
Continuamente se este compilado mientras desarrollamos
```
npm run watch  	   
npm run watch-poll 
```

- Incluir el js dentro del maquetado

Lo llama cuando esta activo el servidor de laravel
```html
<script src="{{ mix('/js/app.js') }}"></script>
```
Solo tienes xampp y tiene la carpeta public en la url
```html
<script src="{{ asset('/js/app.js') }}"></script>
```

Dentro del archivo **webpack.mix**

De esta manera se le agrega el js a mix
```js
mix.js('resources/js/app.js', 'public/js')
 .js('resources/js/docente_c.js', 'public/js')
 .js('resources/js/docente_u.js', 'public/js')
 .js('resources/js/datosTabla.js', 'public/js')
 .postCss('resources/css/app.css', 'public/css', [
 //
 ]);
```


Nota:
- Su scope/alcance no es global y solo su alzance es a nivel del mismo js 


