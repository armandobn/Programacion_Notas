# POO
```js
class Animal{//declarar una clase 
  constructor(especie, edad, color){//constructor
    this.especie=especie;
    this.edad=edad;
    this.color=color;
    this.info=`Soy ${this.especie},tengo ${this.edad} años y soy de color ${this.color}`;
  }

  //Metodos
  verInfo(){
    document.write(this.info +"<br>")
  }

}

class Perro extends Animal{//extends extender o herede de una clase
  constructor(especie,edad,color,raza){
    super(especie,edad,color);//super para heredar las propiedad de su constructor
    this.raza=raza;
  }

  ladrar(){
    alert("!Waw¡");
  }

}

let perro = new Perro("perro",5,"marron","doberman"); //instanciar la clase
let gato = new Animal("gato",5,"negro");
let pajaro = new Animal("pajaro", 5, "verde");
//console.log(perro);
// document.write(perro.info + "<br>"); //llamar la informacion
// document.write(gato.info + "<br>");
// document.write(pajaro.info + "<br>");

perro.ladrar();//LLamar Metodos
gato.verInfo();
pajaro.verInfo();
```