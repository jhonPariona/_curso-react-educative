# Conditional rendering

[📖 robinwieruch](https://www.robinwieruch.de/conditional-rendering-react) |

## 🔥 Condicional con if patrón de protección

Fuera de la declaracion de return, hacemos una condición antes del return si este se cumple no retornamos el componenete principal.

```jsx
const users = [
  { id: "1", firstName: "Robin", lastName: "Wieruch" },
  { id: "2", firstName: "Dennis", lastName: "Wieruch" },
];

function App() {
  return (
    <div>
      <h1>Hello Conditional Rendering</h1>
      <List list={users} />
    </div>
  );
}

function List({ list }) {
  if (!list) {
    /*Si la lista es null o undefined no pintamos nada*/
    return null;
  }

  return (
    <ul>
      {list.map((item) => (
        <Item key={item.id} item={item} />
      ))}
    </ul>
  );
}

function Item({ item }) {
  return (
    <li>
      {item.firstName} {item.lastName}
    </li>
  );
}
```

## Usando if else

No es una buena práctica en vez de usar if else podemos usar if separados.

```jsx
function List({ list }) {
  if (!list) {
    return null;
  }

  if (!list.length) {
    return <p>Sorry, the list is empty.</p>;
  } else {
    return (
      <div>
        {list.map((item) => (
          <Item item={item} />
        ))}
      </div>
    );
  }
}

// mejor práctica es
function List({ list }) {
  if (!list) {
    return null;
  }

  if (!list.length) {
    return <p>Sorry, the list is empty.</p>;
  }

  return (
    <div>
      {list.map((item) => (
        <Item item={item} />
      ))}
    </div>
  );
}
```

## 🔥 Operador ternario

Se usa dentro de return

```jsx
function Recipe({ food, isEdit }) {
  return (
    <div>
      {food.name}
      {isEdit ? <EditRecipe food={food} /> : <ShowRecipe food={food} />}
    </div>
  );
}
```

## 🔥 operador && o evaluación de cortocircuito

Si solo queremos renderizar el true nada mas(cuando devolvemos null en el tercer operador)

```jsx
function LoadingIndicator({ isLoading }) {
  return <div> {isLoading && <p> Loading ... </p>} </div>;
}
```

## renderizado con switch

Si vamos a devolver varios renderizados, ejemplo en una notificación
podemos usar este switch dentro del return haciendo uso de una funcion de flecha

```jsx
function Notification({ text, status }) {
  return (
    <div>
      {(() => {
        switch (status) {
          case "info":
            return <Info text={text} />;
          case "warning":
            return <Warning text={text} />;
          case "error":
            return <Error text={text} />;
          default:
            return null;
        }
      })()}
    </div>
  );
}
```

## 🔥 usando enumeracion para devolver multiples renderizados

enumeracion es un objeto con claves valor, es el mas recomendado para representaciones condicional multiples

```jsx
// si solo dependemos del estado
const NOTIFICATION_STATES = {
  info: <Info />,
  warning: <Warning />,
  error: <Error />,
};

function Notification({ status }) {
  return <div>{NOTIFICATION_STATES[status]}</div>;
}

// si dependemos de prop o estado que se pase en info warning o error
const getNotification = (text) => ({
  info: <Info text={text} />,
  warning: <Warning text={text} />,
  error: <Error text={text} />,
});

function Notification({ status, text }) {
  return <div>{getNotification(text)[status]}</div>;
}
```

ejemplo de enumeracion mas complicada

```jsx
function Message({ isExtrovert, isVegetarian }) {
  const key = `${isExtrovert}-${isVegetarian}`;

  return (
    <div>
      {
        {
          "true-true": <p>I am an extroverted vegetarian.</p>,
          "true-false": <p>I am an extroverted meat eater.</p>,
          "false-true": <p>I am an introverted vegetarian.</p>,
          "false-false": <p>I am an introverted meat eater.</p>,
        }[key]
      }
    </div>
  );
}
```

## Renderizado condicional anidados

No es recomendado ya que es menos legible, en si caso se pued usar if o separar en componentes y que cada uno maneje su renderizado

```jsx
function List({ list }) {
  const isNotAvailable = !list;
  const isEmpty = !list.length;

  return (
    <div>
      {isNotAvailable ? (
        <p>Sorry, the list is not there.</p>
      ) : isEmpty ? (
        <p>Sorry, the list is empty.</p>
      ) : (
        <div>
          {list.map((item) => (
            <Item item={item} />
          ))}
        </div>
      )}
    </div>
  );
}
```

## 🔥 renderizado condicional con HOC componentes de orden superior

Para separar el renderizado condicional del la funcionalidad del componente, ejemplo el componente List unicamente se encarga de representar la lista y creamos HOC para el renderizado condicional que maneja si es q se esta cargando

```jsx
// Higher-Order Component
function withLoadingIndicator(Component) {
  return function EnhancedComponent({ isLoading, ...props }) {
    if (!isLoading) {
      return <Component {...props} />;
    }
    return (
      <div>
        <p>Loading</p>
      </div>
    );
  };
}

const ListWithLoadingIndicator = withLoadingIndicator(List);

function App({ list, isLoading }) {
  return (
    <div>
      <h1>Hello Conditional Rendering</h1>

      <ListWithLoadingIndicator isLoading={isLoading} list={list} />
    </div>
  );
}

// componente List unicaente se encarga de renderizar la lista
```
