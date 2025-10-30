# 🧠 Java Core — Fundamentos Profesionales

## 🎯 Objetivo de la sección
Comprender los pilares técnicos del lenguaje Java moderno (Java 17+), sentando una base sólida para desarrollar software backend robusto, escalable y mantenible.

Esta sección busca que domines los **conceptos esenciales de la plataforma Java SE**, su sintaxis, el paradigma orientado a objetos y las APIs clave del lenguaje.

---

## 🧩 1. Introducción al Ecosistema Java

### 🔹 ¿Qué es Java?
Java es un lenguaje de programación **orientado a objetos**, **compilado e interpretado**, **portable** (gracias a la JVM) y **altamente utilizado en entornos corporativos**.  
Su filosofía central es el principio **“Write Once, Run Anywhere” (WORA)**.

### 🔹 Componentes Clave
| Componente | Descripción |
|-------------|-------------|
| **JDK (Java Development Kit)** | Incluye compilador (`javac`), librerías y herramientas de desarrollo. |
| **JRE (Java Runtime Environment)** | Permite ejecutar programas Java (sin compilar). |
| **JVM (Java Virtual Machine)** | Máquina virtual que interpreta bytecode y lo ejecuta. |

---

## ⚙️ 2. Estructura de un Programa Java

```java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("¡Hola, mundo corporativo!");
    }
}
```
### Explicación:
(`class`) → define una clase (la unidad básica del código en Java).  
(`main`) → método de entrada del programa.  
(`System.out.println`) → imprime texto en la consola.

### Compilación y ejecución manual:
```
javac HolaMundo.java
java HolaMundo
```

## 🧠 3. Tipos de Datos y Variables  
Java es un lenguaje **fuertemente tipado**, lo que significa que cada variable debe declararse con un tipo específico.

---
### 🔹 Tipos Primitivos
| Tipo      | Tamaño  | Ejemplo                            |
| --------- | ------- | ---------------------------------- |
| `byte`    | 8 bits  | `byte edad = 25;`                  |
| `short`   | 16 bits | `short stock = 500;`               |
| `int`     | 32 bits | `int precio = 1999;`               |
| `long`    | 64 bits | `long poblacion = 8_000_000_000L;` |
| `float`   | 32 bits | `float nota = 9.5f;`               |
| `double`  | 64 bits | `double salario = 1200.50;`        |
| `boolean` | 1 bit   | `boolean activo = true;`           |
| `char`    | 16 bits | `char inicial = 'R';`              |

### 🔹 Tipos por referencia
String, arrays, clases, interfaces
Ejemplo:
```
String nombre = "Antonio";
int[] numeros = {1, 2, 3, 4};
```
---
## 🔄 4. Control de Flujo (Control Flow Statements)
Determinan cómo se ejecutan las instrucciones de un programa.  
Por defecto, Java ejecuta el código de arriba hacia abajo, pero mediante estas estructuras podemos alterar el orden de ejecutión según condiciones, repeticiones o bifurcaciones lógicas.
---
### Condicionales
Permiten ejecutar diferentes bloques de código dependiendo del resultado de una condición lógica (`true` o `false`).  
🔹 if, else if, else  
Estructura básica de decisión.
```
if (edad >= 18) {
    System.out.println("Eres mayor de edad");
} else {
    System.out.println("Eres menor de edad");
}
```
#### Explicación:

El bloque dentro del `if` se ejecuta solo si la condición es verdadera.

Si no se cumple, pasa al siguiente `else if`.

Si ninguna condición es verdadera, se ejecuta el bloque `else`.

💡 En proyectos backend, este tipo de control se usa frecuentemente para validar parámetros, roles o permisos de usuario.

---
### Bucles (Loops)
Los bucles permiten ejecutar un bloque de código múltiples veces, mientras se cumpla una condición determinada.
##### `for` clásico
```java
for (int i = 0; i < 5; i++) {
    System.out.println("Iteración " + i);
}
```
##### Explicación:
1. `int i = 0` → inicialización.  
2. `i < 5` → condición que controla el bucle.  
3. `i++` → incremento en cada iteración.

