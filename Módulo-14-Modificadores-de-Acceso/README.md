# Módulo 14: Modificadores de Acceso

## Conclusión
Los modificadores de acceso son herramientas fundamentales en la programación orientada a objetos que permiten controlar el acceso a los miembros de una clase (atributos y métodos). Al usar modificadores de acceso, los desarrolladores pueden proteger los datos y garantizar que solo las partes del código que deben tener acceso a esos datos puedan hacerlo. Esto ayuda a mantener la integridad del programa y a evitar errores.

## ¿Qué son los Modificadores de Acceso?
Los modificadores de acceso son palabras clave en Java que determinan la visibilidad y el nivel de acceso a las clases, atributos y métodos. Hay cuatro modificadores de acceso principales en Java:

### 1. **public**
Cuando un atributo o método es declarado como `public`, se puede acceder a él desde cualquier otra clase en el mismo paquete o en diferentes paquetes. Esto significa que no hay restricciones sobre el acceso a ese miembro.

**Ejemplo de la Vida Real:** Una cuenta bancaria pública donde cualquiera puede ver el saldo.

### 2. **private**
El modificador `private` restringe el acceso al miembro solo a la propia clase. Esto significa que no se puede acceder a este atributo o método desde fuera de la clase donde se declara.

**Ejemplo de la Vida Real:** Una cuenta de correo electrónico donde solo el propietario puede acceder a la bandeja de entrada.

### 3. **protected**
Los miembros declarados como `protected` pueden ser accedidos por la propia clase, por clases en el mismo paquete y por subclases, incluso si están en paquetes diferentes. Este modificador es útil para la herencia.

**Ejemplo de la Vida Real:** Un área de acceso restringido en una empresa donde solo los empleados de un departamento específico y sus superiores pueden entrar.

### 4. **default (package-private)**
Si no se especifica ningún modificador de acceso, se aplica el modificador por defecto, que es conocido como "package-private". Esto significa que los miembros son accesibles solo dentro de su propio paquete y no se puede acceder a ellos desde clases de otros paquetes.

**Ejemplo de la Vida Real:** Un club donde solo los miembros del mismo club pueden asistir a ciertas reuniones.

## Importancia de los Modificadores de Acceso
El uso adecuado de los modificadores de acceso es crucial por varias razones:

- **Encapsulamiento:** Permite ocultar los detalles internos de la implementación de una clase, lo que facilita la modificación del código sin afectar a otras partes del sistema.
- **Seguridad:** Restringir el acceso a los datos sensibles evita que sean alterados accidentalmente por otras partes del código.
- **Mantenimiento:** Hace que el código sea más fácil de entender y mantener al establecer límites claros sobre qué partes del código pueden interactuar entre sí.

## Ejemplo de Código
A continuación, se presenta un ejemplo que ilustra cómo se utilizan los modificadores de acceso en Java.

### Código
```java
class CuentaBancaria {
    // Atributo privado
    private double saldo;

    // Constructor
    public CuentaBancaria(double saldoInicial) {
        this.saldo = saldoInicial;
    }

    // Método público para acceder al saldo
    public double obtenerSaldo() {
        return saldo;
    }

    // Método público para depositar dinero
    public void depositar(double cantidad) {
        if (cantidad > 0) {
            saldo += cantidad;
        }
    }

    // Método protegido para permitir acceso en subclases
    protected void mostrarInformacion() {
        System.out.println("Saldo actual: " + saldo);
    }
}

class CuentaAhorro extends CuentaBancaria {
    private double interes;

    public CuentaAhorro(double saldoInicial, double interes) {
        super(saldoInicial);
        this.interes = interes;
    }

    public void aplicarInteres() {
        double nuevoSaldo = obtenerSaldo() + (obtenerSaldo() * interes / 100);
        depositar(nuevoSaldo - obtenerSaldo());
    }

    // Sobreescribimos el método protegido
    @Override
    protected void mostrarInformacion() {
        super.mostrarInformacion();
        System.out.println("Tasa de interés: " + interes + "%");
    }
}

public class Main {
    public static void main(String[] args) {
        CuentaBancaria cuenta = new CuentaBancaria(1000);
        cuenta.depositar(500);
        System.out.println("Saldo: " + cuenta.obtenerSaldo());

        CuentaAhorro cuentaAhorro = new CuentaAhorro(1000, 5);
        cuentaAhorro.aplicarInteres();
        cuentaAhorro.mostrarInformacion();
    }
}

