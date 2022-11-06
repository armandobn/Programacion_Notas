 // const entradaInput = document.getElementById('buscar_rfc');

 // entradaInput.value='';

 // // entradaInput.addEventListener('keydown',cambiarMayusculas);

 // entradaInput.addEventListener('keyup',cambiarMayusculas);

 // // entradaInput.addEventListener('keypress',cambiarMayusculas);

  

 function eventoTeclado(id_elemento){

 const entradaInput = document.getElementById(id_elemento);

 entradaInput.value='';

 entradaInput.addEventListener('keyup',cambiarMayusculas);

 }

  

 function cambiarMayusculas(elemento){

 let texto = elemento.target.value;

 console.log(texto);

 elemento.target.value=texto.toUpperCase();

 console.log(`TIPO DE EVENTO: ${elemento.type}` );

 }