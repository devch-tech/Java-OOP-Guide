# Módulo 06: Abstracción

## Conclusión
La abstracción es una técnica que permite a los desarrolladores enfocarse en lo esencial de un objeto, ignorando los detalles innecesarios. Facilita la creación de software más limpio, modular y fácil de mantener. Al utilizar la abstracción, puedes diseñar sistemas complejos dividiéndolos en partes más simples y manejables.

## ¿Qué es la Abstracción?
La abstracción es un principio fundamental de la Programación Orientada a Objetos (POO) que permite representar conceptos complejos de manera simplificada. Consiste en ocultar los detalles de implementación y mostrar solo las características relevantes de un objeto. Esto significa que, en lugar de preocuparte por cómo funciona un objeto internamente, solo te enfocas en lo que el objeto puede hacer.

### Ejemplos de Abstracción
Imagina un control remoto de televisión. Los botones permiten realizar acciones como encender el televisor, cambiar de canal o ajustar el volumen. Como usuario, no necesitas saber cómo funciona internamente cada botón; simplemente presionas el que necesitas. Esta es la esencia de la abstracción: interactuar con un objeto a través de una interfaz simple, sin preocuparse por su implementación interna.

### Importancia de la Abstracción
La abstracción tiene varias ventajas, entre las que se incluyen:

- **Simplicidad:** Ayuda a reducir la complejidad del sistema, permitiendo que los desarrolladores se concentren en el comportamiento general sin perderse en los detalles.
- **Modularidad:** Facilita el desarrollo de sistemas modulares, donde diferentes partes pueden ser desarrolladas y mantenidas de manera independiente.
- **Reusabilidad:** Los componentes abstractos pueden ser reutilizados en diferentes contextos, lo que reduce la duplicación de código y mejora la eficiencia del desarrollo.

## Cómo Implementar la Abstracción en Java
En Java, la abstracción se puede lograr mediante:
1. **Clases Abstractas:** Una clase abstracta es una clase que no se puede instanciar por sí misma y puede contener métodos abstractos (sin implementación) que deben ser implementados por las subclases. 
2. **Interfaces:** Una interfaz es un contrato que define métodos que una clase debe implementar. A diferencia de las clases abstractas, las interfaces no pueden contener implementación (en Java 7 y anteriores) y se utilizan para definir comportamientos que pueden ser compartidos entre clases no relacionadas.

## Ejemplos de la Vida Real
Considera el concepto de "Animal". Un animal puede ser un perro, un gato o un pájaro. La clase abstracta `Animal` puede definir métodos como `hacerSonido()` y `moverse()`, pero no tiene una implementación específica. Cada subclase (como `Perro` o `Gato`) proporcionará su propia implementación de estos métodos.

### Ejemplo de Código
Aquí tienes un ejemplo que ilustra cómo se implementa la abstracción en Java:

1. **Clase Abstracta `Animal`:** Define los métodos `hacerSonido()` y `moverse()`, que son abstractos.
2. **Clases Concretas (`Perro`, `Gato`):** Estas clases extienden `Animal` y proporcionan implementaciones concretas para los métodos abstractos.
3. **Clase Principal `Main`:** Aquí se crea un objeto de tipo `Animal` que puede referirse a cualquier subclase, demostrando cómo se puede trabajar con objetos abstractos.

### Código
```java
// Clase Abstracta
abstract class Animal {
    abstract void hacerSonido();
    abstract void moverse();
}

// Clase Hija: Perro
class Perro extends Animal {
    @Override
    void hacerSonido() {
        System.out.println("El perro ladra: ¡Guau!");
    }

    @Override
    void moverse() {
        System.out.println("El perro corre.");
    }
}

// Clase Hija: Gato
class Gato extends Animal {
    @Override
    void hacerSonido() {
        System.out.println("El gato maulla: ¡Miau!");
    }

    @Override
    void moverse() {
        System.out.println("El gato salta.");
    }
}

// Clase Principal
public class Main {
    public static void main(String[] args) {
        Animal miAnimal;

        miAnimal = new Perro();
        miAnimal.hacerSonido(); // Salida: El perro ladra: ¡Guau!
        miAnimal.moverse();      // Salida: El perro corre.

        miAnimal = new Gato();
        miAnimal.hacerSonido(); // Salida: El gato maulla: ¡Miau!
        miAnimal.moverse();      // Salida: El gato salta.
    }
}
