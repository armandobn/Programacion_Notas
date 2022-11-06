## Hive-JS
file:///C:/Users/misti/Videos/Hive/Proyecto8/index.html
"Expected version 128, instead got 149"
"Expected version 128, instead got 149"
message: "Expected version 128, instead got 149"
Estás viendo el error, porque usted está proporcionando la tecla equivocada. Si recibe el error " `AssertionError: Expected version 128, instead got 38`"esto significa que usted está tratando de usar una clave pública cuando usted necesita el uso de una clave privada.

En mi caso, el error, " `AssertionError: Expected version 128, instead got 149`"era porque yo estaba tratando de utilizar la contraseña de mi cuenta en lugar de mi memo clave para codificar la cadena de memo.

https://ilikekillnerds.com/2020/05/how-to-fix-hivejs-assertionerror-expected-version-128-instead-got-149-and-expected-version-128-instead-got-38/