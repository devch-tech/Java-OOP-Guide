# Módulo 07: Constructores y Sobrecarga de Constructores

## Conclusión
Los constructores son fundamentales para la creación de objetos en Java. Comprender cómo funcionan y cómo se pueden sobrecargar es esencial para utilizar eficazmente la Programación Orientada a Objetos, permitiendo un control más preciso sobre la inicialización de los objetos.

## ¿Qué es un Constructor?
Un **constructor** en Java es un método especial que se llama cuando se crea un nuevo objeto. Su propósito principal es inicializar los atributos del objeto y establecer un estado inicial. A diferencia de los métodos normales, un constructor tiene el mismo nombre que la clase y no tiene un tipo de retorno, ni siquiera `void`.

### Tipos de Constructores
1. **Constructor por Defecto:** Es un constructor que no tiene parámetros. Si no se define ningún constructor en la clase, Java proporciona uno por defecto que no realiza ninguna operación específica.
2. **Constructor Parametrizado:** Este tipo de constructor acepta parámetros que se utilizan para inicializar los atributos del objeto al momento de su creación.

## Importancia de los Constructores
Los constructores son importantes porque:
- **Inicializan el estado del objeto:** Permiten establecer valores iniciales para los atributos de la clase.
- **Facilitan la creación de objetos:** Los constructores hacen que la creación de objetos sea más clara y menos propensa a errores, ya que aseguran que el objeto está en un estado válido.

## Sobrecarga de Constructores
La **sobrecarga de constructores** se refiere a la capacidad de tener más de un constructor en la misma clase, cada uno con diferentes parámetros. Esto permite crear objetos de una clase de varias maneras, adaptándose a diferentes necesidades.

### Ventajas de la Sobrecarga
- **Flexibilidad:** Permite crear objetos con diferentes configuraciones sin necesidad de definir múltiples clases.
- **Código más limpio:** Reduce la necesidad de métodos adicionales para crear instancias de una clase.

## Ejemplos de la Vida Real
Imagina que estás construyendo una aplicación para gestionar estudiantes. Podrías tener una clase `Estudiante` que tiene un constructor por defecto que inicializa un estudiante sin datos y un constructor parametrizado que permite establecer el nombre y la edad del estudiante en el momento de la creación.

## Ejemplo de Código
A continuación, se presenta un ejemplo que ilustra cómo funcionan los constructores y la sobrecarga de constructores en Java.

1. **Definición de la clase `Estudiante`:** Incluye un constructor por defecto y un constructor parametrizado.
2. **Clase Principal `Main`:** Crea objetos de la clase `Estudiante` utilizando ambos constructores.

### Código
```java
// Definición de la clase Estudiante
class Estudiante {
    String nombre;
    int edad;

    // Constructor por defecto
    Estudiante() {
        this.nombre = "Desconocido";
        this.edad = 0;
    }

    // Constructor parametrizado
    Estudiante(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    // Método para mostrar la información del estudiante
    void mostrarInfo() {
        System.out.println("Nombre: " + nombre + ", Edad: " + edad);
    }
}

// Clase Principal
public class Main {
    public static void main(String[] args) {
        // Creando un objeto usando el constructor por defecto
        Estudiante estudiante1 = new Estudiante();
        estudiante1.mostrarInfo(); // Salida: Nombre: Desconocido, Edad: 0

        // Creando un objeto usando el constructor parametrizado
        Estudiante estudiante2 = new Estudiante("Juan", 20);
        estudiante2.mostrarInfo(); // Salida: Nombre: Juan, Edad: 20
    }
}
