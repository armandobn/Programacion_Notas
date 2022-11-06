**Ejemplo #1 Ejemplo de **extract()****

Un posible uso de **extract()** es importar a la tabla de símbolos las variables contenidas en un array asociativo devuelto por [wddx_deserialize()](https://www.php.net/manual/es/function.wddx-deserialize.php).

`<?php      /* Se supone que $var_array es un array devuelto desde      wddx_deserialize */      $tamaño = "grande";   $var_array = array("color" => "azul",                   "tamaño"  => "medio",                   "forma" => "esfera");   extract($var_array, EXTR_PREFIX_SAME, "wddx");      echo "$color, $tamaño, $forma, $wddx_tamaño\n";      ?>`

El resultado del ejemplo sería:

azul, grande, esfera, medio

El $tamaño no se ha sobrescrito ya que se especificó **`EXTR_PREFIX_SAME`**, lo que resulta en la creación de $wddx_tamaño. Si se hubiera especificado **`EXTR_SKIP`**, $wddx_tamaño no se habría creado. **`EXTR_OVERWRITE`** causaría que $tamaño tuviera el valor "medio", y **`EXTR_PREFIX_ALL`** resultaría en variables nuevas llamadas $wddx_color, $wddx_tamaño, y $wddx_forma.

### Notas [¶](https://www.php.net/manual/es/function.extract.php#refsect1-function.extract-notes)

**Advertencia**

No use **extract()** en datos que no son de confianza, como las entradas de usuario (esto es, [$_GET](https://www.php.net/manual/es/reserved.variables.get.php), [$_FILES](https://www.php.net/manual/es/reserved.variables.files.php), etc.). Si lo hace, asegúrese de usar uno de los valores de `flags` que no sobrescriban, como **`EXTR_SKIP`**, y sepa que debería realizar la extracción en el mismo orden que fue definido en [variables_order](https://www.php.net/manual/es/ini.core.php#ini.variables-order) dentro de [php.ini](https://www.php.net/manual/es/ini.php).