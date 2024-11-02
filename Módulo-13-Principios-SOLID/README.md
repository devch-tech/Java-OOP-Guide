# Módulo 13: Principios SOLID

## Conclusión
Los principios SOLID son un conjunto de directrices que facilitan la creación de software más mantenible, flexible y escalable. Al seguir estos principios, los desarrolladores pueden construir sistemas que son más fáciles de entender y modificar, lo que a su vez reduce los errores y mejora la calidad del código. Aplicar estos principios puede ser un gran paso hacia el dominio de la programación orientada a objetos.

## ¿Qué son los Principios SOLID?
SOLID es un acrónimo que representa cinco principios fundamentales de diseño de software. Estos principios ayudan a los desarrolladores a crear sistemas que son más fáciles de gestionar a largo plazo. A continuación, explicamos cada uno de estos principios:

### 1. **Single Responsibility Principle (SRP)** - Principio de Responsabilidad Única
Este principio establece que una clase debe tener una sola razón para cambiar. En otras palabras, cada clase debe encargarse de una sola funcionalidad o responsabilidad. Si una clase tiene múltiples responsabilidades, se vuelve difícil de mantener.

**Ejemplo de la Vida Real:** Imagina un coche. Debe tener una responsabilidad clara: transportarte. Si comenzaras a usarlo para también cocinar, sería confuso y complicado.

### 2. **Open/Closed Principle (OCP)** - Principio de Abierto/Cerrado
Este principio indica que las clases deben estar abiertas para la extensión, pero cerradas para la modificación. Esto significa que se puede agregar nueva funcionalidad a una clase sin modificar el código existente.

**Ejemplo de la Vida Real:** Imagina una tienda de ropa que desea agregar una nueva línea de productos. En lugar de modificar la clase existente de productos, puedes crear una nueva clase para la nueva línea, manteniendo la clase original intacta.

### 3. **Liskov Substitution Principle (LSP)** - Principio de Sustitución de Liskov
Este principio establece que los objetos de una clase base deben poder ser reemplazados por objetos de una clase derivada sin alterar las propiedades del programa. Las subclases deben ser completamente intercambiables con sus superclases.

**Ejemplo de la Vida Real:** Si tienes una clase `Ave`, y creas una subclase `Pájaro`, puedes esperar que cualquier instancia de `Pájaro` funcione donde se espere una instancia de `Ave`.

### 4. **Interface Segregation Principle (ISP)** - Principio de Segregación de Interfaces
Este principio sugiere que es mejor tener muchas interfaces específicas en lugar de una interfaz general. Las clases no deben ser forzadas a depender de métodos que no utilizan.

**Ejemplo de la Vida Real:** En lugar de tener un dispositivo que imprime y escanea, es mejor tener dos dispositivos: uno para imprimir y otro para escanear. Esto permite que cada dispositivo cumpla con su función específica sin depender de características que no usa.

### 5. **Dependency Inversion Principle (DIP)** - Principio de Inversión de Dependencias
Este principio establece que las clases de alto nivel no deben depender de las clases de bajo nivel. Ambos deben depender de abstracciones (interfaces). Esto promueve un diseño más desacoplado y flexible.

**Ejemplo de la Vida Real:** Imagina un coche (alto nivel) que depende de un motor (bajo nivel). Si decides cambiar el motor, deberías poder hacerlo sin tener que modificar la clase del coche.

## Ejemplo de Código
A continuación, se presenta un ejemplo que ilustra los principios SOLID en acción.

### Código
```java
// Principio de Responsabilidad Única (SRP)
class Reporte {
    public void generarReporte() {
        // Generar reporte
    }
}

class EnviarCorreo {
    public void enviarReporte() {
        // Enviar reporte por correo
    }
}

// Principio de Abierto/Cerrado (OCP)
interface Producto {
    void mostrarDetalles();
}

class Ropa implements Producto {
    @Override
    public void mostrarDetalles() {
        System.out.println("Detalles de la ropa");
    }
}

class Electronico implements Producto {
    @Override
    public void mostrarDetalles() {
        System.out.println("Detalles del electrónico");
    }
}

// Principio de Sustitución de Liskov (LSP)
class Ave {
    public void volar() {
        System.out.println("El ave vuela");
    }
}

class Pájaro extends Ave {
    // Pájaro hereda Ave
}

// Principio de Segregación de Interfaces (ISP)
interface Impresora {
    void imprimir();
}

interface Escaner {
    void escanear();
}

class ImpresoraSimple implements Impresora {
    @Override
    public void imprimir() {
        System.out.println("Imprimiendo...");
    }
}

class EscanerSimple implements Escaner {
    @Override
    public void escanear() {
        System.out.println("Escaneando...");
    }
}

// Principio de Inversión de Dependencias (DIP)
interface Motor {
    void encender();
}

class MotorElectrico implements Motor {
    @Override
    public void encender() {
        System.out.println("Motor eléctrico encendido");
    }
}

class Coche {
    private Motor motor;

    public Coche(Motor motor) {
        this.motor = motor;
    }

    public void arrancar() {
        motor.encender();
    }
}

// Clase principal
public class Main {
    public static void main(String[] args) {
        // Usando SRP
        Reporte reporte = new Reporte();
        reporte.generarReporte();
        EnviarCorreo enviarCorreo = new EnviarCorreo();
        enviarCorreo.enviarReporte();

        // Usando OCP
        Producto ropa = new Ropa();
        ropa.mostrarDetalles();
        Producto electronico = new Electronico();
        electronico.mostrarDetalles();

        // Usando LSP
        Ave ave = new Pájaro();
        ave.volar();

        // Usando ISP
        Impresora impresora = new ImpresoraSimple();
        impresora.imprimir();
        Escaner escaner = new EscanerSimple();
        escaner.escanear();

        // Usando DIP
        Motor motor = new MotorElectrico();
        Coche coche = new Coche(motor);
        coche.arrancar();
    }
}
