# Proyecto 01 — Errores de compilación en Java

**Requisitos:** JDK 21 y Maven 3.9+.

## Objetivo
Distinguir los errores detectados por el compilador de los que ocurren cuando la aplicación ya se ejecuta.

## Ejecución inicial
```bash
mvn clean compile
java -cp target/classes com.curso.errores.App
```

## Laboratorio: activar un error por vez
El proyecto base compila. Los seis ejemplos defectuosos se guardan como `.java.txt` para evitar que todos los errores impidan compilar simultáneamente.

1. Elige un archivo de `ejemplos-con-error/`.
2. Copia su contenido a `src/main/java/Ejemplo.java`.
3. Ejecuta `mvn clean compile` y observa el mensaje del compilador.
4. Identifica la línea, explica la causa y corrige el código.
5. Ejecuta de nuevo `mvn clean compile` y verifica que ahora compila.
6. Borra `src/main/java/Ejemplo.java` antes del siguiente caso.

> Los ejemplos deben probarse de uno en uno porque todos declaran una clase llamada `Ejemplo`.

## Casos
| Archivo | Fallo | Solución esperada |
|---|---|---|
| 01-Sintaxis | Falta `;` | Agregar punto y coma |
| 02-Tipos | Asignación de String a int | Usar un entero o convertir una cadena numérica |
| 03-Variable | Símbolo no definido | Declarar `saldo` antes de usarlo |
| 04-Metodo | Método inexistente | Definir `imprimirSaldo(int)` |
| 05-Retorno | Método `int` sin `return` | Devolver `a + b` |
| 06-CheckedException | `IOException` no capturada ni declarada | Agregar `throws IOException` o `try/catch` |

## Preguntas para discutir
1. ¿En qué fase se detecta cada error?
2. ¿Se llega a ejecutar `main` cuando falla `mvn compile`?
3. ¿Todos los errores de compilación son errores de sintaxis?
4. ¿Por qué una excepción verificada puede producir un error de compilación?

## Reto
Crea un séptimo ejemplo que produzca un error de compilación por acceder a un atributo privado desde otra clase. Muestra el error y corrígelo usando un método público.

**Nota docente:** el caso 06 anticipa el tema de excepciones verificadas; no es un fallo de ejecución sino un incumplimiento de una obligación del compilador.
