# Capítulo 2: Contratos
El código Solidity está encapsulado en **contratos**. Un `contrato` es el bloque de construcción más básico de las aplicaciones de Ethereum — todas las variables y las funciones pertenecen a un contrato, y este será el punto de partida de todos tus proyectos.

Un contrato vacio llamado `HolaMundo` se parecería a esto:

```
contract HolaMundo {

}
```

## Versión Pragma

Todo el código fuente en Solidity debería empezar con una declaración "version pragma" de la versión del compilador que debe de usarse para ese código. Esto previene problemas con versiones futuras del compilador que podrían no ser compatibles y fallar con tu código.

Esta declaración se asemeja a esto: `pragma solidity ^0.4.25;` (para usar la última versión del compilador de Solidity actual, la 0.4.25).

Poniendo todo junto, este es el esqueleto de como se empieza un contrato — lo primero que escribirás cada vez que empieces un nuevo proyecto:

```
pragma solidity ^0.4.25;

contract HolaMundo {

}
```

# Capítulo 3: Variables de Estado y Números Enteros
Las **_Variables de estado_** se guardan permanentemente en el almacenamiento del contrato. Esto significa que se escriben en la cadena de bloques de Ethereum. Piensa en ellos como en escribir en una base de datos.

##### Ejemplo:

```solidity
contract Example {
  // Esto se guardará permanentemente en la cadena de bloques
  uint myUnsignedInteger = 100;
}
```

En este contrato de ejemplo, hemos creado un `uint` llamado `myUnsignedInteger` y le hemos dado el valor 100.

## Enteros sin Signo: `uint`

El tipo de dato `uint` es un entero sin signo, esto es **su valor siempre debe ser no-negativo**. Hay también un tipo de dato `int` para números enteros con signo.

> Nota: En Solidity, `uint` es realmente un alias para `uint256`, un número entero de 256-bits. Puedes declarar uints con menos bits — `uint8`, `uint16`, `uint32`, etc.. Pero por lo general usaremos `uint` excepto en casos específicos, de los que hablaremos en otras lecciones más adelante.


# Capítulo 4: Operaciones Matemáticas
Las matemáticas de Solidity son bastante básicas. Las siguientes operaciones son las mismas en prácticamente todos los lenguajes de programación:

-   Suma: `x + y`
-   Resta: `x - y`,
-   Multiplicación: `x * y`
-   División: `x / y`
-   Módulo: `x % y` _(por ejemplo, `13 % 5` es `3`, ya que al dividir 13 entre 5, 3 es el resto)_

Solidity también tiene un **_operador exponencial_** (por ejemplo "x elevado a y", x^y):
```solidity
uint x = 5 ** 2; // es igual a 5^2 = 25
```

# Capítulo 5: Estructuras
Algunas veces necesitas tipos de datos más complejos. Para esto Solidity proporciona **_structs_** (estructuras de datos):

```
struct Person {
  uint age;
  string name;
}

```

Las estructuras te permiten crear tipos de datos más complejos que tienen varias propiedades.

> Nota: acabamos de introductir un nuevo tipo de dato `string`, que se usan para cadenas de texto UTF-8 de longitud arbitraria. Ejemplo: `string greeting = "¡Hola Mundo!"`

# Capítulo 6: Arrays

Cuando quieres tener una colección de algo, puedes usar un **_array_**. Hay dos tipos de arrays en Solidity: arrays **_fijos_** y arrays **_dinámicos_**:

```solidity
// Un Array con una longitud fija de 2 elementos:
uint[2] fixedArray;
// otro Array fijo, con longitud de 5 elementos:
string[5] stringArray;
// un Array dinámico, sin longitud fija que puede seguir creciendo:
uint[] dynamicArray;
```

También puedes crear arrays de **_estructuras_**. Si usásemos la estructura `Person` del capítulo anterior:

```solidity
Person[] people; // Array dinámico, podemos seguir añadiéndole elementos
```

¿Recuerdas que las variables de estado quedan guardadas permanentemente en la blockchain? Así que crear un array de estructuras puede ser muy útil para guardar datos estructurados en tu contrato, como una base de datos.

## Arrays Públicos

Puedes declarar un array como `público`, y Solidity creará automaticamente una función **_getter_** para acceder a él. La sintaxis es así:

```solidity
Person[] public people;
```

Otros contratos entonces podrán leer (pero no escribir) de este array. Es un patrón de uso muy útil para guardar datos públicos en tu contrato.

# Capítulo 7: Declaración de Funciones
Una declaración de una función en Solidity se asemeja a esto:

