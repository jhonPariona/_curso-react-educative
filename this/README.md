# This

El valor de this depende del contexto en el que se use. Por lo tanto, si se usa en una función, su valor dependerá de cómo se invoca esa función, es decir, el sitio de llamada.

## Enlace implícito(Implicit Binding)
`CUANDO LA FUNCIÓN ES PARTE DEL OBJETO`
Cuando usamos la notación punto this es lo que esta a la izquierda(**Regla del punto a la izquierda**)

```js
class Developer {
  constructor(firstname, lastname) {
    this.firstname = firstname;
    this.lastname = lastname;
  }

  getName() {
    return `${this.firstname} ${this.lastname}`;
  }
}

var me = new Developer('Robin', 'Wieruch');
console.log(me.getName()); // 'this' es me por eso imprime Robin
var hobbit = new Developer('Frodo', 'Baggins');
console.log(hobbit.getName()); // 'this' es 'hobbit' por eso imprime Frodo
```
}

## Enlace explicito(Explicit binding)
Para vincular las funciones independientes a objetos.

### Call
Enlazar un método independiente a un objeto `fIndependiente.call(objeto)`

```js
class Developer {
  constructor(firstname, lastname) {
    this.firstname = firstname;
    this.lastname = lastname;
  }
}

var printName = function() {
  console.log(`My name is ${this.firstname} ${this.lastname}`);
};

var me = new Developer('Robin', 'Wieruch');

// '.call()' can be used to explicitly bind a function to an object
printName.call(me);

// printName() is not bound to an object so 'this' is undefined
printName(); //this es undefined
```

Podemos pasar argumentos despues del objeto `fIndependiente.call(objeto, arg1, arg2, arg3)`

```js
// class...
var printInfo = function(lang1, lang2, lang3) {
  console.log(`My name is ${this.firstname} ${this.lastname} and I know ${lang1}, ${lang2}, and ${lang3}`);
}
// Create an array of languages
languages = ['Javascript','C++', 'Python'];

// Pass each argument individually by indexing the array
printInfo.call(me, languages[0], languages[1], languages[2]);
```

### Apply
Si queremos pasar los argumentos uno por uno
```js
// Pass all the arguments in one array to .apply()
printInfo.apply(me, languages);
```
 
### Bind
 
 Cuando se lla a una funcion con bind se establece un contexto y devuelve una nueva funcion con un contexto this vinculado.
 
```js
 class Developer {
  constructor(firstname, lastname) {
    this.firstname = firstname;
    this.lastname = lastname;
  }
}

var printName = function() {
  console.log(`My name is ${this.firstname} ${this.lastname}`);
};

var me = new Developer('Robin', 'Wieruch');

// Here we bind the me object to the printName() function and get a new function called newPrintName()
const newPrintName = printName.bind(me);

// funciona bien e imprime correctamente
newPrintName();

// this es undefined
printName();
```

## Nuevo bind
Podemos establecer el bind dentro de la funcion independiente como si fuera un constructor. no serviria para objetos solo para funciones
```js
var printInfo = function(firstname, lastname, lang1, lang2, lang3) {
  this.firstname = firstname;
  this.lastname = lastname;
  console.log(`My name is ${this.firstname} ${this.lastname} and I know ${lang1}, ${lang2}, and ${lang3}`);
}

languages = ['Javascript','C++', 'Python'];
printInfo('Robin', 'Wieruch', languages[0], languages[1], languages[2]);
```

## CONTEXTO GLOBAL

Cuando thisse usa fuera de cualquier contexto, como una clase, función u objeto, se refiere al objeto global . El objeto global en el navegador suele ser el window

## Las funciones de flecha y this

call y aply no funcionan en funciones de flecha ya que las funciones de flecha son inalterables
