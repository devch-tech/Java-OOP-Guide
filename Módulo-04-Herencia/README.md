# Módulo 04: Herencia

## ¿Qué es la Herencia?
La herencia es un principio fundamental de la Programación Orientada a Objetos (POO) que permite crear una nueva clase basada en una clase existente. La clase existente se llama **clase padre** o **superclase**, y la nueva clase se denomina **clase hija** o **subclase**. Esta relación permite a la subclase heredar los atributos y métodos de la superclase, lo que promueve la reutilización de código y la organización del mismo.

## Ventajas de la Herencia
- **Reutilización de Código:** Permite utilizar el código de una clase existente sin necesidad de reescribirlo.
- **Organización:** Facilita la organización y la estructura del código, haciendo que sea más fácil de entender y mantener.
- **Polimorfismo:** Permite a las subclases ser tratadas como instancias de la superclase, lo que ofrece mayor flexibilidad en el diseño del software.

## Cómo Funciona la Herencia
Cuando una clase hija hereda de una clase padre, obtiene todos los atributos y métodos de la clase padre. La clase hija puede:
- **Usar** los métodos y atributos heredados.
- **Sobrescribir** (override) métodos de la clase padre para modificar su comportamiento.
- **Agregar** nuevos métodos y atributos propios.

### Ejemplo de Herencia
Consideremos un ejemplo sencillo para ilustrar la herencia. Supongamos que tenemos una clase `Animal` que representa animales en general. Luego, crearemos una subclase `Perro` que hereda de `Animal`:

1. **Clase Padre: Animal**
   - Esta clase tendrá atributos comunes a todos los animales, como `nombre` y `edad`, y un método llamado `hacerSonido()` que se puede sobrescribir en las subclases.

2. **Clase Hija: Perro**
   - La clase `Perro` hereda de `Animal`, por lo que tendrá acceso a `nombre` y `edad`, pero también puede definir su propio comportamiento, como un método `hacerSonido()` que imprima "¡Guau!".

### Sobrescritura de Métodos
La sobrescritura de métodos permite a la clase hija proporcionar una implementación específica de un método que ya está definido en la clase padre. Esto se realiza mediante el mismo nombre y la misma firma del método.

## Ejemplo de Código
Aquí está el ejemplo de código que ilustra la herencia en Java:

```java
// Clase Padre
class Animal {
    String nombre;
    int edad;

    // Constructor
    Animal(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    // Método para hacer sonido
    void hacerSonido() {
        System.out.println("El animal hace un sonido.");
    }
}

// Clase Hija
class Perro extends Animal {
    // Constructor
    Perro(String nombre, int edad) {
        super(nombre, edad); // Llamada al constructor de la clase padre
    }

    // Sobrescribiendo el método hacerSonido
    @Override
    void hacerSonido() {
        System.out.println(nombre + " dice: ¡Guau!");
    }
}

// Clase Principal
public class Main {
    public static void main(String[] args) {
        // Creando un objeto de la clase Perro
        Perro miPerro = new Perro("Fido", 3);
        System.out.println("Nombre: " + miPerro.nombre);
        System.out.println("Edad: " + miPerro.edad);
        miPerro.hacerSonido(); // Salida: Fido dice: ¡Guau!
    }
}
