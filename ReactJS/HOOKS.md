


### useState

```
const [state, setState] = useState(initialState);
```

Devuelve un valor con estado y una función para actualizarlo.

Durante el renderizado inicial, el estado devuelto (`state`) es el mismo que el valor pasado como primer argumento (`initialState`).

La función `setState` se usa para actualizar el estado. Acepta un nuevo valor de estado y sitúa en la cola una nueva renderización del componente.

```
setState(newState);
```

En las renderizaciones siguientes, el primer valor devuelto por `useState` será siempre el estado más reciente después de aplicar las actualizaciones.




```jsx
function Counter() {
  const [counter, setCounter] = useState(0);
  //const [variable, funcion] = useState(asignamos valor inicial); 
  return (
    <div>
      <h1>Counter: {counter}</h1>
      <button
        onClick={() => {
          setCounter(counter + 1); //Cambiar el valor del estado
        }}
      >
        Sumar
      </button>
      <button
        onClick={() => {
          setCounter(counter - 1);
        }}
      >
        Restar
      </button>
      <button onClick={()=>{
        setCounter(0)
      }}>
        Reiniciar
      </button>
    </div>
  );
}
```

### useEffect

Siempre se va ejecutar cuando haya un cambio en el componente que lo contiene

```jsx
 useEffect(
    ()=>{
      console.log("render")
    }
  );
```

Hace que se ejecute solo una vez
```jsx
  useEffect(() => {
    console.log("render");
  }, []);
```