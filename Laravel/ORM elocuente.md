# ORM(Asignacion objeto-relacional)
## ¿Que es un ORM?
El mapeo objeto-relacional es una tecnica de programacion para convertir datos entre el sistem de tipos utilizando en un lenguaje de programacion orientado a objetos y la utilizacion de una base de datos relacional como motro de persistencia.

Esto quiere decir que la aplicación tomará a la base de datos como si fuera un objeto de la misma aplicación.

## Tinker
### ¿Que es tineker?
Tinker le permite interactuar con toda su aplicacion Larabel en linea de comando, incluido el ORM de Eloquent, trabajos,eventos y mas.

Ingresar a Tinker:
```
php artisan tinker
```

Salir de Tinker
```
exit;
```

### Agregar información con tinker

1. Indicar el modelo a usar
```php
>>> use App\Models\Curso;
```
2. Crear una instancia de esta clase
```php
>>> $curso = new Curso;
```
3. Llenar de propiedades
```php
>>> $curso->name = 'Laravel';
=> "Laravel"
>>> $curso->descripcion = 'El merjo frameworke de PHP';
=> "El merjo frameworke de PHP"

```
4. Aguardar el registro
```php
>>> $curso->save();
=> true
```


Devolver que tiene el objeto
```php
>>> $curso;
=> App\Models\Curso {#3390
     name: "Laravel",
     description: "El merjo frameworke de PHP",
   }
```
 
 
Cambiar los atributos
```php
>>> $curso->descripcion = "El mejor framework de mundo";
=> "El mejor framework de mundo"
>>> $curso
=> App\Models\Curso {#3388
     name: "Laravel",
     descripcion: "El mejor framework de mundo",
     updated_at: "2021-08-09 20:50:20",
     created_at: "2021-08-09 20:50:20",
     id: 1,
   }

```

Recupera todos los datos de la tabla
$cursos = Curso::All();
Me devuelve una collecion de datos de la categoria y el dato
>>> $cursos = Curso::where('categoria','Diseño Web')->get();

Me devuelve la collecion en orden descendente
 $cursos = Curso::where('categoria','Diseño Web')->orderBy('id','desc')->get();

Solo devuelve el primer registro de la collecion
>>> $cursos = Curso::where('categoria','Diseño Web')->orderBy('name','asc')->first();

Devuelve una collecion especifica de que campos mostrar
 $cursos = Curso::select('name','descripcion')->get();
 
 Devuelve la cantidad especifica de registros
 >>> $cursos = Curso::select('name','descripcion')->take(5)->get();

Busca por id el elemento que queremos
$cursos = Curso::find(5);
 

Devuelve los registros especificados en un rango
>>> Curso::where('id','>','45')->get();

Tambien acepta caracteres especiales
>>> Curso::where('name','like','%Dicta%')->get();



 @foreach ($docens as $docen)

 @if($docen->categoria == $tabla[0]->categoria)

 <input type="text" class="form-control" value="{{$motivo=$docen->denominacion}}" disabled>

 @endif

 @endforeach

 @foreach ($admins as $admin)

 @if($admin->categoria == $tabla[0]->categoria)

 <input type="text" class="form-control" value="{{$motivo=$admin->denominacion}}" disabled>

 @endif

 @endforeach
 
 
 create database alumnos;
 use alumnos;
 
 create table usuarios(
 		id int not null auto_increment primary key,
		nombre varchar(255),
		apellido varchar(255),
		edad int,
	  created_at datetime NOT NULL,
    updated_at datetime NOT NULL
 )
 
 
 
 
 tabla: usuarios(plural)   cuales  
 model: usuario (singular)   cual    
