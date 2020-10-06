# Destructuring

Para recuperar cada valor de objetos y listas

```jsx
const student = {
  ID: "21",
  name: "Jhon",
  GPA: "3.0",
};

const { ID, name, GPA } = student;
```

podemos cambiar el nombre de cada propiedad

```jsx
const student = {
  ID: "21",
  name: "Jhon",
  GPA: "3.0",
};

const { name: n } = student;
console.log(n);
```

## rest Destructuring

cuando obtenemos una propiedad y lo demás lo obtenemos en una sola variable y este normalemnte se pasa a otro componente

```jsx
// rest destructuring
const { users, ...rest } = this.state;
```
