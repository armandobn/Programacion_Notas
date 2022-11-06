
# Rutas/Route/Web.php

1. [[#Crear Ruta]]
2. [[#Varibles por URL]] 
   1. [[#Pasar variable por URL]]
   2. [[#Pasar mas de 1 Varible por URL]]
   3. [[#Pasar 1 varible mas otra varible opcional]]
3. [[#Tipos de route]]
   1. [[#GET]]
   2. [[#POST]]
   3. [[#PUT]]
   4. [[#DELETE]]

*Carpeta Router/web.php

## Crear Ruta
```php
Route::get('cursos',function(){
    return "Bienvenido a la pagina cursos";
});
```

## Varibles por URL

### Pasar variable por URL

```php
Route::get('cursos/{curso}',function($curso){
    return "bienvenido al curso: $curso";
});

```

### Pasar mas de 1 Varible por URL

 ```php
 Route::get('cursos/{curso}/{categoria}', function ($curso,$categoria) {
    return "Bienvenido al curso $curso, de la categoria $categoria";
});
 ```

### Pasar 1 varible mas otra varible opcional
? -Lo vuelve opcional la variable pero tambien hay que pasarle un valor null
```php
Route::get('cursos/{curso}/{categoria?}', function ($curso,$categoria = null) {
    if($categoria){
        return "Bienvenido al curso $curso, de la categoria $categoria";
    }else{
        return "Bienvenido al curso $curso";
    } 
});
```


## Tipos de route
### GET
```php
Route::get('cursos', [CursoController::class, 'index'])->name('cursos.index');
```
### POST
```php
Route::post('cursos',  [CursoController::class, 'store'])->name('cursos.store');
```
### PUT
```php
Route::put('cursos/{curso}', [CursoController::class, 'update'])->name('cursos.update');
```
### DELETE
```php
Route::delete('cursos/{curso}', [CursoController::class, 'destroy'])->name('cursos.destroy');
```



muestra las rutas creadas
php artisan r:l

