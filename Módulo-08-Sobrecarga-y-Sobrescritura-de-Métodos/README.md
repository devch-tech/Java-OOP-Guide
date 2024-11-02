# Módulo 08: Sobrecarga y Sobrescritura de Métodos

## Conclusión
La sobrecarga y la sobrescritura de métodos son dos conceptos esenciales en la Programación Orientada a Objetos que permiten una mayor flexibilidad y reutilización del código. Entender cómo y cuándo usarlos puede facilitar el diseño de programas más eficaces y fáciles de mantener.

## ¿Qué es la Sobrecarga de Métodos?
La **sobrecarga de métodos** ocurre cuando en una misma clase se definen múltiples métodos con el mismo nombre pero con diferentes parámetros (tipo, número o ambos). Esto permite que un método realice diferentes tareas según los argumentos que reciba.

### Importancia de la Sobrecarga
- **Flexibilidad:** Permite utilizar el mismo nombre de método para realizar tareas similares con diferentes tipos de datos.
- **Legibilidad:** Hace que el código sea más limpio y fácil de entender, ya que se puede usar un solo nombre para un conjunto de operaciones relacionadas.

## Ejemplo de la Vida Real
Imagina una calculadora. Puedes tener un método llamado `sumar`, que puede sumar dos números enteros, o bien sumar dos números de punto flotante. En ambos casos, se utiliza el mismo nombre de método, pero se manejan diferentes tipos de datos.

## ¿Qué es la Sobrescritura de Métodos?
La **sobrescritura de métodos** se refiere a la capacidad de una subclase de proporcionar una implementación específica de un método que ya está definido en su superclase. Esto permite que la subclase modifique el comportamiento del método heredado.

### Importancia de la Sobrescritura
- **Polimorfismo:** Permite que una referencia de superclase apunte a un objeto de subclase y ejecute el método sobrescrito.
- **Flexibilidad:** Permite adaptar el comportamiento de los métodos heredados a las necesidades específicas de la subclase.

## Ejemplo de la Vida Real
Imagina una clase base llamada `Animal` con un método `hacerSonido`. Las subclases como `Perro` y `Gato` pueden sobrescribir este método para emitir diferentes sonidos. Así, al llamar al método `hacerSonido` en un objeto de tipo `Animal`, se ejecutará el sonido específico del tipo de animal.

## Ejemplo de Código
A continuación, se presenta un ejemplo que ilustra la sobrecarga y sobrescritura de métodos en Java.

1. **Definición de la clase `Calculadora`:** Incluye métodos sobrecargados para sumar.
2. **Definición de la clase base `Animal`:** Contiene un método que será sobrescrito en las subclases.
3. **Subclases `Perro` y `Gato`:** Sobrescriben el método de la clase base.

### Código
```java
// Definición de la clase Calculadora
class Calculadora {
    // Método sobrecargado para sumar dos enteros
    int sumar(int a, int b) {
        return a + b;
    }

    // Método sobrecargado para sumar tres enteros
    int sumar(int a, int b, int c) {
        return a + b + c;
    }

    // Método sobrecargado para sumar dos números de punto flotante
    double sumar(double a, double b) {
        return a + b;
    }
}

// Clase base Animal
class Animal {
    void hacerSonido() {
        System.out.println("El animal hace un sonido");
    }
}

// Subclase Perro
class Perro extends Animal {
    @Override
    void hacerSonido() {
        System.out.println("El perro dice: ¡Guau!");
    }
}

// Subclase Gato
class Gato extends Animal {
    @Override
    void hacerSonido() {
        System.out.println("El gato dice: ¡Miau!");
    }
}

// Clase Principal
public class Main {
    public static void main(String[] args) {
        // Ejemplo de sobrecarga
        Calculadora calc = new Calculadora();
        System.out.println("Suma de 2 y 3: " + calc.sumar(2, 3)); // Salida: 5
        System.out.println("Suma de 1, 2 y 3: " + calc.sumar(1, 2, 3)); // Salida: 6
        System.out.println("Suma de 2.5 y 3.5: " + calc.sumar(2.5, 3.5)); // Salida: 6.0

        // Ejemplo de sobrescritura
        Animal miPerro = new Perro();
        miPerro.hacerSonido(); // Salida: El perro dice: ¡Guau!

        Animal miGato = new Gato();
        miGato.hacerSonido(); // Salida: El gato dice: ¡Miau!
    }
}
