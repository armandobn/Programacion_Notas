# Props
```js
export function Greeting(props) {
  console.log(props);
  return <h1>{props.title}</h1>;
}
```

```js
import React from "react";
import ReactDOM from "react-dom/client";
import { Greeting } from "./Greeting";

const root = ReactDOM.createRoot(document.getElementById("root"));

root.render(
  <>
    <Greeting title="hola" />
    <Greeting title={2+8}/>
    <Greeting title="hola a" />
  </>
);
```

Utilizamos la destructuracion para llamar al valor

```js
export function Greeting({title}) {
  console.log(title);
  return <h1>{title}</h1>;
}
```

```js
import React from "react";
import ReactDOM from "react-dom/client";
import { Greeting } from "./Greeting";

const root = ReactDOM.createRoot(document.getElementById("root"));

root.render(
  <>
    <Greeting title="hola" />
    <Greeting title={2+8}/>
    <Greeting title="hola a" />
  </>
);
```

Utilizamos la destructuracion y pasamos dos parametros

```js
export function Greeting({title, name}) {
  console.log(title, name);
  return <h1>{title}</h1>;
}
```

```js
import React from "react";
import ReactDOM from "react-dom/client";
import { Greeting } from "./Greeting";

const root = ReactDOM.createRoot(document.getElementById("root"));

root.render(
  <>
    <Greeting title="hola" name="Mia" />
    <Greeting title={2+8} name="Correcto"/>
    <Greeting title="hola a" />
  </>
);
```

Aparte de hacer la destructuracion podemos indicarle que si no tiene valor darle uno por defecto

```js
export function Greeting({title, name = "User"}) {
  console.log(title, name);
  return <h1>{title}</h1>;
}
```

```js
import React from "react";
import ReactDOM from "react-dom/client";
import { Greeting } from "./Greeting";

const root = ReactDOM.createRoot(document.getElementById("root"));

root.render(
  <>
    <Greeting title="hola" name="Mia" />
    <Greeting title={2+8} name="Correcto"/>
    <Greeting title="hola a" />
  </>
);
```

## Default Props