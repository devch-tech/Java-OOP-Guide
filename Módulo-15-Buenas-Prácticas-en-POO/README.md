# Módulo 15: Buenas Prácticas en Programación Orientada a Objetos

## Conclusión
Adoptar buenas prácticas en programación orientada a objetos es crucial para crear aplicaciones que sean mantenibles, escalables y fáciles de entender. Siguiendo estas prácticas, los desarrolladores pueden mejorar la calidad de su código y facilitar la colaboración en equipo.

## ¿Qué son las Buenas Prácticas en POO?
Las buenas prácticas en programación orientada a objetos (POO) son recomendaciones y principios que ayudan a los desarrolladores a escribir código más claro y efectivo. Estas prácticas abarcan desde el diseño de clases hasta la organización del código.

## Principales Buenas Prácticas en POO

### 1. **Sigue el Principio DRY (Don't Repeat Yourself)**
Evita la duplicación de código. Si necesitas usar el mismo código en diferentes lugares, considera crear un método o clase reutilizable. Esto reduce errores y facilita el mantenimiento.

**Ejemplo de la Vida Real:** Imagina un sistema de reservas de vuelos. En lugar de escribir el mismo código para calcular el precio de los vuelos en diferentes clases, crea una clase de "CalculadorDePrecios".

### 2. **Usa Nombres Significativos**
Elige nombres descriptivos para clases, métodos y variables. Un buen nombre debe comunicar claramente su propósito.

**Ejemplo de la Vida Real:** Si tienes una clase que representa un "Cliente", no la llames `C` o `X`. Usa `Cliente` o `ClienteVIP` si es un cliente especial.

### 3. **Aplica el Principio de Responsabilidad Única (SRP)**
Cada clase debe tener una única responsabilidad. Esto hace que el código sea más fácil de entender y de probar.

**Ejemplo de la Vida Real:** Si tienes una clase que gestiona la base de datos y también envía correos electrónicos, divídelas en dos clases: `GestorDeBaseDeDatos` y `ServicioDeEmail`.

### 4. **Utiliza Encapsulamiento**
Protege los datos de tus clases utilizando modificadores de acceso. Mantén los atributos como `private` y proporciona métodos `public` para acceder y modificar esos atributos.

**Ejemplo de la Vida Real:** En una aplicación de redes sociales, los perfiles de usuario deben tener información privada, como la dirección de correo electrónico, accesible solo a través de métodos específicos.

### 5. **Preferencia por la Composición sobre la Herencia**
Cuando sea posible, utiliza la composición en lugar de la herencia. Esto significa que en lugar de crear una jerarquía de clases, combina diferentes objetos para lograr el comportamiento deseado.

**Ejemplo de la Vida Real:** En lugar de tener una clase `Vehículo` que hereda de `Coche` y `Motocicleta`, puedes tener una clase `Vehículo` que contenga un objeto de tipo `Motor`, y los diferentes vehículos pueden usar este motor.

### 6. **Documenta tu Código**
Incluye comentarios y documentación para explicar el propósito de las clases y los métodos. Esto ayudará a otros desarrolladores (y a ti mismo en el futuro) a comprender tu código.

**Ejemplo de la Vida Real:** Al igual que las instrucciones de uso de un dispositivo, tu código debe tener comentarios que expliquen su funcionamiento.

### 7. **Escribe Pruebas Unitarias**
Las pruebas unitarias ayudan a asegurar que cada parte del código funcione correctamente. Esto es especialmente importante en POO, donde las interacciones entre objetos pueden ser complejas.

**Ejemplo de la Vida Real:** Si estás desarrollando una aplicación de gestión de inventarios, asegúrate de probar cada método para agregar, eliminar y buscar productos.

## Ejemplo de Código
A continuación, se presenta un ejemplo que ilustra algunas de estas buenas prácticas en POO.

### Código
```java
class Cliente {
    private String nombre;
    private String email;

    public Cliente(String nombre, String email) {
        this.nombre = nombre;
        this.email = email;
    }

    public String getNombre() {
        return nombre;
    }

    public String getEmail() {
        return email;
    }

    public void enviarEmail(String mensaje) {
        // Lógica para enviar un correo electrónico al cliente
        System.out.println("Enviando a " + email + ": " + mensaje);
    }
}

class GestorDeClientes {
    private List<Cliente> clientes;

    public GestorDeClientes() {
        clientes = new ArrayList<>();
    }

    public void agregarCliente(Cliente cliente) {
        clientes.add(cliente);
    }

    public void notificarClientes(String mensaje) {
        for (Cliente cliente : clientes) {
            cliente.enviarEmail(mensaje);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        GestorDeClientes gestor = new GestorDeClientes();
        Cliente cliente1 = new Cliente("Juan Pérez", "juan@example.com");
        Cliente cliente2 = new Cliente("Ana Gómez", "ana@example.com");

        gestor.agregarCliente(cliente1);
        gestor.agregarCliente(cliente2);

        gestor.notificarClientes("¡Bienvenido a nuestra tienda!");
    }
}

