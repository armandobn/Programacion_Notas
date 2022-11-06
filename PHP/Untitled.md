## Tipo de Datos

|Tipo de Dato|Valores que abarca|Valor devuelto por la funcion gettype|Funcion is_type que devuelve TRUE con este tipo|   |
|---|---|---|---|
|boleano|Valores Bolaneos True y False| "boolean"|is_bool|
|integer|Numeros enteros del -2,15e+9 al -2,15e+9| "integer| is_int|
|float|Numeros con coma flotante. Los valores abarcados dependen del sistema operativo del servidor web |"double"| is_double|
|string|Cadenas de caracteres de cualquier longitud|"string" |is_string |
|array|Campos de datos o matrices. Son estructuras de datos en forma de tabla o de lista, que contiene datos de otros tipos|"array"|is_array|
|NULL|Representa un valor vacio. Las variables que aun no tienen ningun valor, que se han borrado con la funcion ..unset.. o se han declarado directamente como NULL, tiene este tipo de datos.|"unknow type"|is_null|  |

## Operadores de Comparacion
| Sintaxis	| Definicion		| Resultado									|
|---------------|-----------------------|-------------------------------------------------------------------------------|
| $var1==$var2| Igual que		| Verdadero si las dos variables son iguales					|
| $var1===$var2	| Identica que		| Verdadero si las dos variables son iguales y del mismo tipo			|
| $var1!=$var2	| Diferente que		| Verdadero si las dos variables son iguales					|
| $var1<>$var2	| Diferente que		| Verdadero si las dos variables no son iguales y ademas no son del mismo tipo	|
| $var1<$var2	| Menor que		| Verdadero si $var1 es menor que $var2						|
| $var1>$var2	| Mayor que		| Verdadero si $var1 es mayor que $var2						|
| $var1<=$var2	| Menor o Igual que	| Verdadero si $var1 es menor o igual que $var2					|
| $var1>=$var2	| Mayor o Igual que	| Verdadero si $var1 es mayor o igual que $var2					|

## Operdores Logicos
|	| |
|-----|----------------|
|and	| dos condiciones de cumplan|
|or| una condicion por lo menos se cumpla|
|or| una condicion por lo menos se cumpla|
|!=	| Indiferente de |
|!	| Negacion para que se vuelva valido|
## Comentarios
```php
// Comentario Corto
/*Comentario
		Largo
*/
```

## Concatenacion
```php
$nombre1="pepe";
$apellido='lopez';
echo $nombre1." ".$apellido;
```


## Formas de imprimir por pantalla 
### echo
unicamente trabaja con texto
```php
echo "Hola";
```

### print_r()
nos da mas informacion
```php
print_r("hola");
```

### print()

```php
print("Hola");
```
