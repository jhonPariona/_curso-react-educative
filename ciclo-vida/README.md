# Ciclo de vida

## componentWillMount()

Este método se invoca antes de que se monte un componente en el DOM. Esto sucede una vez en el ciclo de vida de un componente y antes del primer renderizado.

Se usa para inicializar valores(Es mejor usar el constructor) y hacer peticiones a la base de datos(Mejor usar omponentDidMount).

> componentWillMount () no es seguro y debe evitarse.

## 🔥 ComponentDidMount()

 cuando se monta un componente en el DOM

> Como este método se llama una vez después del primer renderizado, es posible que desee inicializar el estado y los accesorios que se requerirán en el DOM. En este momento, se puede solicitar información al servidor.

## componentDidUpdate()

Cuando se actualiza un componente

> puede usar este método para enviar solicitudes al servidor para cualquier actualización en el estado o accesorios del componente que se requieren para DOM.

## componentWillUnmount()

Cuando el componente se eleimina del DOM

> cuando un usuario cierra sesión en una aplicación, es posible que desee borrar sus credenciales y los demás tokens de autorización por motivos de seguridad.
