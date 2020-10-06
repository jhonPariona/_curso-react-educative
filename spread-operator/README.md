# Spread operator

Sirve para copiar el contenido de un array u objeto

```jsx
a = [1, 2, 3];
b = [4, 5, 6];
c = [...a, ...b]; //spread operator
console.log("c: " + c);
```

```jsx
const person = { name: "Jhon" };
const student = { ID: "21", GPA: "3.0" };

const new_object = { ...person, ...student, semester: "3" };
console.log(new_object);
```
