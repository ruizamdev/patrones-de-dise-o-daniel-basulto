# ¿Qué son los Patrones de Diseño?

Soluciones habituales a problemas comunes en el diseño de software.

## Origen del término

El concepto de los "patrones" se orginó como un concepto arquitectónico por Christopher Alexander, en 1977 en su libro "Un lenguaje de patrones".

La idea fue recogida por cuatro autores (Gang of Four), Erich Gamma, John Vlissides, Ralph Johnson y Richard Helm, que en 1994 lanzan el libro "Patrones de diseño: Elementos Reutilizables en el Software Orientado a Objetos"

## ¿Debo aprender patrones de diseño?

Es indispensable aprender patrones de diseño por dos razones:

1. Son una caja de herramientas de soluciones a problemas comunes en el diseño de software.

2. Definen un lenguaje que tú y tu equipo usarán para comunicarse de forma eficiente.

### A considerar...

- Pueden ser vistos como planos prefabricados.
- Un patrón no es una biblioteca que podamos cortar, pegar y utilizar. Son implementados dentro del contexto del problema a resolver.
- Un patrón no es un algoritmo.
  - Un algoritmo nos dirá el orden de los pasos.
  - Un patrón nos dirá el resultado y sus funciones.

## Categorias de Patrones

### Patrones Creacionales

Su función es proveer mecanismos para la creación de objetos que favorecen la flexibilidad, reusabilidad y extensibilidad del código.

**Ejemplos:**

- Builder
- Factory method
- Singleton

### Patrones Estructurales

Su función es determinar cómo las clases y objetos se combinan/ensamblan para formar estructuras más grandes.

**Ejemplos:**

- Adapter
- Decorator
- Facade
- Proxy

### Patrones de Comportamiento

Su función es tratar con procedimientos que se encargan de implementar una comunicacion y asignación de responsabilidades efectiva entre objetos.

**Ejemplos:**

- Command
- Iterator
- Observer
- Strategy
