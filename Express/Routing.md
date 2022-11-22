```js
//Codigo de Node
// const http = require('http')
// const fs= require('fs')
// const server=http.createServer((req,res)=>{
//     const read=fs.createReadStream('./static/index.html')
//     read.pipe(res)
// }) 
// server.listen(3000);
// console.log(`Server on port ${3000}`)

//Codigo Express
const express = require('express')
const app = express()

//tipo de peticion get
app.get('/', (req,res)=>{
    res.send('Hello Word'); //esto lo interpreta que le mandamos solo un texto
    //res.end('Hello Word'); //Lo interpreto como si fuera un texto (node)(nos da mucha informacion)
    // res.sendFile('./static/index.html',{//ruta al archivo a llamar
    //     root: __dirname // le indicamos que tome nuestra ruta de nuestro directorio
    // })
})
//se le llama routing en express, podemos crear diferentes tipos de rutas,cada funcion es independiente
app.get('/about', (req,res)=>{
    res.send('About');
})
app.get('/yo', (req,res)=>{
    res.send('yo');
})

//si no encuentra la ruta, esto nos respondra
app.use((resq,res)=>{
    //status mandamos que numero nos reponda, ejemplo el error 404
    res.status(404).send('No se encontro tu pagina')    
})

app.listen(3000) //porque cual puesto escuchara
console.log(`Server on port ${300}`)
```