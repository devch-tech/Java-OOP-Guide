# 🧩 Módulo 04: Herencia

## Definición de Herencia
La **herencia** es un concepto fundamental de la Programación Orientada a Objetos (POO) que permite que una clase (denominada clase hija o subclase) herede atributos y métodos de otra clase (denominada clase padre o superclase). Este mecanismo no solo promueve la reutilización del código, sino que también establece una jerarquía entre clases, facilitando la organización y el mantenimiento del software.

### Ventajas de la Herencia
1. **Reutilización de Código**: Las subclases pueden utilizar los métodos y atributos de la superclase, lo que reduce la duplicación de código y mejora la eficiencia.
2. **Organización del Código**: Permite agrupar clases relacionadas en una jerarquía, haciendo que el código sea más comprensible y fácil de manejar.
3. **Polimorfismo**: Las subclases pueden ser tratadas como instancias de la superclase, lo que permite utilizar una interfaz común para diferentes tipos de objetos.

## Sintaxis de Herencia en Java
En Java, la herencia se define utilizando la palabra clave `extends`. La subclase hereda todos los métodos y atributos de la superclase, pero solo aquellos que no son `private`.

### Ejemplo de Herencia
Para ilustrar cómo funciona la herencia, consideremos un ejemplo con una clase padre llamada `Animal` y dos clases hijas: `Perro` y `Gato`.

### Explicación del Ejemplo
1. **Clase Padre `Animal`**: Esta clase contiene un atributo `nombre` y un método `hacerSonido()`, que puede ser sobrescrito por las subclases.
  
2. **Clases Hijas `Perro` y `Gato`**:
   - Ambas heredan de `Animal` usando `extends`.
   - En el constructor de cada clase hija, se utiliza `super(nombre)` para invocar el constructor de la clase padre y establecer el nombre del animal.
   - Cada subclase proporciona su propia implementación del método `hacerSonido()` utilizando la anotación `@Override`. Esto permite que cada tipo de animal produzca un sonido específico.

3. **Uso en el Método `main`**:
   - Creamos instancias de `Perro` y `Gato` y las asignamos a variables de tipo `Animal`. Esto demuestra el polimorfismo: aunque son diferentes tipos de objetos, se pueden manejar como instancias de la misma clase base.

## Conclusión
La herencia es una herramienta poderosa en la Programación Orientada a Objetos que permite crear jerarquías de clases y reutilizar código de manera efectiva. Al entender cómo funciona la herencia, los desarrolladores pueden escribir código más limpio y mantenible, reflejando mejor el mundo real en sus programas.

---

### Bloques de Código

```java
// Clase padre
class Animal {
    // Atributos
    String nombre;
    
    // Constructor
    public Animal(String nombre) {
        this.nombre = nombre;
    }

    // Método que describe el sonido que hace el animal
    public void hacerSonido() {
        System.out.println(nombre + " hace un sonido.");
    }
}

// Clase hija
class Perro extends Animal {
    public Perro(String nombre) {
        super(nombre); // Llama al constructor de la clase padre
    }

    // Sobrescribe el método hacerSonido
    @Override
    public void hacerSonido() {
        System.out.println(nombre + " dice: ¡Guau!");
    }
}

// Otra clase hija
class Gato extends Animal {
    public Gato(String nombre) {
        super(nombre); // Llama al constructor de la clase padre
    }

    // Sobrescribe el método hacerSonido
    @Override
    public void hacerSonido() {
        System.out.println(nombre + " dice: ¡Miau!");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal miPerro = new Perro("Fido");
        Animal miGato = new Gato("Mimi");

        miPerro.hacerSonido(); // Salida: Fido dice: ¡Guau!
        miGato.hacerSonido(); // Salida: Mimi dice: ¡Miau!
    }
}

