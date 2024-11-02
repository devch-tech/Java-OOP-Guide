# 🏁 Introducción a la Programación Orientada a Objetos

## ¿Qué es la Programación Orientada a Objetos?
La Programación Orientada a Objetos (POO) es un paradigma que organiza el software en "objetos". Cada objeto es una instancia de una clase y puede contener tanto datos como comportamientos. En lugar de ver el software como una simple secuencia de comandos, la POO permite agrupar propiedades y métodos en estructuras lógicas, facilitando la modelación de situaciones del mundo real.

**Ejemplo de la vida real:** Imagina un **automóvil**. Cada coche tiene propiedades como el **color**, **marca** y **modelo**, así como comportamientos como **acelerar**, **frenar** y **girar**. En la programación, un automóvil se representaría como un objeto.

## Importancia de la POO en el desarrollo de software
La POO es fundamental en el desarrollo de software moderno debido a varias razones:
- **Modularidad:** Permite dividir el software en partes más manejables (clases y objetos), facilitando el desarrollo y mantenimiento.
- **Reutilización:** Las clases pueden ser reutilizadas en diferentes programas, lo que ahorra tiempo y esfuerzo.
- **Escalabilidad:** Facilita la adición de nuevas funcionalidades sin afectar el sistema existente.
- **Facilidad de mantenimiento:** Los cambios en una clase no afectan a otras clases, siempre que la interfaz permanezca constante.

## Ventajas y características principales
1. **Encapsulamiento:** Permite ocultar los detalles internos de la implementación de un objeto, exponiendo solo lo necesario.
2. **Herencia:** Facilita la creación de nuevas clases basadas en clases existentes, promoviendo la reutilización del código.
3. **Polimorfismo:** Permite que diferentes clases sean tratadas como instancias de la misma clase a través de una interfaz común, lo que simplifica el código.
4. **Abstracción:** Permite trabajar con conceptos complejos a un nivel más alto, simplificando el diseño del software.

## Ejemplo de Código
A continuación, un ejemplo que muestra una clase simple que representa un **Coche**:

```java
class Coche {
    // Atributos
    String color;
    String marca;

    // Método para acelerar
    void acelerar() {
        System.out.println("El coche " + color + " de marca " + marca + " está acelerando.");
    }

    // Método para frenar
    void frenar() {
        System.out.println("El coche " + color + " de marca " + marca + " está frenando.");
    }
}

public class Main {
    public static void main(String[] args) {
        // Creando un objeto de la clase Coche
        Coche miCoche = new Coche();
        miCoche.color = "Rojo";
        miCoche.marca = "Toyota";
        
        // Usando los métodos del objeto
        miCoche.acelerar(); // Salida: El coche Rojo de marca Toyota está acelerando.
        miCoche.frenar();   // Salida: El coche Rojo de marca Toyota está frenando.
    }
}
