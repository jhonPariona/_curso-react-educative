<h1 align=center>
  <img src="assets/imgs/portada.png" alt="portada">
</h1>

[⚛️ JavaScript Fundamentals Before Learning React](https://www.educative.io/courses/javascript-fundamentals-before-learning-react)

> React ofrece cierta administración de estado interna, pero aparte de esto, es solo una biblioteca de componentes que procesa HTML para su navegador.

```jsx
import React from 'react';

export default class App extends React.Component {
  //métodos, state, constructor
  render() {
    //Javascript
    return (
      //jsx, {}
    );
  }
}
```

## Alcance Variables js

- **var** Scope dentro de la funcion que se declara.
- **let y const** dentro de `{}` bloque.

> Ya no usar var, por defecto usar const

## Renderizado condicional

[Renderizado condicional](./conditional-rendering/README.md)

## Desestructuracion

[Desestructuracion](./destructuring/README.md)

## Spread operator

[operador de propagacion](./spread-operator/README.md)

## Funciones

> Una función es un fragmento de código que se define solo una vez, pero que se puede llamar innumerables veces.

> En JavaScript, las funciones son en realidad objetos. Al igual que cualquier objeto típico, también tienen atributos y métodos. Lo único que los diferencia de los objetos es que pueden llamarse

[Funciones en javascript](https://github.com/jhonPariona/_curso-react-educative/tree/main/funciones#funciones)

## OPP clases
[Clases](https://github.com/jhonPariona/_curso-react-educative/tree/main/oop#oop)

## This
[This](https://github.com/jhonPariona/_curso-react-educative/tree/main/this#this)

## Composición y herencia

[Composicion y herencia](https://github.com/jhonPariona/_curso-react-educative/tree/main/herencia-composicion#herencia)


## Modulos
[Modulos](https://github.com/jhonPariona/_curso-react-educative/tree/main/modulos#-modulos)

## COmponentes

>  bloques de construcción que conforman el aspecto de un sitio web y todos los componentes de React deben comenzar con una letra mayúscula

## Props

> argumentos que puedes pasar a una función

## State

> El estado determina el aspecto del componente y puede actualizarlo sobre la marcha, el estado es solo un objeto en un componente de React 

> setState()no actualiza inmediatamente su componente

## Ciclo de vida

> Cada componente de React pasa por un ciclo de vida y los métodos de ciclo de vida son funciones proporcionadas por React a través de las cuales podemos controlar lo que sucede cuando cada pequeña sección de su interfaz de usuario se procesa, actualiza, considera volver a renderizar y luego desaparece por completo.
