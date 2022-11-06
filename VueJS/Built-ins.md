# Built-ins
- Directives
- Components
- Special Elements
- Special Sttributes
##  Built-in Directives
### v-bind
Enlace dinámicamente uno o más atributos, o una propiedad de componente a una expresión.
-   **Taquigrafía:** `:`o `.`(cuando usas `.prop`modificador)
    
-   **Espera:** `any (with argument) | Object (without argument)`
    
-   **Argumento:** `attrOrProp (optional)`
    
-   **Modificadores:**
	-   `.camel`- transformar el nombre del atributo kebab-case en camelCase.
	-   `.prop`- forzar que un enlace se establezca como una propiedad DOM. 3.2+
	-   `.attr`- forzar que un enlace se establezca como un atributo DOM. 3.2+

**Uso**

Cuando se utiliza para unir el `class`o `style`atributo, `v-bind`admite tipos de valores adicionales como Array u Objects.
Al establecer un enlace en un elemento, Vue comprueba de forma predeterminada si el elemento tiene la clave definida como una propiedad mediante un `in`verificación del operador. Si la propiedad está definida, Vue establecerá el valor como una propiedad DOM en lugar de un atributo. Esto debería funcionar en la mayoría de los casos, pero puede anular este comportamiento utilizando explícitamente `.prop`o `.attr`modificadores Esto a veces es necesario, especialmente cuando se [trabaja con elementos personalizados](https://vuejs.org/guide/extras/web-components.html#passing-dom-properties) .

Cuando se usa para el enlace de accesorios de componentes, el accesorio debe declararse correctamente en el componente secundario.

Cuando se usa sin un argumento, se puede usar para vincular un objeto que contiene pares de nombre y valor de atributo. Nota en este modo `class`y `style`no es compatible con Array u Objects.