|| Muy usado para iterar índices de arrays o colecciones con tamaño conocido.
---
##### `while`
```java
int contador = 0;
while (contador < 3) {
    System.out.println("Contador: " + contador);
    contador++;
}
```
##### Explicación:
El bloque se ejecuta mientras la condición sea verdadera.  
Si es falsa desde el inicio, no se ejecuta nunca.  
|| Ideal cuando no sabes cuántas veces se repetirá el bucle.
---
##### `do-while`
```java
int numero = 1;
do {
    System.out.println("Número: " + numero);
    numero++;
} while (numero <= 3);
```
##### Explicación:
Ejecuta el bloque al menos una vez, y luego evalúa la condición.  
Útil para menús interactivos o validaciones que deben ocurrir al menos una vez.
---
#### `for-each` (Enhanced for loop)
```java
List<String> nombres = List.of("Ricky", "Ana", "Carlos");

for (String nombre : nombres) {
    System.out.println("Empleado: " + nombre);
}
```
##### Explicación:
Recorre cada elemento de una colección o array sin necesidad de manejar índices.  
Perfecto para iterar listas, conjuntos o resultados de base de datos.
---
### Switch (Java moderno)
El `switch` permite evaluar una variable o expresión contra múltiples valores posibles.  
Desde Java 14+, se introdujo una versión más limpia y funcional con la sintaxis de flechas (`->`).

```java
String dia = "LUNES";
switch (dia) {
    case "LUNES" -> System.out.println("Inicio de semana");
    case "VIERNES" -> System.out.println("Casi fin de semana");
    default -> System.out.println("Día intermedio");
}
```
#### Ventajas de la nueva sintaxis:
- No requiere `break`.
- Evita errores por caídas accidentales (“fall-through”).
- Más expresiva y legible.

💼 En backend, el `switch` se usa comúnmente para mapear estados, tipos de solicitud, o niveles de prioridad.

---
### Operador ternario (`?:`)
Permite simplificar condiones simples en una sola línea.  
```java
int edad = 22;
String mensaje = (edad >= 18) ? "Acceso permitido" : "Acceso denegado";
System.out.println(mensaje);
```
---
### 🧱 5. Programación Orientada a Objetos (OOP)
### 🧩 ¿Qué es la Programación Orientada a Objetos? 

La POO es un paradigma de programación que organiza el software en “objetos”, los cuales combinan datos (atributos) y comportamientos (métodos) en una misma unidad lógica.  
En términos corporativos, la POO se utiliza para modelar entidades del dominio de negocio.  
Por ejemplo, en una empresa: Empleado, Cliente, Factura o Pedido son clases que representan objetos del mundo real.  
Java implementa los 4 pilares fundamentales de la POO: 

| Pilar             | Descripción                                   | Ejemplo                               |
| ----------------- | --------------------------------------------- | ------------------------------------- |
| **Encapsulación** | Ocultar detalles internos de una clase.       | Campos `private` y métodos `get/set`. |
| **Herencia**      | Reutilizar código de otra clase.              | `class Empleado extends Persona`      |
| **Polimorfismo**  | Mismo método, comportamiento diferente.       | Sobreescritura (`@Override`).         |
| **Abstracción**   | Definir lo esencial sin implementar detalles. | Clases abstractas o interfaces.       |

---
### Clases y objetos
Una clase es una plantilla que define las características y comportamientos de un objeto.  
Un objeto es una instancia concreta de esa clase.

#### Ejemplo:
```java
public class Empleado {
    // Atributos (estado)
    private String nombre;
    private double salario;

    // Constructor
    public Empleado(String nombre, double salario) {
        this.nombre = nombre;
        this.salario = salario;
    }

    // Métodos (comportamiento)
    public String getNombre() {
        return nombre;
    }

    public double getSalario() {
        return salario;
    }

    public void aumentarSalario(double cantidad) {
        this.salario += cantidad;
    }

    @Override
    public String toString() {
        return nombre + " - " + salario + " €";
    }
}
```
#### Uso de la clase:
```java
public class Empresa {
    public static void main(String[] args) {
        Empleado empleado = new Empleado("Ricky", 2500);
        empleado.aumentarSalario(300);
        System.out.println(empleado);
    }
}
```
#### Explicación:
- La clase `Empleado` encapsula atributos y métodos relacionados. Por tanto son atributos privados.
- Los métodos públicos controlan el acceso y la modificación de los datos.
- `toString()` sobrescribe el comportamiento por defecto del objeto al imprimirlo.
---
### Encapsulación
La encapsulación protege los datos internos de una clase, exponiendo solo lo necesario a través de métodos públicos.  
En entornos empresariales, esto garantiza la integridad de los datos y evita modificaciones no controladas.  
Por ejemplo, evita salarios negativos o estados inválidos.
```java
public class CuentaBancaria {
    private double saldo;

    public CuentaBancaria(double saldoInicial) {
        this.saldo = saldoInicial;
    }

    public void depositar(double cantidad) {
        if (cantidad > 0) {
            saldo += cantidad;
        }
    }

    public double getSaldo() {
        return saldo;
    }
}
```

💡 Siempre marca los atributos como `private` y ofrece métodos públicos controlados (`getters` y `setters`).  

---
### Herencia
La herencia permite que una clase hija herede atributos y métodos de una clase padre, evitando duplicación de código y fomentando la reutilización.

