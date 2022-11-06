crear app laravel composer  
> composer create-project laravel/laravel app-name

instala paquetes
npm i

protected table - hacer referencia a que tabla vamos a usar

rutas web
rutas api- middleware - interceptor de las peticiones https

cofigureRateLimiting
-peticiones en las api
-evitar ataques SSF

Modules/ - englobando
create
edit
form
index
show

Layouts/
MainLayout

@stack - custom-scritps

{{config('app.name')}} || {{'titulo'}}

$items = User::paginate(5);
return view('modules.users.index',compact('items'))


delete - te borra los datos en crudo
destroy - te da siertos errores si estan relacionados
