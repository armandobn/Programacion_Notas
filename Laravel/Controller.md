# Controller / Controlador

Crear un Controlador, se realiza desde la raiz del proyecto 
```
php artisan make:controller HomeController
```

//web.php
```php
Route::get('/', HomeController::class);
```


//HomeController.php
```php
<?php
namespace App\Http\Controllers; //Donde se encuentra
use Illuminate\Http\Request;

class HomeController extends Controller
{
    //Queremos que solo administre una unica ruta con 					  	   __invoke();
    public function __invoke(){
        // return view('welcome');
        return "Bienvenido a la pagina principal";
    }

}
```


