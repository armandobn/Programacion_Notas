```jsx
export const Posts = () => {
  return (
    <button
      onClick={() => {
        // alert('Obteniendo datos')
        fetch("https://jsonplaceholder.typicode.com/posts")
          .then((respose) => respose.json())
          .then((data) => console.log(data));
      }}
    >
      Traer Datos
    </button>
  );
};
```