-------Extra-----
*web.php
return redirect('ruta'); //Redirecciona a esa ruta
Route::redirect('redireccionamineto','ruta');

Controller.php
dd($nomida); //poder ver una variable si esta viajando pero lo demas no se vera
dd($nomida,$pago);

*Llamar imagenes desde el public
public/fotos/robert.phg ...Donde esta alojado la foto
src="{{asset('fotos/robert.PNG')}}"

*Redirigir a otras vistas
<a href="{{route('salir')}}">Cerrar</a>
**Se le da un nombre al controlador para que pueda dectectar
Route::get('cursos/{curso}', [CursoController::class, 'show'])->name('salir'); 