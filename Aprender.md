https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys

3-patron observador
-proxy



### Objeto

```js
const obj = {};
const obj = {
	name:'Rol',
	ape:'ki'
}

obj.<prop>
console.log(obj.name); => 'Rol'

obj.name='Roldan'; //Esta mal nunca debe hacerse, aunque se pueda porque esta mutando el objeto

const nv={...obj, ape='assw'};
```