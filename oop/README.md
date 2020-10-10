# OOP

## Clases

Son azucar sintáctico de los prototipos(chain prototypes o cadena de prototipos).

Las clases son miniprogramas con contexto propio: métodos(funciones) y propiedades(variables), para describir una instamcia y poder crear diferentes objetos a partir de ella. Estos objetos se tratan como variables.

```js
class Car{
    constructor(color, model, engineCap, registrationNum){
        this.color = color;
        this.model = model;
        this.engineCap = engineCap;
        this.registrationNum = registrationNum;
    }

    getColor(){
        return this.color;
    }
    getModel(){
        return this.model;
    }
    setColor(color){
        this.color = color;
    }
    setModel(model){
        this.model = model;
    }
}
```
