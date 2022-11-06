Manejar estilos

El espera codigo de JavaScript para estilos

```jsx
export function TaskCard() 
  
  return (
    <div style={{ background: "#202020", color: "#fff", padding: "20px" }}>
      <h1 style={{ fontWeight: "lighter" }}>Mi primer tarea</h1>
      <p>Tareal realizada</p>
    </div>
  );
}
```

```jsx
root.render(
  <>
	<TaskCard />
  </>
);
```

Otra forma de estelizar 
```jsx
export function TaskCard() 
  const cardStyles = { background: "#202020", color: "#fff", padding: "20px" };
  const titleStyle = { fontWeight: "lighter" };
  return (
    <div style={cardStyles}>
      <h1 style={titleStyle}>Mi primer tarea</h1>
      <p>Tareal realizada</p>
    </div>
  );
}
```

```jsx
root.render(
  <>
	<TaskCard />
  </>
);
```


Otra forma de estelizar utilizando un archivo css, el archivo se importara en el componente que se le dara el estilo.
**Aqui en lugar de trabajar con class se utilizara className**
``class -> className``

```css
.card{
    background-color: #202020;
    color: aliceblue;
    padding: 10px;
}
```

```jsx
import "./task.css";

export function TaskCard() {
  return (
    <div className='card'>
      <h1>Mi primer tarea</h1>
      <p>Tareal realizada</p>
    </div>
  );
}
```

```jsx
root.render(
  <>
	<TaskCard />
  </>
);
```

Trabajarlo con condicionales

```jsx
import "./task.css";

export function TaskCard(ready) {
  return (
    <div className="card">
      <h1>Mi primer tarea</h1>
      <span>{ready ? "Tarea realizada" : "Tarea Pendiente"}</span>
      {/* <span>{ready === true ? "Tarea realizada" : "Tarea Pendiente"}</span> */}
    </div>
  );
}
```

Lo manejados de esta forma porque manejamos ahora mediante el nombre de las clases para poder cambiar los estilos

```jsx
import "./task.css";
export function TaskCard({ready}) {
  return (
    <div className="card">
      <h1>Mi primer tarea</h1>
      <span
      className={ready ? 'bg-green' : 'bg-red'}
      // style={ready ? {background:"green"} : { background:"red"}}
      >{ready ? "Tarea realizada" : "Tarea Pendiente"}</span>
      {/* <span>{ready === true ? "Tarea realizada" : "Tarea Pendiente"}</span> */}
    </div>
  );
}
```

```jsx
root.render(
  <>
	<TaskCard />
  </>
);
```