```java
public class Empleado {
    protected String nombre;
    protected double salario;

    public Empleado(String nombre, double salario) {
        this.nombre = nombre;
        this.salario = salario;
    }

    public double calcularSueldo() {
        return salario;
    }
}

public class Desarrollador extends Empleado {
    private String lenguaje;

    public Desarrollador(String nombre, double salario, String lenguaje) {
        super(nombre, salario); // Llama al constructor de Empleado
        this.lenguaje = lenguaje;
    }

    @Override
    public double calcularSueldo() {
        return super.calcularSueldo() + 500; // Bono técnico
    }
}
```
```java
public class Empresa {
    public static void main(String[] args) {
        Desarrollador dev = new Desarrollador("Ricky", 2500, "Java");
        System.out.println(dev.nombre + " gana " + dev.calcularSueldo() + " €");
    }
}
```
⚙️ `super()` permite acceder a los miembros de la clase padre.  
🔁 `@Override` indica que estamos modificando un método heredado.
---

### Polimorfismo
El polimorfismo permite que distintas clases hijas respondan de forma diferente al mismo método.  
Esto se utiliza ampliamente en backend para tratar diferentes tipos de objetos de manera uniforme (por ejemplo, distintos tipos de usuarios, pagos o notificaciones).
```java
public abstract class Empleado {
    protected String nombre;

    public Empleado(String nombre) {
        this.nombre = nombre;
    }

    public abstract double calcularSueldo();
}

public class Desarrollador extends Empleado {
    private double salarioBase;

    public Desarrollador(String nombre, double salarioBase) {
        super(nombre);
        this.salarioBase = salarioBase;
    }

    @Override
    public double calcularSueldo() {
        return salarioBase + 500;
    }
}

public class Gerente extends Empleado {
    private double salarioBase;

    public Gerente(String nombre, double salarioBase) {
        super(nombre);
        this.salarioBase = salarioBase;
    }

    @Override
    public double calcularSueldo() {
        return salarioBase + 1000; // Bono de liderazgo
    }
}
```
##### Uso:
```java
import java.util.List;

public class Empresa {
    public static void main(String[] args) {
        List<Empleado> empleados = List.of(
            new Desarrollador("Ricky", 2500),
            new Gerente("Ana", 3000)
        );

        for (Empleado e : empleados) {
            System.out.println(e.nombre + " cobra " + e.calcularSueldo() + " €");
        }
    }
}
```
#### Explicación:
- Aunque ambos objetos son `Empleado`, el método `calcularSueldo()` se comporta de manera diferente según la clase real.
- Esto es polimorfismo dinámico (en tiempo de ejecuación).
---

### Abstracción
La abstracción consiste en definir lo esencial sin exponer detalles concretos.  
Se logra mediante clases abstractas o interfaces.
#### Clase abstracta
Son clases que no pueden instanciarse directamente y que definen comportamientos comunes.
```java
public abstract class Figura {
    public abstract double calcularArea();
}
```
#### Interfaces
Definen contratos (qué debe hacer una clase), sin especificar cómo.
```java
public interface Autenticable {
    boolean autenticar(String usuario, String password);
}

public class Usuario implements Autenticable {
    @Override
    public boolean autenticar(String usuario, String password) {
        return "admin".equals(usuario) && "1234".equals(password);
    }
}
```

💼 En el mundo backend, las interfaces se usan extensivamente para definir servicios (ej. `UserService`, `Repository`, `PaymentGateway`), y luego se implementan según la capa de negocio.

---
### Buenas prácticas OOP en Java

| Práctica                                  | Descripción                                                                  |
| ----------------------------------------- | ---------------------------------------------------------------------------- |
| **Encapsula todo**                        | Evita exponer atributos públicos.                                            |
| **Usa constructores claros**              | Inicializa siempre los objetos de forma consistente.                         |
| **Aplica composición antes que herencia** | Favorece flexibilidad y bajo acoplamiento.                                   |
| **Divide responsabilidades**              | Una clase debe tener un único propósito (*Single Responsibility Principle*). |
| **Documenta clases y métodos públicos**   | Mejora la mantenibilidad del código.                                         |
---
### 💼 Ejercicios prácticos
Implementa un pequeño sistema de empleados:
1. Define una clase abstracta Empleado con los atributos nombre y salarioBase.
2. Crea dos clases hijas: Desarrollador y Gerente, que sobrescriban el método calcularSueldo().
3. Añade una interfaz Bonificable con un método double calcularBono().
4. Implementa esa interfaz en ambas clases.
5. Usa una lista de Empleado en Empresa.java para imprimir el salario total de cada empleado (base + bono).
---

### 📚 Recursos Adicionales
