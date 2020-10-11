# Herencia

Sigue el principio `es un` hijo es un Padre

 La herencia permite que nuevas clases adopten las propiedades y métodos de las clases existentes. Una clase que hereda otra clase se llama superclase o clase base . Una clase que hereda de una superclase se denomina subclase o clase derivada.
 En javaScript usamos la palabra `extends`
 
 ```js
 class Developer {
  constructor(firstname, lastname) {
    this.firstname = firstname;
    this.lastname = lastname;
  }
  getName() {
    return this.firstname + ' ' + this.lastname;
  }
}

class ReactDeveloper extends Developer {
  getJob() {
    return 'React Developer';
  }
}

var me = new ReactDeveloper('Robin', 'Wieruch'); //hereda el constructor

console.log(me.getName()); //hereda sus metodos
console.log(me.getJob()); //puede usar métodos propios
```

Tiene dos problemas 1. Problema gorila/banana: tengo un superclase que tiene el atributo de nombre y 2 clases hijas 1 que tiene un metodo que dispara laser y otro que dispara pistola, ahora si quiero crear una nueva clase que dispare laser y pistola, lo que podria hacer es escribir los metodos laser y pistola en el padre lo cual llevaria que el q solo usa pistola tenga innecesariamente acceso al otro mṕetodo que no usará.

Problema2: Pobrema de duplicación por necesidad: otra forma de una solucion seria copiar los metodos laser y pistola en el nuevo hijo y dejando las clases hijas con sus metodos locales y nada en el padre pero estariamos duplicando lineas que son una mala práctica.

# 🔥 Composición

Sigue el principio has A(tiene un) la claseHija y metodoHija tiene un metodoPadre

Clases que contienen instancias de otras clases como atributos para implementar sola la funcionalidad deseada.
