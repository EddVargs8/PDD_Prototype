## Edwin Alejandro Vargas Reyes - 19290961
# **Prototype**
![Patron de diseño prototype](https://refactoring.guru/images/patterns/cards/prototype-mini-3x.png)

Pertenece a la categoría de **patrones creacionales**. Estos se centran en cómo crear objetos de manera que se favorezca la flexibilidad y la reutilización del código. El patrón **Prototype** se utiliza cuando queremos crear nuevos objetos copiando o "clonando" una instancia existente en lugar de crearlos desde cero 

## Ejemplo

Una empresa de transporte gestiona una flota de vehículos, Cada vehículo tiene características comunes (tipo, color, motor, etc.), pero existen muchos vehículos que comparten las mismas configuraciones.

Crear cada uno de estos vehículos desde cero usando el constructor de una clase puede ser ineficiente, especialmente cuando la mayoría de ellos solo difieren en algunos detalles. Esta repetición de creación puede ser costosa en términos de tiempo de desarrollo y recursos computacionales.

-   Prototype permite crear objetos rápidamente mediante clonación sin la necesidad de definir una gran cantidad de subclases.

-   Prototype facilita la extensión y modificación de objetos en tiempo de ejecución.

-   Prototype reduce la repetición de código, ya que no necesitas duplicar lógica común en múltiples subclases.

-   Prototype ofrece flexibilidad para manejar nuevas configuraciones y cambios sin requerir una reestructuración completa del código.

## Código en JS
```javascript
// Clase base Vehicle
class Vehicle {
  constructor(type, color, engine) {
    this.type = type;
    this.color = color;
    this.engine = engine;
  }

  // Método para clonar el vehículo actual
  clone() {
    return new Vehicle(this.type, this.color, this.engine);
  }
}

// Crear prototipos específicos
const carPrototype = new Vehicle("Car", "Red", "V4");
const truckPrototype = new Vehicle("Truck", "Blue", "V8");

// Clonar los prototipos para crear nuevos vehículos
const car1 = carPrototype.clone();
const car2 = carPrototype.clone();
const truck1 = truckPrototype.clone();

// Modificar algunas propiedades si es necesario
car1.color = "Black";
truck1.engine = "V10";


```
Pros y contras

✅ Puedes clonar objetos sin acoplarlos a sus clases concretas.

✅ Obtienes una alternativa a la herencia al tratar con preajustes de configuración para objetos complejos.

✅ Ofrece la posibilidad de que el cliente genere objetos de un tipo desconocido.

❌ Clonar objetos complejos con referencias circulares puede resultar complicado.




