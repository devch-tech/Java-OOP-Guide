# Módulo 10: Variables de Instancia y Variables de Clase

## Conclusión
Entender la diferencia entre variables de instancia y variables de clase es esencial para gestionar el estado de los objetos en la Programación Orientada a Objetos. Te ayudará a escribir código más claro y a evitar confusiones en el uso de atributos dentro de tus clases.

## ¿Qué son las Variables de Instancia?
Las **variables de instancia** son atributos que pertenecen a una instancia específica de una clase. Cada objeto creado a partir de la clase tiene su propio conjunto de variables de instancia, lo que significa que cada objeto puede tener valores diferentes para estos atributos.

### Características de las Variables de Instancia
- **Almacenamiento individual:** Cada objeto tiene su propia copia de las variables de instancia.
- **Acceso a través de métodos:** Pueden ser accedidas y modificadas a través de métodos de instancia.
- **Estado del objeto:** Representan el estado específico de un objeto.

## Ejemplo de la Vida Real
Imagina una clase `Persona`. Cada persona tiene atributos como `nombre`, `edad` y `altura`. Cuando creas un objeto de la clase `Persona`, cada persona tendrá un nombre, edad y altura distintos, es decir, sus variables de instancia tendrán diferentes valores.

## ¿Qué son las Variables de Clase?
Las **variables de clase** son atributos que pertenecen a la clase en sí y no a ninguna instancia específica. También se les llama **variables estáticas**. Esto significa que todas las instancias de la clase comparten el mismo valor de la variable de clase.

### Características de las Variables de Clase
- **Almacenamiento compartido:** Solo hay una copia de la variable de clase, compartida por todas las instancias de la clase.
- **Acceso a través del nombre de la clase:** Se accede a ellas usando el nombre de la clase en lugar de un objeto.
- **Uso común:** Son útiles para almacenar información que es común a todas las instancias.

## Ejemplo de la Vida Real
Considera una clase `Banco` que tiene una variable de clase llamada `tasaInteres`. Esta tasa es la misma para todos los clientes del banco. Cuando se actualiza la tasa de interés, se refleja en todas las instancias de `Banco`, ya que es una variable de clase.

## Ejemplo de Código
A continuación, se presenta un ejemplo que ilustra la diferencia entre variables de instancia y variables de clase en Java.

### Código
```java
// Clase Persona
class Persona {
    // Variable de instancia
    private String nombre;
    private int edad;

    // Variable de clase
    private static int contadorPersonas = 0;

    // Constructor
    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
        contadorPersonas++; // Aumentar el contador al crear una nueva persona
    }

    // Método para mostrar información
    public void mostrarInformacion() {
        System.out.println("Nombre: " + nombre + ", Edad: " + edad);
    }

    // Método estático para mostrar el número total de personas
    public static void mostrarContadorPersonas() {
        System.out.println("Número total de personas: " + contadorPersonas);
    }
}

// Clase Principal
public class Main {
    public static void main(String[] args) {
        // Creando instancias de Persona
        Persona persona1 = new Persona("Alice", 30);
        Persona persona2 = new Persona("Bob", 25);

        // Mostrando información de cada persona
        persona1.mostrarInformacion(); // Salida: Nombre: Alice, Edad: 30
        persona2.mostrarInformacion(); // Salida: Nombre: Bob, Edad: 25

        // Mostrando el número total de personas
        Persona.mostrarContadorPersonas(); // Salida: Número total de personas: 2
    }
}

