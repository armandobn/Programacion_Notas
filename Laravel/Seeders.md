# Seeders
**Carperta:** database/seeders

## ¿Que es un Seeders?
Los seeders son datos de prueba en mi base de datos, estos los podemos crear desde aplicación, es importante tener a la mano datos de prueba para hacer constar que el módulo en el que se esta trabajando funcione perfectamente.

## Creacion de un Seeder
Crear un seeder
```
php artisan make:seeder CursoSeeder
```

Comando para que nos cree lo que indicamos en el seeders
```
php artisan db:seed
```

Ejecutar tanto el comadando de fresh y seed en consecutivo
```
php artisan migrate:fresh --seed
```

Si no teníamos la migración y es la primera vez
```
php artisan migrate --seed
```

## Dar de alta un seeder
**Carpeta:** database/seeders
**Archivo:** DatabaseSeeder.php

Para poder dar de alta un seeder es importante llamarlo desde el archivo **DatabaseSeeder.php** con la siguiente linea de comando
```
$this->call(HardwareSeeder::class);
```

De esta manera quedaria como resultado por cada seeder que deseemos llamar
```php
<?php
namespace Database\Seeders;
use App\Models\Curso;
use Illuminate\Database\Seeder;

class DatabaseSeeder extends Seeder
{
	 /**
	 * Seed the application's database.
	 *
	 * @return void
	 */
	 public function run()
	 {
		// \App\Models\User::factory(10)->create();
	 $this->call(CursoSeeder::class);
	 }

}
```

**Laravel Recomienda:** trabajarlo de la siguiente manera

```php
<?php
namespace Database\Seeders;
//use App\Models\Curso;
use Illuminate\Database\Seeder;

class DatabaseSeeder extends Seeder
{
	 /**
	 * Seed the application's database.
	 *
	 * @return void
	 */
	 public function run()
	 {
	 //$this->call(CursoSeeder::class);
	 \App\Models\Curso::factory(50)->create();//Recomienda hacerlo asi laravel 8

	 }

}
```