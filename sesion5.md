<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 5 


**Actividad 5: Ejercicios de bucles**

**Ejercicios - while:**

1. Pedir al usuario que ingrese un número y mostrar su tabla de multiplicar hasta el número 10.

```java
import java.util.Scanner;

public class EjercicioWhile1{
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Ingresa un número: ");
        int numero = scanner.nextInt();
        
        System.out.println("Tabla de multiplicar del " + numero + ":");
        int contador = 1;
        while (contador <= 10) {
            int resultado = numero * contador;
            System.out.println(numero + " x " + contador + " = " + resultado);
            contador++;
        }
        
        scanner.close();
    }
}
```
2. Pedir al usuario que ingrese una cadena de caracteres y contar la cantidad de caracteres que son números.

```java
import java.util.Scanner;

public class EjercicioWhile2 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingresa una cadena de texto: ");
        String cadena = scanner.nextLine();

        int contador = 0;

        while (contador < cadena.length()) {

            for (int i = 0; i < cadena.length(); i++) {
                contador++;

            }
            int total = contador;
            System.out.println("El texto que ingresaste tiene " + total + " caracteres");

        }
        scanner.close();
    }
}
```
**Ejercicios - do while:**

1. Escribe un programa en Java que imprima los números del 1 al 100, pero que se detenga si el usuario introduce un número negativo.

```java
import java.util.Scanner;

public class EjercicioDoWhile1 {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        int num;

        do{
            System.out.print("Escribe un número (o ingresa un número negativo para detener): ");
            num = input.nextInt();

            if(num >=0){
                for(int i = 1; i <= 100; i++){
                    System.out.println(i);
                }
            } else{
                System.out.println("Programa detenido.");

            }
        } while (num >= 0);

        input.close();

    } 
}
```

2. Escribe un programa en Java que pida al usuario un número entero e imprima la tabla de multiplicar de ese número, pero que se detenga si el usuario introduce el número 0.

```java
import java.util.Scanner;

public class EjercicioDoWhile2 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int numero;

        do {
            System.out.print("Ingresa un número (o ingresa 0 para salir): ");
            numero = scanner.nextInt();

            if (numero != 0) {
                System.out.println("Tabla de multiplicar de " + numero + ":");
                for (int i = 1; i <= 10; i++) {
                    System.out.println(numero + " x " + i + " = " + (numero * i));
                }
            } else {
                System.out.println("Programa detenido.");
            }
        } while (numero != 0);
        
        scanner.close();
    }
    
}
```
**Ejercicios - for:**

1. Imprimir los números impares del 1 al 50.

 ```java
 public class EjercicioFor1 {
    public static void main(String[] args) {

    int i;

    for(i = 1; i <= 50; i++){
        if(i % 2 != 0){
            System.out.println(i);
        }
    }

    }
}
 ```
2. Imprimir los números primos del 1 al 100.

```java
public class EjercicioFor2 {
    public static void main(String[] args) {
        System.out.println("Números primos del 1 al 100:");

        for (int numero = 2; numero <= 100; numero++) {
            boolean esPrimo = true;

            for (int i = 2; i <= numero / 2; i++) {
                if (numero % i == 0) {
                    esPrimo = false;
                    break;
                }
            }
            if (esPrimo) {
                System.out.print(numero + " ");
            }
        }
    }
}
```