```solidity
function eatHamburgers(string _name, uint _amount) {

}
```

Esta es una función llamada `eatHamburgers` que toma dos parámetros: una cadena de texto (`string`) y un número entero sin signo `uint`. Por ahora dejamos el cuerpo de la función vacio.

> Nota: la convención (no obligatoria) es llamar los parámetros de las funciones con nombres que empiezan con un subrayado (`_`) para de esta forma diferenciarlos de variables globales. Utilizaremos esta convención en este tutorial.

Y llamaríamos a esta función de esta forma:

```solidity
eatHamburgers("vitalik", 100);
```

# Capítulo 8: Trabajando con estructuras y arrays

### Creando nuevas Estructuras (Structs)

¿Recuerdas las estructura `Person` en el ejemplo anterior?

```solidity
struct Person {
  uint age;
  string name;
}

Person[] public people;
```

Ahora aprenderemos como crear un nuevo `Person` y añadirlo a nuestro array `people`.

```solidity
// crear un nuevo `Person`
Person satoshi = Person(172, "Satoshi");

// añadir esta persona a nuestro array
people.push(satoshi);
```

También podemos combinar estas dos cosas para hacerlas en una sola línea y mantener el código limpio:

```solidity
people.push(Person(16, "Vitalik"));
```

Date cuenta que `array.push()` añade algo al **final** del array, así que los elementos siguen el orden de añadido. Observa este ejemplo:

```solidity
uint[] numbers;
numbers.push(5);
numbers.push(10);
numbers.push(15);
// el array `numbers` es ahora [5, 10, 15]
```
# Capítulo 9: Funciones Públicas y Privadas

En Solidity, las funciones son públicas (`public`) por defecto. Esto significa que cualquiera (o cualquier otro contrato) puede llamarla y ejecutar su código.

Esto no es algo que queramos que pase siempre, y de hecho puede hacer vulnerables tus contratos. Es por lo tanto una buena práctica marcar tus funciones como privadas (`private`), y solamente hacer públicas aquellas que queramos exponer al mundo exterior.

Vamos a ver como se declara una función privada:

```
uint[] numbers;

function _addToArray(uint _number) private {
  numbers.push(_number);
}
```

Esto significa que solo otras funciones dentro de tu contrato podrán llamar a esta función y añadir al array `numbers`.

Como puedes ver, usamos la palabra clave `private` después del nombre de la función. Y de las misma forma que con los parámetros de funciones, la convención es nombrar las funciones privadas empezando con una barra baja (`_`).

# Capítulo 10: Más sobre Funciones

En este capítulo aprenderemos sobre los **_valores de retorno_** de una función, y sobre modificadores de funciones.

## Valores de Retorno

Para devolver un valor desde una función, la declaración es la siguiente:

```solidity
string greeting = "Qué tal viejo!";

function sayHello() public returns (string) {
  return greeting;
}
```

En Solidity, la declaración de la función contiene al final tipo de dato del valor de retorno (en nuestro caso `string`).

## Modificadores de Función

La función de arriba no cambia el estado en Solidity, esto es que no cambia ningún valor o escribe nada.

En este caso podríamos declararla como función **_view_**, que significa que solo puede ver los datos pero no modificarlos:

```
function sayHello() public view returns (string) {
```

Solidity también contiene funciones **_pure_**, que significa que ni siquiera accedes a los datos de la aplicación. Por ejemplo:

```
function _multiply(uint a, uint b) private pure returns (uint) {
  return a * b;
}
```

Esta función no lee desde el estado de la aplicación - el valor devuelto depende por completo de los parámetros que le pasemos. En este caso deberíamos declarar la función como **_pure_**.

> Nota: No siempre es fácil recordar marcar una función como pure o view, por suerte el compilador de Solidity es muy bueno avisándonos de cuándo debemos usar estos modificadores de función.

# Capítulo 11: Keccak256 y Encasillado de tipo

Queremos que nuestra función `_generateRandomDna` devuelva un valor semi-aleatorio `uint`. ¿Cómo se puede conseguir esto?

Ethereum incluye una función hash llamada `keccak256`, que es una versión de SHA3. Una función hash lo que hace es mapear una cadena de caracteres a un número aleatorio hexadecimal de 256-bits. Un pequeño cambio en la cadena de texto producirá un hash completamente distinto.

Es muy útil para muchas cosas, pero por ahora vamos a usarlo solamente para generar un número cuasi-aleatorio.

Ejemplo:

