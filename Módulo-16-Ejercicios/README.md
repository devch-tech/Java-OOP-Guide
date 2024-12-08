# 50 Ejercicios de Programación Orientada a Objetos en Java

## 🧩 Clases y Objetos
1. Crea una clase `Persona` con atributos como `nombre`, `edad` y un método que imprima los datos.
2. Diseña una clase `Coche` con atributos `marca`, `modelo` y `año`. Crea instancias y muestra sus datos.
3. Implementa una clase `Producto` con un método que calcule el precio con IVA.
4. Define una clase `Rectangulo` que calcule el área y el perímetro.
5. Crea una clase `CuentaBancaria` con métodos para depositar y retirar dinero.

## 🔐 Encapsulamiento
6. Modifica la clase `Persona` para encapsular sus atributos usando métodos `getter` y `setter`.
7. Implementa una clase `Empleado` con atributos privados y métodos para obtener y modificar su salario.
8. Diseña una clase `Libro` que permita cambiar su precio solo si es mayor que cero.
9. Crea una clase `Cuenta` donde solo se pueda retirar dinero si el saldo es suficiente.
10. Protege los datos de una clase `Usuario` con validación en los métodos `setter`.

## 🧬 Herencia
11. Crea una clase base `Animal` y clases hijas `Perro` y `Gato`. Implementa un método `hacerSonido`.
12. Diseña una jerarquía de clases `Vehiculo`, con clases hijas `Coche` y `Moto`.
13. Extiende una clase `Figura` con clases `Circulo` y `Cuadrado` que calculen áreas.
14. Implementa una clase `Empleado` con subclases `Gerente` y `Operador`, cada una con responsabilidades distintas.
15. Diseña una jerarquía de clases para un sistema escolar con clases `Persona`, `Estudiante` y `Profesor`.

## 🎭 Polimorfismo
16. Utiliza el método `hacerSonido` en una lista de objetos `Animal` para mostrar cómo funciona el polimorfismo.
17. Implementa un método `calcularPago` en una clase base `Empleado`, sobrescribiéndolo en subclases.
18. Crea una clase `Figura` con un método `dibujar`, implementado de manera diferente en `Rectangulo` y `Circulo`.
19. Diseña un programa que calcule impuestos para diferentes tipos de productos usando polimorfismo.
20. Crea un sistema de transporte con clases como `Coche`, `Avion` y `Barco`, y un método `mover`.

## 🎨 Abstracción
21. Implementa una clase abstracta `Figura` con métodos abstractos para calcular el área y el perímetro.
22. Diseña un sistema de pagos con una clase abstracta `Pago` y subclases como `Tarjeta` y `Efectivo`.
23. Crea una clase abstracta `Animal` con un método abstracto `comer` y diferentes implementaciones en subclases.
24. Diseña un sistema de vehículos con una clase abstracta `Vehiculo` y métodos específicos en clases hijas.
25. Implementa un programa para simular electrodomésticos con una clase abstracta `Electrodomestico`.

## ⚙️ Interfaces
26. Crea una interfaz `Volable` con un método `volar`, implementado por las clases `Pajaro` y `Avion`.
27. Diseña un sistema de pago con una interfaz `Transaccion` y clases `Tarjeta` y `PayPal`.
28. Implementa una interfaz `Operaciones` con métodos `sumar` y `restar`, usados en una clase `Calculadora`.
29. Define una interfaz `Imprimible` para clases `Documento` y `Foto`.
30. Diseña una interfaz `Alarma` implementada por las clases `Casa` y `Coche`.

## ⚙️ Constructores y Sobrecarga
31. Crea una clase `Persona` con un constructor que acepte diferentes combinaciones de parámetros.
32. Implementa una clase `Coche` con un constructor por defecto y otro con parámetros.
33. Diseña una clase `Libro` con varios constructores para inicializar solo ciertos atributos.
34. Crea una clase `Empleado` con un constructor que permita crear empleados con salario fijo o por hora.
35. Diseña una clase `Pedido` con sobrecarga para inicializar pedidos con uno o varios productos.

## 🔄 Sobrecarga y Sobrescritura
36. Implementa una clase `Calculadora` con métodos sobrecargados para sumar enteros, flotantes y arreglos.
37. Crea una clase base `Vehiculo` con un método `mover` sobrescrito en subclases como `Barco` y `Coche`.
38. Diseña un programa que utilice sobrecarga para inicializar diferentes tipos de cuentas bancarias.
39. Implementa una jerarquía de clases `Figura` con métodos sobrescritos para calcular áreas.
40. Crea una clase `Pago` con métodos sobrecargados para procesar transacciones de diferentes tipos.

## 📝 Métodos y Variables Estáticas
41. Crea una clase `Utilidades` con un método estático `calcularPromedio`.
42. Diseña una clase `Contador` con una variable estática que lleve el registro de objetos creados.
43. Implementa una clase `MathHelper` con métodos estáticos para operaciones matemáticas comunes.
44. Crea una clase `Configuracion` con variables estáticas que representen constantes globales.
45. Diseña una clase `Banco` con un método estático para calcular intereses.

## 📐 Clases Internas y Anónimas
46. Crea una clase `Calculadora` con una clase interna `Operaciones` para realizar cálculos básicos.
47. Diseña una clase `Biblioteca` con una clase interna para gestionar préstamos de libros.
48. Implementa una clase `Evento` con una clase anónima que sobrescriba un método de notificación.
49. Usa una clase anónima para implementar una interfaz `Runnable` y ejecutar un hilo.
50. Diseña una aplicación simple con un botón que tenga un evento manejado por una clase interna.
