# Módulo 05: Polimorfismo

## Conclusión
El polimorfismo es una herramienta poderosa en la programación que permite crear aplicaciones más flexibles y fáciles de mantener. Facilita la creación de nuevas funcionalidades sin necesidad de alterar el código existente, lo que es esencial para el desarrollo de software ágil y eficiente.

## ¿Qué es el Polimorfismo?
El polimorfismo es un concepto fundamental en la Programación Orientada a Objetos (POO) que permite a los objetos de diferentes clases ser tratados como objetos de una clase común. En otras palabras, el polimorfismo permite que un mismo método actúe de diferentes maneras según el objeto que lo invoque. Esto se logra a través de la herencia y la sobrescritura de métodos.

### Tipos de Polimorfismo
1. **Polimorfismo en Tiempo de Compilación (o estático):** Este tipo se logra mediante la sobrecarga de métodos. La sobrecarga ocurre cuando dos o más métodos en la misma clase tienen el mismo nombre pero diferentes parámetros (número o tipo).

2. **Polimorfismo en Tiempo de Ejecución (o dinámico):** Este tipo se obtiene mediante la sobrescritura de métodos. Aquí, una subclase proporciona su propia implementación de un método que ya existe en su superclase.

## Ejemplos de la Vida Real
Imagina que tienes una aplicación de transporte. En esta aplicación, hay diferentes tipos de vehículos: `Coche`, `Bicicleta` y `Camión`. Todos estos vehículos pueden tener un método `mover()`, pero cada tipo de vehículo se moverá de manera diferente.

- **Coche:** Se mueve rápido por la carretera.
- **Bicicleta:** Se mueve de manera más lenta y puede ir por caminos más angostos.
- **Camión:** Se mueve lentamente y puede llevar carga pesada.

Aunque todos estos vehículos pueden ser tratados como "vehículos" y pueden invocar el método `mover()`, cada uno implementará su propia lógica de movimiento.

## Importancia del Polimorfismo
El polimorfismo es crucial en la programación porque:
- **Facilita la Extensibilidad:** Puedes agregar nuevas clases sin modificar el código existente. Por ejemplo, si agregas una nueva clase `Motocicleta`, solo necesitas implementar el método `mover()`.
- **Mejora la Mantenibilidad:** Reduce la necesidad de duplicar código y permite que el sistema se adapte a cambios futuros.

## Explicación del Código
A continuación, se presenta un ejemplo de polimorfismo en Java:

1. **Clase Base `Vehiculo`:** Esta es la superclase que define un método común `mover()` que puede ser sobrescrito por las subclases.
2. **Clases Hijas (`Coche`, `Bicicleta`, `Camion`):** Cada clase hija proporciona su propia implementación del método `mover()`, mostrando cómo se comporta cada tipo de vehículo de manera única.
3. **Clase Principal `Main`:** Aquí se crea un objeto de tipo `Vehiculo` que puede referirse a cualquier subclase. Dependiendo del tipo de objeto asignado, el método `mover()` invoca la implementación correspondiente de la subclase, lo que demuestra el comportamiento del polimorfismo.

### Ejemplo de Código
```java
// Clase Base
class Vehiculo {
    void mover() {
        System.out.println("El vehículo se mueve.");
    }
}

// Clase Hija: Coche
class Coche extends Vehiculo {
    @Override
    void mover() {
        System.out.println("El coche se mueve rápido por la carretera.");
    }
}

// Clase Hija: Bicicleta
class Bicicleta extends Vehiculo {
    @Override
    void mover() {
        System.out.println("La bicicleta se mueve a una velocidad moderada.");
    }
}

// Clase Hija: Camión
class Camion extends Vehiculo {
    @Override
    void mover() {
        System.out.println("El camión se mueve lentamente con carga pesada.");
    }
}

// Clase Principal
public class Main {
    public static void main(String[] args) {
        Vehiculo miVehiculo;

        miVehiculo = new Coche();
        miVehiculo.mover(); // Salida: El coche se mueve rápido por la carretera.

        miVehiculo = new Bicicleta();
        miVehiculo.mover(); // Salida: La bicicleta se mueve a una velocidad moderada.

        miVehiculo = new Camion();
        miVehiculo.mover(); // Salida: El camión se mueve lentamente con carga pesada.
    }
}
