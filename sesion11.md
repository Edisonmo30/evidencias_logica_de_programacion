<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 11 


**Actividad 11: Ejercicios de Lógica de Programación**

Dado un conjunto de números enteros, se debe determinar si existe un número que aparezca más de una vez. Si existe, se debe imprimir su valor.

### Ejercicio 1

```java
public class Ejercicio1 {

    public static void main(String[] args) {
        // Declaramos un conjunto de números enteros
        int[] numeros = {1, 2, 3, 4, 5, 2};

        // Creamos una variable para almacenar el número que aparece más de una vez
        int numeroRepetido = 0;

        // Recorremos el conjunto de números
        for (int i = 0; i < numeros.length; i++) {
            // Comprobamos si el número actual ya ha aparecido
            for (int j = 0; j < i; j++) {
                if (numeros[i] == numeros[j]) {
                    // El número actual ya ha aparecido
                    numeroRepetido = numeros[i];
                    break;
                }
            }
        }

        // Si el número repetido es distinto de 0, lo imprimimos
        if (numeroRepetido != 0) {
            System.out.println("El número repetido es: " + numeroRepetido);
        } else {
            // No hay ningún número repetido
            System.out.println("No hay ningún número repetido");
        }
    }
}
```

### Ejercicio 2

Conversión de decimal a binario. La conversión de decimal a binario es el proceso de convertir un número decimal a su representación binaria. El sistema binario es un sistema de numeración basado en dos dígitos, 0 y 1.

**Utilizando bucle while**

```java
public class Ejercicio2 {

    public static void main(String[] args) {
        // Declaramos la variable para almacenar el número decimal
        int numeroDecimal = 10;

        // Declaramos la variable para almacenar el resultado
        String numeroBinario = "";

        // Inicializamos el bucle
        int i = 0;
        while (numeroDecimal > 0) {

            // Calculamos el resto de la división
            int resto = numeroDecimal % 2;

            // Añadimos el resto a la cadena
            numeroBinario = resto + numeroBinario;

            // Dividimos el número decimal por 2
            numeroDecimal = numeroDecimal / 2;

            // Incrementamos el índice del bucle
            i++;
        }

        // Imprimimos el resultado
        System.out.println("El número binario es: " + numeroBinario);
    }
}
```

**Utilizando bucle for**

```java
public class Ejercicio2 {

    public static void main(String[] args) {
        // Declaramos la variable para almacenar el número decimal
        int numeroDecimal = 10;

        // Declaramos la variable para almacenar el resultado
        String numeroBinario = "";

        // Inicializamos el bucle
        for (int i = numeroDecimal; i > 0; i /= 2) {

            // Calculamos el resto de la división
            int resto = i % 2;

            // Añadimos el resto a la cadena
            numeroBinario = resto + numeroBinario;
        }

        // Imprimimos el resultado
        System.out.println("El número binario es: " + numeroBinario);
    }
}
```

Este algoritmo funciona dividiendo el número decimal por 2 repetidamente. Cada vez que se divide el número, el resto se almacena en la cadena. El proceso se repite hasta que el número decimal es 0.

Por ejemplo, para convertir el número decimal 10 a binario, el algoritmo funcionaría de la siguiente manera:

```git
Iteración 1:

numeroDecimal = 10
resto = 10 % 2 = 0
numeroBinario = 0

Iteración 2:

numeroDecimal = 10 / 2 = 5
resto = 5 % 2 = 1
numeroBinario = 01

Iteración 3:

numeroDecimal = 5 / 2 = 2
resto = 2 % 2 = 0
numeroBinario = 010

Iteración 4:

numeroDecimal = 2 / 2 = 1
resto = 1 % 2 = 1
numeroBinario = 0101

Iteración 5:

numeroDecimal = 1 / 2 = 0
resto = 0 % 2 = 0
numeroBinario = 01010
```

**Actividad: Ejercicios de Lógica de Programación**

1. Basándose en el algoritmo 1 de la sesión 11, aplicar la siguiente variante: Dado un conjunto de números enteros, se debe determinar si existe algún número que aparezca más de una vez. Si es así, se deben imprimir todos los números que aparezcan más de una vez
   
2. Desarrollar un algoritmo que realice la conversión de binario a decimal.

### Solución:

1. 
```java
import java.util.ArrayList;

public class algo1 {

    public static void main(String[] args) {
        int[] numeros = { 1, 2, 3, 4, 5, 2, 4, 5, 5, 4 };

        ArrayList<Integer> numerosRepetidos = new ArrayList<>();

        for (int i = 0; i < numeros.length; i++) {
            for (int j = 0; j < i; j++) {
                if (numeros[i] == numeros[j] && !numerosRepetidos.contains(numeros[i])) {
                    numerosRepetidos.add(numeros[i]);
                }
            }
        }

        if (!numerosRepetidos.isEmpty()) {
            System.out.println("Los números repetidos son: ");
            for (int numero : numerosRepetidos) {
                System.out.println(numero);
            }
        } else {
            System.out.println("No hay ningún número repetido");
        }
    }
}
```

2. 
```java
import java.util.Scanner;

public class binario {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingrese un número decimal: ");
        double numeroDecimal = scanner.nextDouble();

        int parteEntera = (int) numeroDecimal;

        String parteBinariaEntera = "";

        while (parteEntera > 0) {
            int resto = parteEntera % 2;
            parteBinariaEntera = resto + parteBinariaEntera;
            parteEntera = parteEntera / 2;
        }

        double parteFraccionaria = numeroDecimal - (int) numeroDecimal;

        StringBuilder parteBinariaFraccionaria = new StringBuilder();

        // Convertir la parte fraccionaria a binario
        while (parteFraccionaria > 0) {
            if (parteBinariaFraccionaria.length() > 32) {
                System.out.println("La conversión binaria de la fracción se ha redondeado por longitud.");
                break;
            }
            double resultado = parteFraccionaria * 2;
            if (resultado >= 1) {
                parteBinariaFraccionaria.append(1);
                parteFraccionaria = resultado - 1;
            } else {
                parteBinariaFraccionaria.append(0);
                parteFraccionaria = resultado;
            }
        }

        System.out.println("El número binario es: " + parteBinariaEntera + "." + parteBinariaFraccionaria);

        scanner.close();
    }
}
```