```
//6e91ec6b618bb462a4a6ee5aa2cb0e9cf30f7a052bb467b0ba58b8748c00d2e5
keccak256("aaaab");
//b1f078126895a1424524de5321b339ab00408010b7cf0e6ed451514981e58aa9
keccak256("aaaac");
```

Como puedes ver, el valor devuelto para cada caso es completamente distinto, a pesar de que sólo hemos cambiado un carácter del argumento.

> Nota: Generar números aleatorios de forma **segura** en la cadena de bloques es algo muy difícil. El método que usamos aquí no es seguro, pero la seguridad no es nuestra prioridad para el ADN del Zombi, es suficiente para este propósito.

## Casteo de variables

A veces es necesario convertir entre tipos de datos. Por ejemplo en el siguiente caso:

```
uint8 a = 5;
uint b = 6;
// dará un error porque a * b devuelve un `uint` y no un `uint8`:
uint8 c = a * b;
// debemos de forzar la variable b para que sea convertida a `uint8`
uint8 c = a * uint8(b);
```

En el código de arriba. `a * b` devuelve un `uint`, pero estábamos intentando guardarlo como `uint8`, lo que podría causar problemas. Casteándolo a `uint8` funcionará y el compilador no nos dará error.

# Capítulo 11: Keccak256 y Encasillado de tipo

Queremos que nuestra función `_generateRandomDna` devuelva un valor semi-aleatorio `uint`. ¿Cómo se puede conseguir esto?

Ethereum incluye una función hash llamada `keccak256`, que es una versión de SHA3. Una función hash lo que hace es mapear una cadena de caracteres a un número aleatorio hexadecimal de 256-bits. Un pequeño cambio en la cadena de texto producirá un hash completamente distinto.

Es muy útil para muchas cosas, pero por ahora vamos a usarlo solamente para generar un número cuasi-aleatorio.

Ejemplo:

```
//6e91ec6b618bb462a4a6ee5aa2cb0e9cf30f7a052bb467b0ba58b8748c00d2e5
keccak256("aaaab");
//b1f078126895a1424524de5321b339ab00408010b7cf0e6ed451514981e58aa9
keccak256("aaaac");
```

Como puedes ver, el valor devuelto para cada caso es completamente distinto, a pesar de que sólo hemos cambiado un carácter del argumento.

> Nota: Generar números aleatorios de forma **segura** en la cadena de bloques es algo muy difícil. El método que usamos aquí no es seguro, pero la seguridad no es nuestra prioridad para el ADN del Zombi, es suficiente para este propósito.

## Casteo de variables

A veces es necesario convertir entre tipos de datos. Por ejemplo en el siguiente caso:

```
uint8 a = 5;
uint b = 6;
// dará un error porque a * b devuelve un `uint` y no un `uint8`:
uint8 c = a * b;
// debemos de forzar la variable b para que sea convertida a `uint8`
uint8 c = a * uint8(b);
```

En el código de arriba. `a * b` devuelve un `uint`, pero estábamos intentando guardarlo como `uint8`, lo que podría causar problemas. Casteándolo a `uint8` funcionará y el compilador no nos dará error.

# Capítulo 13: Eventos

¡Nuestro contrato está casi terminado! Añadamos ahora un **_evento_**.

Los **_eventos_** son la forma en la que nuestro contrato comunica que algo sucedió en la cadena de bloques a la interfaz de usuario, el cual puede estar 'escuchando' ciertos eventos y hacer algo cuando sucedan.

Ejemplo:

```solidity
// declara el evento
event IntegersAdded(uint x, uint y, uint result);

function add(uint _x, uint _y) public {
  uint result = _x + _y;
  // lanza el evento para hacer saber a tu aplicación que la función ha sido llamada:
  emit IntegersAdded(_x, _y, result);
  return result;
}
```

La aplicación con la interfaz de usuario podría entonces estar escuchando el evento. Una implementación en JavaScript sería así:

```solidity
YourContract.IntegersAdded(function(error, result) {
  // hacer algo con `result`
}
```


# Capítulo 2: Mapeos y Direcciones

Vamos a hacer nuestro juego multijugador dandolés a los zombis un dueño en la base de datos.

Para esto, vamos a necesitar dos nuevos tipos de datos: `mapping` y `address`.

## Direcciones

La blockchain de Ethereum está creada por **_cuentas_**, que podrían ser como cuentas bancarias. Una cuenta tiene un balance de **_Ether_** (la divisa utilizada en la blockchain de Ethereum), y puedes recibir pagos en Ether de otras cuentas, de la misma manera que tu cuenta bancaria puede hacer transferencias a otras cuentas bancarias.

