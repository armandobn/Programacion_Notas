Manejador de eventos
nos permite hacer algo cuando ocurre un determinado evento en una interfaz

```jsx
<input onClick={function(){
      alert('Input Seleccionado')
    }}/>
```

```jsx
 <input onChange={function(){
      console.log('escribiendo en el input')
    }}/>
```

```jsx
<input id="hola" onChange={function(e){
      console.log(e.target.value)
    }}/>
```