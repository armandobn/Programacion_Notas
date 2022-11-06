# Plantillas de Blade
Blade es el motor de plantillas simple pero potente que se incluye con Laravel. A diferencia de algunos motores de plantillas PHP, Blade no le impide usar código PHP simple en sus plantillas. De hecho, todas las plantillas de Blade se compilan en código PHP simple y se almacenan en caché hasta que se modifican, lo que significa que Blade prácticamente no agrega gastos generales a su aplicación. 
crud
create(crear)
read(leer)
update(actualizar)
delete(Eliminar)
Los archivos de plantilla Blade usan la extencion `.blade.php` y normalmente las vistas se almacenan en el directorio`resources/views`.

Directorio:  `resources/views`
Extension del archivo: `.blade.php`

Las vistas de hoja se pueden devolver, utilizando el `view`ayudante global, la cual son las siguientes:
- `rutas` 
- `controladores` 

## [Visualización de datos](https://laravel.com/docs/9.x/blade#displaying-data)

Puede mostrar los datos que se pasan a sus vistas de Blade envolviendo la variable entre llaves. Por ejemplo, dada la siguiente ruta:

Archivo: *web.php*

```php
Route::get('/', function () {    return view('welcome', ['name' => 'Samantha']);});
```

Puede mostrar el contenido de la `name`variable así:
Archivo: *welcome.blade.php*

```php
Hello, {{ $name }}.
```