Cada cuenta tiene una dirección (`address`), que sería como el número de la cuenta bancaria. Es un identificador único que apuntado a una cuenta, y se asemejaría a algo así:

`0x0cE446255506E92DF41614C46F1d6df9Cc969183`

(Esta dirección pertenece al equipo de CryptoZombies. Si estás disfrutando CryptoZombies, ¡puedes enviarnos algunos Ether! 😉 )

Vamos a entrar en el meollo de las direcciones en otra lección, por ahora solo necesitas entender que **una direccion está asociada a un usuario específico** (o un contrato inteligente).

Así que podemos utilizarlo como identificador único para nuestros zombis. Cuando un usuario crea un nuevo zombi interactuando con nuestra app, adjudicaremos la propiedad de esos zombis a la dirección de Ethereum que ha llamado a la función.

## Mapeando

En la Lección 1 vimos los **_structs_** y los **_arrays_**. Los **_mapeos_** son otra forma de organizar los datos en Solidity.

Definir un `mapping` se asemejaría a esto:

```
// Para una aplicación financiera, guardamos un uint con el balance de su cuenta:
mapping (address => uint) public accountBalance;
// O podría usarse para guardar / ver los usuarios basados en un userId
mapping (uint => string) userIdToName;
```

Un mapeo es esencialmente una asociación valor-clave para guardar y ver datos. En el primer ejemplo, la clave es un `address` (dirección) y el valor correspondería a un `uint`, y en el segundo ejemplo la clave es un `uint` y el valor un `string`.

# Capítulo 3: Msg.sender

Ahora que tenemos nuestros mapeos para seguir el rastro del propietario de un zombi, queremos actualizar el metodo `_createZombie` para que los utilice.

Para poder hacer esto, necesitamos algo llamado `msg.sender`.

## msg.sender

En Solidity, hay una serie de variables globales que están disponibles para todas las funciones. Una de estas es `msg.sender`, que hace referencia a la `dirección` de la persona (o el contrato inteligente) que ha llamado a esa función.

> Nota: En Solidity, la ejecución de una función necesita empezar con una llamada exterior. Un contrato se sentará en la blockchain sin hacer nada esperando a que alguien llame a una de sus funciones. Así que siempre habrá un `msg.sender`.

Aquí tenemos un ejemplo de como usar `msg.sender` y actualizar un `mapping`:

```
mapping (address => uint) favoriteNumber;

function setMyNumber(uint _myNumber) public {
  // Actualiza tu mapeo `favoriteNumber` para guardar `_myNumber` dentro de `msg.sender`
  favoriteNumber[msg.sender] = _myNumber;
  // ^ La sintaxis para guardar datos en un mapeo es como en los arrays
}

function whatIsMyNumber() public view returns (uint) {
  // Conseguimos el valor guardado en la dirección del emisor
  // Será `0` si el emisor no ha llamado a `setMyNumber` todavía
  return favoriteNumber[msg.sender];
}
```

En este trivial ejemplo, cualquiera puede llamar a `setMyNumber` y guardar un `uint` en nuestro contrato, que estará atado a su dirección. Entonces, cuando llamen a `whatIsMyNumber`, debería devolverles el `uint` que han guardado.

Usando `msg.sender` te da la seguridad de la blockchain de Ethereum — la única forma de que otra persona edite la información de esta sería robandole la clave privada asociada a la dirección Ethereum.

# Capítulo 4: Require

En la lección 1, hicimos que los usuarios puediesen crear nuevos zombis llamando a `createRandomZombie` e introduciendo un nombre. Sin embargo, si un usuario continuase llamando a esta función crearía un ejército de zombis ilimitado, el juego no sería muy divertido.

Vamos a hacer que un jugador solo pueda llamar a esta función una vez. De esta manera los nuevo jugadores podrán llamar a esta función cuando empiezen el juego para crear el primer zombi de su ejército.

¿Cómo podemos hacer para que esta función solo pueda ser llamada una vez por jugador?

Para eso usamos `require`. `require` hace que la función lanze un error y pare de ejecutarse si la condición no es verdadera:

```
function sayHiToVitalik(string _name) public returns (string) {
  // Compara si _name es igual a "Vitalik". Lanza un error si no lo son.
  // (Nota: Solidity no tiene su propio comparador de strings, por lo que
  // compararemos sus hashes keccak256 para ver si sus strings son iguales)
  require(keccak256(_name) == keccak256("Vitalik"));
  // Si es verdad, continuamos con la función:
  return "Hi!";
}
```

Si llamas a la función con `sayHiToVitalik("Vitalik")`, esta devolverá "Hi!". Si la llamas con cualquier otra entrada, lanzará un error y no se ejecutará.

