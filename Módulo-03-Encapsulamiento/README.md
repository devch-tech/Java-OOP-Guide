# 🧩 Módulo 03: Encapsulamiento

## Definición de Encapsulamiento
El **encapsulamiento** es un principio fundamental de la Programación Orientada a Objetos (POO) que consiste en ocultar los detalles internos de una clase y exponer solo lo necesario a través de métodos públicos. Esto ayuda a proteger el estado interno del objeto y a controlar cómo se accede y se modifica.

## Beneficios del Encapsulamiento
- **Control de acceso**: Permite definir qué atributos y métodos son accesibles desde fuera de la clase.
- **Protección de datos**: Evita modificaciones no autorizadas en los atributos de la clase.
- **Flexibilidad**: Facilita la modificación interna de una clase sin afectar el código que la utiliza.
- **Mantenimiento**: Mejora la mantenibilidad del código al reducir las dependencias entre las clases.

## Modificadores de Acceso
En Java, existen cuatro modificadores de acceso que determinan la visibilidad de los atributos y métodos:
- **public**: Accesible desde cualquier parte del programa.
- **private**: Solo accesible dentro de la propia clase.
- **protected**: Accesible dentro de la misma clase, clases hijas y clases en el mismo paquete.
- **default**: (sin modificador) Accesible solo dentro del mismo paquete.

## Ejemplo de Código
Aquí tienes un ejemplo que muestra cómo implementar el encapsulamiento en Java:

```java
class Persona {
    // Atributos privados
    private String nombre;
    private int edad;

    // Método público para establecer el nombre
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    // Método público para obtener el nombre
    public String getNombre() {
        return nombre;
    }

    // Método público para establecer la edad
    public void setEdad(int edad) {
        if (edad > 0) { // Validación simple
            this.edad = edad;
        } else {
            System.out.println("La edad debe ser mayor que 0.");
        }
    }

    // Método público para obtener la edad
    public int getEdad() {
        return edad;
    }
}

public class Main {
    public static void main(String[] args) {
        Persona persona = new Persona();
        persona.setNombre("Ana");
        persona.setEdad(30);

        System.out.println("Nombre: " + persona.getNombre()); // Salida: Nombre: Ana
        System.out.println("Edad: " + persona.getEdad()); // Salida: Edad: 30
    }
}
