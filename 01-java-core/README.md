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

## 🔄 4. Control de Flujo (Control Flow Statements)
Determinan cómo se ejecutan las instrucciones de un programa.  
Por defecto, Java ejecuta el código de arriba hacia abajo, pero mediante estas estructuras podemos alterar el orden de ejecutión según condiciones, repeticiones o bifurcaciones lógicas.

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
Explicación:

El bloque dentro del `if` se ejecuta solo si la condición es verdadera.

Si no se cumple, pasa al siguiente `else if`.

Si ninguna condición es verdadera, se ejecuta el bloque `else`.

💡 En proyectos backend, este tipo de control se usa frecuentemente para validar parámetros, roles o permisos de usuario.
### Bucles
```
for (int i = 0; i < 5; i++) {
    System.out.println("Iteración " + i);
}
```
### Switch (Java moderno)
El `switch` permite evaluar una variable o expresión contra múltiples valores posibles.  
Desde Java 14+, se introdujo una versión más limpia y funcional con la sintaxis de flechas (`->`).

```
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
### Operador ternario (`?:`)
Permite simplificar condiones simples en una sola línea.  
```
int edad = 22;
String mensaje = (edad >= 18) ? "Acceso permitido" : "Acceso denegado";
System.out.println(mensaje);
```