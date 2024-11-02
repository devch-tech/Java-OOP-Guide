# Módulo 06: Interfaces

## Conclusión
Las interfaces son una herramienta poderosa en la Programación Orientada a Objetos que permiten definir un contrato que las clases deben seguir. Fomentan la reutilización de código y el diseño limpio, permitiendo a los desarrolladores construir sistemas más flexibles y escalables.

## ¿Qué son las Interfaces?
Una **interfaz** en Java es un contrato que define un conjunto de métodos que una clase debe implementar. A diferencia de una clase abstracta, una interfaz solo puede contener métodos abstractos (hasta Java 7) y constantes. Esto significa que las interfaces no pueden proporcionar implementación de métodos, sino que describen lo que las clases deben hacer.

### Características de las Interfaces
- **No pueden ser instanciadas:** No puedes crear un objeto de una interfaz. Solo se pueden implementar en clases.
- **Métodos abstractos:** A partir de Java 8, las interfaces pueden contener métodos por defecto con una implementación, pero los métodos declarados en una interfaz son, por defecto, abstractos.
- **Múltiple herencia:** Una clase puede implementar múltiples interfaces, lo que permite una forma de herencia múltiple en Java.

## Importancia de las Interfaces
Las interfaces son fundamentales porque permiten a las clases trabajar juntas de manera más efectiva y proporcionan un marco para la comunicación entre diferentes partes del sistema. Algunas de las ventajas de utilizar interfaces son:

- **Flexibilidad:** Permiten que diferentes clases implementen los mismos métodos de maneras distintas, facilitando la implementación de polimorfismo.
- **Desacoplamiento:** Ayudan a reducir la dependencia entre componentes de un sistema, lo que mejora la mantenibilidad y la prueba del código.
- **Reusabilidad:** Puedes crear una interfaz y hacer que varias clases la implementen, lo que evita la duplicación de código.

## Ejemplos de la Vida Real
Piensa en un **dispositivo de carga** para teléfonos móviles. Todos los cargadores deben tener un puerto USB, pero cada uno puede tener diferentes características (como carga rápida, carga solar, etc.). En este caso, puedes definir una interfaz `Cargador` con un método `cargar()`. Cada cargador específico implementaría esta interfaz, proporcionando su propia forma de cargar el dispositivo.

### Implementación de Interfaces en Java
Cuando una clase implementa una interfaz, se compromete a proporcionar implementaciones para todos los métodos definidos en la interfaz. Esto se hace utilizando la palabra clave `implements`.

## Ejemplo de Código
Aquí tienes un ejemplo que ilustra cómo se implementan las interfaces en Java:

1. **Definición de la Interfaz `Cargador`:** Contiene un método abstracto `cargar()`.
2. **Clases Concretas (`CargadorSolar`, `CargadorRápido`):** Estas clases implementan la interfaz y proporcionan sus propias implementaciones para el método `cargar()`.
3. **Clase Principal `Main`:** Crea objetos de las clases que implementan la interfaz y llama a sus métodos.

### Código
```java
// Definición de la Interfaz
interface Cargador {
    void cargar();
}

// Clase que implementa la interfaz Cargador: CargadorSolar
class CargadorSolar implements Cargador {
    @Override
    public void cargar() {
        System.out.println("Cargando el dispositivo con energía solar.");
    }
}

// Clase que implementa la interfaz Cargador: CargadorRápido
class CargadorRapido implements Cargador {
    @Override
    public void cargar() {
        System.out.println("Cargando el dispositivo rápidamente.");
    }
}

// Clase Principal
public class Main {
    public static void main(String[] args) {
        Cargador cargador;

        cargador = new CargadorSolar();
        cargador.cargar(); // Salida: Cargando el dispositivo con energía solar.

        cargador = new CargadorRapido();
        cargador.cargar(); // Salida: Cargando el dispositivo rápidamente.
    }
}
