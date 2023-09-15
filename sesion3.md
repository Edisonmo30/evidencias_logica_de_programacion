<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 3 


**Actividad 3: Ejercicios de operaciones básicas en Java.**

**1. Suma y multiplicación:** Escribe un programa que solicite al usuario dos números enteros y luego imprima la suma y multiplicación de esos números.

```java
import java.util.Scanner;

public class sumaMultiplicacion {
public static void main(String[] args) {
    Scanner input = new Scanner (System.in);
    
    System.out.print ("ingrese el primer numero: ");
    int a = input.nextInt(); 

    System.out.print ("Ingrese el segundo numero: ");
    int b = input.nextInt();

    int suma = a + b;
    System.out.println ("La suma de los dos numeros ingresado es: " + suma);

    int multiply = a * b;
    System.out.print ("La multiplicación de los dos numeros ingresados es: " + multiply);

    input.close ();
}
}
``` 

**2. Resta y división:** Escribe un programa que tome dos números enteros ingresados por el usuario y calcule la resta y división de esos números.

```java
import java.util.Scanner;

public class RestaDivision {
    public static void main(String[] args) {
        Scanner input = new Scanner (System.in);

        System.out.print ("Ingrese el primer numero: ");
        int a = input.nextInt();

        System.out.print ("Ingrese el segundo numero: ");
        int b = input.nextInt();

        int resta = a - b;
        System.out.println ("La suma de los dos numeros ingresado es: " + resta);

        int division = a / b;
        System.out.print ("La multiplicación de los dos numeros ingresados es: " + division);

        input.close ();
    }
}
```

**3. Operaciones combinadas:** Escribe un programa que solicite al usuario tres números enteros y realice las siguientes operaciones: suma de los tres números, multiplicación del primer número por el segundo y división del resultado entre el tercer número.

```java
import java.util.Scanner;

public class operacionesCombinadas {
    public static void main(String[] args) {
        Scanner input = new Scanner (System.in);

        System.out.print ("Ingrese el primer numero: ");
        int a = input.nextInt();

        System.out.print ("Ingrese el segundo numero: ");
        int b = input.nextInt();

        System.out.print ("Ingrese el tercer numero: " );
        int c = input.nextInt();

        int suma = a + b + c;
        System.out.println ("La suma de los tres numeros ingresado es: " + suma);

        int division = (a * b) / c;
        System.out.print ("La multiplicación de los numeros es: " + division);

        input.close ();
    }
}
```

**4. Operaciones con decimales:** Escribe un programa que solicite al usuario dos números decimales y realice las siguientes operaciones: suma, resta, multiplicación y división.

```java
import java.util.Scanner;

public class OperacionesDecimales {
    public static void main(String[] args) {
        Scanner input = new Scanner (System.in);

        System.out.print ("Ingrese el primer numero decimal: ");
        double a = input.nextDouble();

        System.out.print ("Ingrese el segundo numero decimal: ");
        double b = input.nextDouble();

        double suma = a + b;
        System.out.println ("La suma de los dos numeros ingresado es: " + suma);

        double rest = a - b;
        System.out.println ("La resta de los dos numeros ingresado es: " + rest);

        double multiply = a * b;
        System.out.println ("La multiplicacion de los dos numeros ingresado es: " + multiply);

        double division = (a / b);
        System.out.println ("La division de los dos numeros ingresado es: " + division);

        input.close ();
    }
}
```

**5. Incremento y decremento:** Escribe un programa que declare una variable entera y la inicialice con un valor. Luego, incrementa su valor en 1 y muestra el resultado. Después, decrementa su valor en 1 y muestra el resultado nuevamente.

```java
import java.util.Scanner;

public class IncrementoDecremento {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int numero = 0;
        
        System.out.print ("Ingrese el numero 1 o 2: ");
        int a= input.nextInt();

        if(a == 1){
            numero +=1;
            System.out.print("Incremento: " + numero);
        }

        else {
            numero -=1;
            System.out.print("Decremento: " + numero);
        }
        
        
        input.close();
    }
}
```

**6. Operador de asignación compuesta:** Escribe un programa que declare una variable entera y la inicialice con un valor. Utiliza el operador de asignación compuesta para sumar 5 a la variable y luego mostrar su valor.

```java
import java.util.Scanner;

public class OperadorAsignacionCompuesta {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int a = 30;
        
        System.out.println ("valor inicial: " + a + " + 5");

        a+=5;
        System.out.print ("valor total: " + a);
       
        input.close();
    }
}
```

**7. Operadores lógicos:** Escribe un programa que tome dos valores booleanos ingresados por el usuario y muestre el resultado de las operaciones lógicas AND, OR y NOT entre esos valores.

```java
import java.util.Scanner;

public class OperadoresLogicos {
    public static void main(String[] args) {
        Scanner input = new Scanner (System.in);

        System.out.print ("Ingrese el primer valor booleano: ");
        boolean valor1 = input.nextBoolean();

        System.out.print ("Ingrese el segundo valor booleano: ");
        boolean valor2 = input.nextBoolean();

        boolean operacionAnd = valor1 && valor2;
        System.out.println ("resultado de la operación AND: " + operacionAnd);

        boolean operacionOR = valor1 || valor2;
        System.out.println ("resultado de la operación OR: " + operacionOR);

        boolean operacionNOT1 = !valor1;
        System.out.println ("resultado de la operación NOT para el primer valor: " + operacionNOT1);

        boolean operacionNOT2 = !valor2;
        System.out.println ("resultado de la operación NOT para el primer valor: " + operacionNOT2);


        input.close ();
    }
}
```

**8. Operador ternario:** Escribe un programa que tome un número entero ingresado por el usuario y utilice el operador ternario para determinar si el número es positivo o negativo. Luego, muestra el resultado en la salida.

```java
import java.util.Scanner;

public class operadorTernario {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingresa un numero entero: ");
        int numero = scanner.nextInt();

        String resultado = (numero >= 0) ? "positivo" : "negativo";
        System.out.println("El numero ingresado es: " + resultado);

        scanner.close();
    }
}
```





