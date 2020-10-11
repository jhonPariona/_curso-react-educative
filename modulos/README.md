# 🔥 Modulos

> compartir todo lo que se puede asignar a una variable y  importar todas las variables exportadas desde otro archivo como un solo objeto o por separado.

cada clase(Componnente) es un módulo es buena práctica que cada archivo tenga un solo módulo(Fuertemente cohesivo).

> Las clases definidas en los módulos son privadas por defecto y otros archivos que existen dentro de su proyecto no pueden acceder a ellas. Puede hacerlos públicos mediante el uso de declaraciones de importación / exportación.

## Exportaciones Nombradas

se usa `{}` y se debe importar con el nombre con el q se exportó.

```js
const firstname = 'Robin';
const lastname = 'Wieruch';

export { firstname, lastname };

//o
export const firstname = 'Robin';
export const lastname = 'Wieruch';
```

```js
//individualmente
import React from 'react';
import { firstname, lastname } from './myfile.js';

export default class App extends React.Component {
  render() {
    return (
      <p>Hello {firstname}!</p>
    );
  }
}

//como un solo objeto
import React from 'react';
import * as person from './myfile.js';

export default class App extends React.Component {
  render() {
    return (
      <p>Hello, {person.firstname}!</p>
    );
  }
}
```

## Exportaciones por defecto

No se usa `{}` y se puede importar con un nombre diferente al exportado.

Usa la palabra `default` se usa esta exportación para:

- para exportar e importar una sola funcionalidad de un módulo
- para resaltar la funcionalidad principal de la API exportada de un módulo
- tener una funcionalidad de importación alternativa

```js
// export de una clase
export default class_name {....}

//import
import class_name_diferente from module_name;
```



## Alias

para renombrar la variable que importamos

```js
import React from 'react';
import { firstname as username } from './myfile.js';

export default class App extends React.Component {
  render() {
    return (
      <p>Hello, {username}!</p>
    );
  }
}
```