De este modo `require` es muy útil a la hora de verificar que ciertas condiciones sean verdaderas antes de ejecutar una función.

# Capítulo 5: Herencia

Nuestro código está haciendose un poco largo. Mejor que hacer un contrato extremandamente largo, a veces tiene sentido separar la lógica de nuestro código en multiples contratos para organizar el código.

Una característica de Solidity que hace más manejable esto es la **_herencia_** de los contratos:

```
contract Doge {
  function catchphrase() public returns (string) {
    return "So Wow CryptoDoge";
  }
}

contract BabyDoge is Doge {
  function anotherCatchphrase() public returns (string) {
    return "Such Moon BabyDoge";
  }
}
```

`BabyDoge` **_hereda_** de `Doge`. Eso significa que si compilas y ejecutas `BabyDoge`, este tendrá acceso tanto a `catchphrase()` como a `anotherCatchphrase()` (y a cualquier otra función publica que definamos en `Doge`).

Esto puede usarse como una herencia lógica (como una subclase, un `Gato` es un `Animal`). Pero también puede usarse simplemente para organizar tu código agrupando lógica similar en diferentes clases.
# Capítulo 6: Importar

¡Guau! Notarás que hemos limpiado el código de la derecha, ahora tienes unas pestañas en la parte superior de tu editor. Adelante, clica entre las pestañas para probarlo.

Nuestro código estaba quedando algo largo, por eso lo hemos dividido en multiples archivos haciendolo así más manejable. Así es como normalmente deberás guardar tu código base en tus proyectos de Solidity.

Cuando tienes multiples archivos y quieres importar uno dentro de otro, Solidity usa la palabra clave `import`:

```
import "./someothercontract.sol";

contract newContract is SomeOtherContract {

}
```

Entonces si tenemos un fichero llamado `someothercontract.sol` en el mismo directorio que este contrato (eso es lo que significa `./`), será importado por el compilador.

# Capítulo 7: Storage vs Memory

En Solidity, hay dos sitios donde puedes guardar variables - en `storage` y en `memory`.

**_Storage_** se refiere a las variables guardadas permanentemente en la blockchain. Las variables de tipo **_memory_** son temporales, y son borradas en lo que una función externa llama a tu contrato. Piensa que es como el disco duro vs la RAM de tu ordenador.

La mayoría del tiempo no necesitas usar estas palabras clave ya que Solidity las controla por defecto. Las variables de estado (variables declaradas fuera de las funciones) son por defecto del tipo `storage` y son guardadas permanentemente en la blockchain, mientras que las variables declaradas dentro de las funciones son por defecto del tipo `memory` y desaparecerán una vez la llamada a la función haya terminado.

Aun así, hay momentos en los que necesitas usar estas palabras clave, concretamente cuando estes trabajando con **_structs_** y **_arrays_** dentro de las funciones:

```
contract SandwichFactory {
  struct Sandwich {
    string name;
    string status;
  }

  Sandwich[] sandwiches;

  function eatSandwich(uint _index) public {
    // Sandwich mySandwich = sandwiches[_index];

    // ^ Parece algo sencillo, pero solidity te dará un warning
    // diciendo que deberías declararlo `storage` o `memory`.

    // De modo que deberias declararlo como `storage`, así:
    Sandwich storage mySandwich = sandwiches[_index];
    // ...donde `mySandwich` es un apuntador a `sandwiches[_index]`
    // de tipo storage, y...
    mySandwich.status = "Eaten!";
    // ...esto cambiará permanentemente `sandwiches[_index]` en la blockchain.

    // Si únicamente quieres una copia, puedes usar `memory`:
    Sandwich memory anotherSandwich = sandwiches[_index + 1];
    // ...donde `anotherSandwich` seria una simple copia de 
    // los datos en memoria, y...
    anotherSandwich.status = "Eaten!";
    // ...modificará la variable temporal y no tendrá efecto
    // en `sandwiches[_index + 1]`. Pero puedes hacer lo siguiente:
    sandwiches[_index + 1] = anotherSandwich;
    // ...si quieres que la copia con los cambios se guarde en la blockchain.
  }
}
```

No te preocupes si no has entendido del todo como usar esto - durante este tutorial te diremos cuándo usar `storage` y cuándo usar `memory`, y el compilador de Solidity también te dará advertencias para hacerte saber cuando usar cada una de estas palabras clave.

¡Por ahora, es suficiente con que entiendas en que caso necesitarás usar explícitamente `storage` o `memory`!