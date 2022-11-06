Exportacion por Funcion
```js
export function Greeting() {
	return <h1>Componente de React</h1>
}
export function UserCard(){
    return <h1>User card</h1>;
}
```

```js
import { Greeting, UserCard } from "./Greeting";
```

Exportacion por default
```js
function Product(){
    return <div>
        <h1>Producto</h1>
    </div>
}

export function Navbar(){
    return <nav>
        navigation
    </nav>
}
export default Product;
```

```js
import Product, {Navbar} from './Product';
```