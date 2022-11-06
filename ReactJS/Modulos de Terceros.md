Utilizamos la siguiente pagina para poder llamar iconos
https://react-icons.github.io/react-icons/

```jsx
import { VscGlobe } from "react-icons/vsc";
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
        <VscGlobe/>
      Traer Datos
    </button>
  );
};
```