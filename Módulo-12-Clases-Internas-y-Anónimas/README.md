# Módulo 12: Clases Internas y Anónimas

## Conclusión
Las clases internas y anónimas son herramientas útiles en Java que permiten estructurar el código de manera más organizada y comprensible. Aprender a utilizarlas puede mejorar la legibilidad y funcionalidad de tu programa, facilitando la implementación de características que requieren una relación cercana entre clases.

## ¿Qué son las Clases Internas?
Las **clases internas** son clases definidas dentro de otra clase. Permiten agrupar clases que están relacionadas y ayudan a acceder a los miembros de la clase externa. Existen varios tipos de clases internas:

1. **Clases Internas No Estáticas**: Tienen acceso a los miembros de la clase externa, incluidos los atributos y métodos privados.
2. **Clases Internas Estáticas**: No pueden acceder a los miembros no estáticos de la clase externa, pero pueden tener sus propios miembros estáticos.

### Características de las Clases Internas
- Facilitan la encapsulación y el mantenimiento del código.
- Permiten acceder a los miembros de la clase externa sin necesidad de instanciarla.
- Pueden ser útiles en situaciones donde una clase necesita realizar operaciones específicas en su clase contenedora.

## Ejemplo de la Vida Real
Imagina que estás creando una aplicación de gestión de estudiantes. Tendrás una clase `Escuela` y dentro de ella, una clase interna `Estudiante`. La clase `Estudiante` puede acceder a la información de la clase `Escuela`, como el nombre de la escuela y la dirección, sin necesidad de crear una instancia de `Escuela`.

## ¿Qué son las Clases Anónimas?
Las **clases anónimas** son una forma especial de clases internas que no tienen un nombre. Se utilizan principalmente para crear instancias de clases que solo se necesitarán una vez. Son comunes en situaciones donde se necesita implementar interfaces o extender clases de manera rápida y directa.

### Características de las Clases Anónimas
- Se definen y se instancian al mismo tiempo.
- Se utilizan para crear instancias de clases que no se reutilizarán en otro lugar.
- Son útiles para implementar métodos de interfaz de manera rápida.

## Ejemplo de la Vida Real
Un ejemplo común de clase anónima es en la creación de un evento de clic en un botón en una aplicación gráfica. Puedes crear un manejador de eventos directamente donde se necesita, sin tener que definir una nueva clase por separado.

## Ejemplo de Código
A continuación, se presenta un ejemplo que ilustra el uso de clases internas y anónimas en Java.

### Código
```java
// Clase externa
class Escuela {
    private String nombre;

    public Escuela(String nombre) {
        this.nombre = nombre;
    }

    // Clase interna no estática
    class Estudiante {
        private String nombreEstudiante;

        public Estudiante(String nombreEstudiante) {
            this.nombreEstudiante = nombreEstudiante;
        }

        public void mostrarInformacion() {
            System.out.println("Escuela: " + nombre + ", Estudiante: " + nombreEstudiante);
        }
    }

    // Método para crear un estudiante
    public void crearEstudiante(String nombreEstudiante) {
        Estudiante estudiante = new Estudiante(nombreEstudiante);
        estudiante.mostrarInformacion();
    }
}

// Clase principal
public class Main {
    public static void main(String[] args) {
        Escuela escuela = new Escuela("Escuela Primaria");
        escuela.crearEstudiante("Juan"); // Salida: Escuela: Escuela Primaria, Estudiante: Juan

        // Clase anónima
        Runnable tarea = new Runnable() {
            @Override
            public void run() {
                System.out.println("Ejecutando una tarea en segundo plano.");
            }
        };
        tarea.run(); // Salida: Ejecutando una tarea en segundo plano.
    }
}
