Peticiones Son verbos esto forma parte o propio del HTTP 

GET
Cliente pide obtener algo, es una escucha 
POST
Cliente manda informacion al servidor
PUT
Cliente envia el id para poder actualizar un dato
DELETE
Cliente envia el id para poder eliminar un dato
PATCH
Cliente solo quiere actualizar una parte de los datos

Metodos HTTP

```js
const express = require('express')
const app = express()

app.get('/products', (req,res)=>{
    res.send('lista de productos');
})

app.post('/products', (req,res)=>{
    res.send('Creando productos');
})

app.put('/products', (req,res)=>{
    res.send('Actualizando productos');
})

app.delete('/products', (req,res)=>{
    res.send('Eliminando productos');
})

app.patch('/products', (req,res)=>{
    res.send('Actualizando una parte del productos');
})

app.listen(3000)
console.log(`Server on port ${300}`)
```

HTTP RESPONSE

```js
const express = require("express");
const app = express();

app.get("/", (req, res) => {
  res.send("Hello world");
});

app.get("/miarchivo", (req, res) => {
  res.sendFile("./texto.txt", {
    root: __dirname,
  });
});

  
app.get("/user", (req, res) => {
  res.json({
    name: "Armando",
    lastname: "arm",
    age: 22,
    points: [1, 2, 3],
    address: { city: "mexican", street: "some street 134" },
  });
});

app.get("/isAlive", (req, res) => {
  res.sendStatus(204);//Enviar un codigo de estado
});

  

app.listen(3000);
console.log(`Server on port ${300}`);
```


REQUEST BODY

```JS
const express = require("express");
const app = express();

app.use(express.text()) //para que pueda procesar lo que le envian las aplicaciones clientes
app.use(express.json())
app.use(express.urlencoded({extended:false})) //No necesita interpretar(form)

app.post('/user',(req,res)=>{
    console.log(req.body)
    res.send('Nuevo usuario Creado')
})

app.listen(3000);
console.log(`Server on port ${300}`);
```