# 🧩 Clases y Objetos

## Definición de clase y objeto
En la POO, una **clase** es una plantilla o modelo que define un tipo de objeto. Contiene atributos (propiedades) y métodos (comportamientos) que describen lo que puede hacer un objeto de esa clase. Un **objeto** es una instancia de una clase; representa un elemento concreto que tiene su propio estado y comportamiento.

**Ejemplo de la vida real:** Piensa en una **receta de pastel**. La receta es la clase, que describe cómo hacer un pastel (ingredientes y pasos). Cada pastel que se hornea siguiendo esa receta es un objeto, ya que es una instancia concreta de la receta.

## Creación de clases y objetos en Java
Para crear una clase en Java, se utiliza la palabra clave `class`, seguida del nombre de la clase. Dentro de la clase, se definen los atributos y métodos. Para crear un objeto, se utiliza la palabra clave `new` junto con el nombre de la clase.

## Diferencias entre clases y objetos
- **Clase**: Es un concepto abstracto que define un tipo de objeto. No ocupa memoria hasta que se crea un objeto.
- **Objeto**: Es una instancia concreta de una clase. Ocupa memoria y tiene un estado específico.

**Ejemplo de la vida real:** Siguiendo el ejemplo del pastel, la receta (clase) no es comestible ni ocupa espacio en la cocina, mientras que el pastel horneado (objeto) es un producto tangible que puedes comer y ocupa espacio.

## Resumen
Las clases y objetos son los bloques de construcción fundamentales de la Programación Orientada a Objetos. Las clases definen las características y comportamientos, mientras que los objetos representan instancias concretas de esas definiciones, permitiendo modelar el mundo real en el software.

### Ejemplo de Código
Aquí tienes un ejemplo simple que muestra cómo crear una clase `Perro` y un objeto de esa clase:



```java
class Perro {
    // Atributos
    String nombre;
    String raza;

    // Método para ladrar
    void ladrar() {
        System.out.println(nombre + " dice: ¡Guau!");
    }
}

public class Main {
    public static void main(String[] args) {
        // Creando un objeto de la clase Perro
        Perro miPerro = new Perro();
        miPerro.nombre = "Fido";
        miPerro.raza = "Labrador";
        
        // Usando el método del objeto
        miPerro.ladrar(); // Salida: Fido dice: ¡Guau!
    }
}
