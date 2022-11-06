## [Form Request Validation](https://laravel.com/docs/8.x/validation#form-request-validation)

### [Creating Form Requests](https://laravel.com/docs/8.x/validation#creating-form-requests)

Para escenarios de validación más complejos, es posible que desee crear una "from request". Las from request son clases de solicitud personalizadas que encapsulan su propia lógica de validación y autorización. Para crear una clase de solicitud de formulario, puede utilizar el `make:request` Artisan CLI command.

```bash
php artisan make:request StorePostRequest
```

La clase de form request generada se colocará en el `app/Http/Requests`directorio. Si este directorio no existe, se creará cuando ejecute el `make:request`dominio. Cada solicitud de formulario generada por Laravel tiene dos métodos: `authorize`y `rules`.

Como habrás adivinado, el `authorize`El método es responsable de determinar si el usuario actualmente autenticado puede realizar la acción representada por la solicitud, mientras que el `rules`El método devuelve las reglas de validación que deberían aplicarse a los datos de la solicitud:

```php
/** 
 * Get the validation rules that apply to the request. 
 * 
 * @return array 
 */
 public function rules(){    
	 return [        
		 'title' => 'required|unique:posts|max:255',        
		 'body' => 'required',
	 ];
 }
```

Entonces, ¿cómo se evalúan las reglas de validación? Todo lo que necesita hacer es escribir la solicitud en el método de su controlador. La solicitud de formulario entrante se valida antes de que se llame al método del controlador, lo que significa que no necesita saturar su controlador con ninguna lógica de validación:

```php
/**
* Store a new blog post.
*
* @param \App\Http\Requests\StorePostRequest $request
* @return Illuminate\Http\Response
*/

public function store(StorePostRequest $request)
{
	// The incoming request is valid...
	// Retrieve the validated input data...
	$validated = $request->validated();
	// Retrieve a portion of the validated input data...
	$validated = $request->safe()->only(['name', 'email']);
	$validated = $request->safe()->except(['name', 'email']);
}
```

Si falla la validación, se generará una respuesta de redireccionamiento para enviar al usuario de regreso a su ubicación anterior. Los errores también se mostrarán en la sesión para que estén disponibles para su visualización. Si la solicitud era una solicitud XHR, se devolverá al usuario una respuesta HTTP con un código de estado 422 que incluye una representación JSON de los errores de validación.

#### [Adición de enlaces posteriores a solicitudes de formulario](https://laravel.com/docs/8.x/validation#adding-after-hooks-to-form-requests)

### [Personalización de los mensajes de error](https://laravel.com/docs/9.x/validation#customizing-the-error-messages)

Puede personalizar los mensajes de error utilizados por la solicitud de formulario anulando el `messages`método. Este método debería devolver una matriz de pares de attribute/rule y sus correspondientes mensajes de error:

```php
/** 
* Get the error messages for the defined validation rules. 
* 
* @return array 
* 
**/
public function messages(){    
	return [        
		'title.required' => 'A title is required',        
		'body.required' => 'A message is required',    
	];
}
```