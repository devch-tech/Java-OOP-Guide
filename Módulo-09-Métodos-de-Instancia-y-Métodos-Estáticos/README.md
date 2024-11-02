# Módulo 09: Métodos de Instancia y Métodos Estáticos

## Conclusión
Entender la diferencia entre métodos de instancia y métodos estáticos es fundamental en la Programación Orientada a Objetos. Esta comprensión te permitirá estructurar tu código de manera eficiente, aprovechando al máximo las características de Java.

## ¿Qué son los Métodos de Instancia?
Los **métodos de instancia** son aquellos que pertenecen a una instancia específica de una clase. Esto significa que para poder invocar un método de instancia, primero necesitas crear un objeto de esa clase. Cada objeto puede tener diferentes estados (valores de sus atributos) y los métodos de instancia pueden acceder y modificar esos valores.

### Características de los Métodos de Instancia
- **Acceso a atributos:** Pueden acceder a los atributos de la clase y manipularlos.
- **Necesitan un objeto:** Deben ser llamados en el contexto de un objeto creado a partir de la clase.
- **Pueden sobreescribirse:** Si se trata de métodos en una subclase, se pueden sobrescribir para cambiar su comportamiento.

## Ejemplo de la Vida Real
Piensa en una clase `Coche`. Cada coche (instancia) tiene su propio color, marca y modelo. Si creas un método como `acelerar()`, cada coche puede tener su propia forma de acelerar basada en sus atributos específicos.

## ¿Qué son los Métodos Estáticos?
Los **métodos estáticos** pertenecen a la clase en sí, y no a una instancia de la clase. Esto significa que no necesitas crear un objeto para utilizarlos. Los métodos estáticos son ideales para operaciones que no dependen del estado de una instancia específica.

### Características de los Métodos Estáticos
- **Acceso limitado:** No pueden acceder a los atributos de instancia directamente. Solo pueden acceder a otros métodos estáticos y atributos estáticos.
- **Llamada sin instancia:** Pueden ser llamados directamente usando el nombre de la clase.
- **Comunes para todos los objetos:** Utilizados generalmente para operaciones que son comunes para todas las instancias de una clase.

## Ejemplo de la Vida Real
Imagina una clase `Matematica` que tiene un método estático `sumar()`. Este método puede sumar dos números y no necesita una instancia de `Matematica` porque la operación de suma no depende de un estado específico de un objeto.

## Ejemplo de Código
A continuación, se presenta un ejemplo que ilustra la diferencia entre métodos de instancia y métodos estáticos en Java.

### Código
```java
// Clase Coche
class Coche {
    // Atributos de instancia
    private String marca;
    private String color;

    // Constructor
    public Coche(String marca, String color) {
        this.marca = marca;
        this.color = color;
    }

    // Método de instancia
    public void acelerar() {
        System.out.println("El coche " + marca + " de color " + color + " está acelerando.");
    }

    // Método estático
    public static void mostrarMarca(String marca) {
        System.out.println("La marca del coche es: " + marca);
    }
}

// Clase Principal
public class Main {
    public static void main(String[] args) {
        // Creando instancias de Coche
        Coche miCoche = new Coche("Toyota", "rojo");
        Coche otroCoche = new Coche("Ford", "azul");

        // Llamando a un método de instancia
        miCoche.acelerar(); // Salida: El coche Toyota de color rojo está acelerando.
        otroCoche.acelerar(); // Salida: El coche Ford de color azul está acelerando.

        // Llamando a un método estático
        Coche.mostrarMarca("Toyota"); // Salida: La marca del coche es: Toyota
        Coche.mostrarMarca("Ford"); // Salida: La marca del coche es: Ford
    }
}
