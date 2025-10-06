# Patrones de Diseño y su relación con Programación Orientada a Objetos

## Programación orientada a objetos

La POO basa el diseño de software alrededor de la figura de los objetos, elementos que contienen propiedades y comportamiento.

```text
Class -> person
- firstName: string
- lastName: string
- method run
- method walk
```

### Pilares de la POO

- **Abstracción**: Oculta la complejidad mostrando solo lo escencial
- **Polimorfismo**: Múltipes formas de implementar un mismo comportamiento
- **Encapsulamiento**: Proteger y ocultar el estado interno de los objetos
- **Herencia**: Reutiliza código heredando propiedades y comportamientos

#### Herencia y composición

##### Herencia

1. La subclase y la superclase están estrechamente acopladas.
2. Una subclase no puede reducir la interfaz de la superclase.
3. Tratando de reusar el mayor código posible podemos crear clasificaciones (taxonomías) de clases complejas

##### Composición

Una relación entre dos clases, en donde una de ellas o ambas,
hace referencia a objetos de la otra clase en sus propiedades.

#### Relación entre clases y diagrama UML

**UML**: Unified Model Language

##### Relación de dependencia

Hay una dependencia entre dos clases si al realizar cambios en alguna de ellas resulta en modificaciones en la otra.

```typescript
class Builder:
  public method build(hammer: Tool) is
    // If useIt method is renamed our code will fail
    hammer.useIt()
```

##### Relación de asociación

Hay una asociación entre clases si uno de ellos tiene acceso de forma permanente a los objetos de la otra. Esta relación está representada usualmente como un atributo de clase.

```typescript
class Builder:
  // Hammer is available for all the class methods
  private ownHammer: Tool

  public method build() is
    // If useIt method is renamed our code will fail
    ownHammer.useIt()
```

##### Relación de implementación

La relación de implementación se da cuando una clase define su comportamiento con base en el definido en una interfaz.

```typescript
interface TextFormater {
  public method format(text)
}

// Both classes based theri behavior in the interface
class PlanTextFormatter implements TextFormatter:
  public format(text) is
    print("PLAIN TEXT: " + text)

class ShortTextFormatter implements TextFormatter:
  public format(text) is
    print("SHORT TEXT: " + text)
```

##### Relación de herencia

Hay una relación de herencia, cuando una clase es capaz de utilizar la misma interfaz e implementación de otra, pero con la posibilidad de extender su comportamiento.

```typescript
class Node:
  private text: string
  private next: Node

class LinkedList:
  private head: Node
  private tail: Node

  public method append(textToInsert) is
    // Insert an element in the list

  public method remove(textToDelete) is
    // Delete the desire element in the list

// A queue that uses a linked list internally
class Queue that uses a linked list internally

  public method enqueue(text) is
    //Call the method defined in the parent
    parent.append(text)

  public method dequeue(text) is
    // Call the method defined in the parent
    parent.remove(text)
```

##### Relación de agregación

Hay una relación de agregación entre clases si el objeto generado por una de ellas "tiene" uno o más objetos de la otra. La clase contenedora no gestiona el ciclo de vida de los objetos.

```typescript
class Vehicle:
  private engine: Engine
  private wheels: Array<Wheel>

  // We pass the object as params,
  // the class doesn't create the objects
  constructor(newEngine, wheelsList) is
    engine = newEngine
    wheels = wheelsList

  public method verifyWheels() is
    for wheel in wheels:
      var isWheelReady = wheel.verify()
      if(!isWheelReady) return false
    return true

  public method turnOn() is
    var allWheelsReady = verifyWheels()
    if (!allWheelsReady) return
    engine.start()
```

##### Relación de composición

Hay una relación de composición entre clases si el objeto generado por una de ella consiste de uno o más objetos de la otra. La clase contenedora gestiona el ciclo de vida de lo objetos.

```typescript
class Vehicle:
  private engine: Engine
  private wheels: Array<Wheel>

  constructor() is
    engine = newEngine()
    // This returns a list of wheels
    wheels = new Wheel.get(4)

  public method verifyWheels() is
    for wheel in wheels:
      var isWheelReady = wheel.verify()
      if(!isWheelReady) return false
    return true

  public method turnOn() is
    var allWheelsReady = verifyWheels()
    if (!allWheelsReady) return
    engine.start()
```

## A considerar...

1. Necesitas aprender sobre patrones de diseño para avanzar en el Desarrollo de software
2. Conocimiento sobre patrones de diseño como requisitos para posiciones en la industria.
3. Los patrones de diseño deben de dejar de ser enseñados usando POO y ser enseñados con paradigmas con mayor presencia (funcional) en el mercado.
4. Los patrones de diseño no solo te enseñan a solucionar un problema, sino también a pensar con creatividad.
