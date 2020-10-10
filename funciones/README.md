# Funciones

# Funciones anónimas(Anonymous) y funciones nombradas(Named)

Funciones anónimas(omite el nombre de la funcion despues de la palabra clave function) se declaran en tiempo de ejecución, primero devemos de declararlas para usarlas.
```js
var myFunction = function()
{
  console.log("Hello! I'm an Anonymous function");
}

myFunction();
```

Named function(usan un nombre pdespues de la palabra clave function) pueden ser llamadas incluso antes de ser declaradas. Es más recomendable usar estas ya que ayuda a la identificar más facil en que funcion ocurrio el error.
```js
function myFunction()
{
  console.log("Hello! I'm a named function!");
}

myFunction();
```

> Cada tipo de funciones controla como este interactua con los componentes externos, su scope, el contexto,... A continuación se muestras los tipos en javascript

 
## Arrow function
Sintax sugar, el valor de this apuntara a el mismo, si solo se retorna una cosa se puede omitir `{}` y si solo se pasa un parámetro tambien puede omitir los `()`

```js
// JavaScript ES6 arrow function with body
const getGreetingArrow1 = () => {
  return 'Welcome to JavaScript';
}

// JavaScript ES6 arrow function without body and implicit return
const getGreetingArrow2 = () => 'Welcome to JavaScript';
```

## Function Declaration
Este método usa hosting es decir que se puede usar antes de declararlo.
```js
  fName();
  
  function fName(Parametros){
    ...
  }
```

## Function expression
Tipo más común, se usa cuando quieres usarlo como un retorno y almacenarlo en una variable
Se debe usar despues de la declaración.

```js
//Anonymous
var varName = function(){}

//Named
var varName = function fName(){}

```

## Generator function
Retorna un Generator-Iterator mediante el key yield

```js
function* fName(){}
```

## Generator Function Expression

 Es el mismo que el anterior solo que podemios omitir el nombre de la funcion
 ```js
 function* (){}
 ```
 


## Function constructor

Este tipo no es recomendado ya que podria suponer problemas de seguridad, es usado para generar una nueva funcion que recibe los argumentos una nueva funcion

```js
var varName = new Function(parametros, 'FunctionBodyStaring');
```
