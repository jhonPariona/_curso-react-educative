# Map
Retorna Todo.

crea una un nuevo array con cada elemento del array. este método recibe una funcion que se le pasa como argumento una variable que toma cada elemento del array y podemos retornar lo q queramos de cada elemento.
```jsx
//...
export default class App extends React.Component {
  render() {
    var users = [
      { name: 'Robin' },
      { name: 'Markus' },
    ];

    return (
      <ul>
        {users.map(user => <li>{user.name}</li>)}
      </ul>
    );
  }
}
```

## Filter
Retorna unicamente lo que cumple la condicion.

Se usa para devolver una nueva matríz de acuerdo a una condición. recibe un método en el que recibe cada elemento y retorna los elemenento que cumplan la condicion.

```jsx
export default class App extends React.Component {
  render() {
    var users = [
      { name: 'Robin', isDeveloper: true },
      { name: 'Markus', isDeveloper: false },
      { name: 'John', isDeveloper: true },
    ];

    return (
      <ul>
        {users
          .filter(user => user.isDeveloper)
          .map(user => <li>{user.name}</li>)
        }
      </ul>
    );
  }
}
```
