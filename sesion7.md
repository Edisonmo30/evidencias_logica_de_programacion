<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 7 


**Actividad 7: Ejecicios Array - ArrayList.**

**1. En parejas, probar, analizar y explicar el funcionamiento de los siguientes ejemplos de Array y ArrayList.**

*Ejemplo Array*

```Java

//Se define una variable suma inicializada en 0, se crea un ciclo for, con la variable i que inicializa en 0,
        //es menor a la longitud de la cadena y se suma i + 1, luego se le suma a la variable suma la variable números,
        //lo que nos da como resultado, la suma de todo el String del diccionario.
        // luego se define una variable como entero llamada maximo, inicializada en 0, 
        //y se inicia un ciclo for en el cual se define el iterable i inicializado en 0, con i menor
        //que la longitud total de la cadena y se incrementa +1, para recorrer todo el diccionario.
        // si el iterable i es mayor que cada número recorrido se reemplaza en la secuencia del iterable,
        //hasta que se defina el número que queda como el mayor de la cadena o diccionario,
        //por último, se imprime la variable máximo como resultado de el número más alto.
        //el método .sort, ordena los números de forma ascendente y el método .tostring, convierte el diccionario en una cadena.
        
import java.util.Arrays;

public class array1 {

    public static void main(String[] args) {
        // Crear un array de números enteros
        int[] numeros = {5, 2, 10, 7, 1};

        // Imprimir el array original
        System.out.println("Array original: " + Arrays.toString(numeros));       
        
        // Calcular la suma de los elementos del array
        int suma = 0;
        for (int i = 0; i < numeros.length; i++) {
            suma += numeros[i];
        }
        System.out.println("La suma de los elementos es: " + suma);

        // Encontrar el número más grande en el array
        int maximo = numeros[0];
        for (int i = 1; i < numeros.length; i++) {
            if (numeros[i] > maximo) {
                maximo = numeros[i];
            }
        }
        System.out.println("El número más grande es: " + maximo);

        // Ordenar el array en orden ascendente
        Arrays.sort(numeros);
        System.out.println("Array ordenado: " + Arrays.toString(numeros));
    }
}
```
*Ejemplo Arraylist*

```Java

/*Se importan las utilidades Arraylist y Scanner, luego se crea una clase llamada array2, se crea un Arraylist definido como lo dice 
 * la documentación y se crea la instancia scanner que se usa para tomar datos del usuario por consola. se inicializa el ciclo while en true,
 * y se le pide al usuario que ingrese los datos específicos, se crea una variable llamada opcion que almacena el dato seleccionado por el usuario,
 * se crea un condicional if que nos compara la variable con la selección del usuario, y si ingresa una opción diferente rompe el ciclo.
 * Se crea una función llamada agregarNota, donde se asigna el Arraylist y la entrada del usuario, se le pide al usuario que ingrese la nota,
 * y se almacena en una variable tipo String llamada titulo, se le pide al usuario que ingrese el contenido de la nota y se almacena en una variable 
 * tipo String llamada contenido, luego la variable notas se agrega al diccionario con el método .add y se almacena con el titulo + - + contenido.
 * se crea una funcion mostrarNotas donde asignamos como argumentos el Arraylist y la variable notas, se crea un ciclo for, que tiene la variable temporal
 * "n", y se usa : para separar la variable del diccionario notas, y se imprime la variable temporal "n".
 */

import java.util.ArrayList; 
import java.util.Scanner;

public class array2 {

  public static void main(String[] args) {

    ArrayList<String> notas = new ArrayList<>();
    
    Scanner scan = new Scanner(System.in);

    while(true) {

      System.out.println("1. Agregar nota");  
      System.out.println("2. Mostrar notas");
      System.out.println("3. Salir");

      int opcion = scan.nextInt();

      if (opcion == 1) {
        agregarNota(notas, scan);  
      } else if (opcion == 2) {
        mostrarNotas(notas);
      } else {
        break;
      }

    }

  }

  public static void agregarNota(ArrayList<String> notas, Scanner scan) {
    
    System.out.println("Ingrese el titulo de la nota:");
    String titulo = scan.nextLine();
    
    System.out.println("Ingrese el contenido de la nota:");
    String contenido = scan.nextLine();
    
    notas.add(titulo + " - " + contenido);

  }

  public static void mostrarNotas(ArrayList<String> notas) {

    for(String n : notas) {
      System.out.println(n);
    }

  }

}
```

**2. Crear un ejemplo de Array y otro de ArrayList para visualizar sus diferencias.**

*Ejemplo Array*

```Java

public class inventados1 {

    public static void main(String[] args) {
        String[] nombres = { "luis", "bertulfo", "esmeralda", "fabian" };
        int[] edades = { 20, 15, 11, 16 }; // Agregar edades correspondientes

        for (int i = 0; i < nombres.length; i++) {
            if (edades[i] > 18) { // Verificar si la persona es mayor de 18 años
                System.out.println(nombres[i]); // Imprimir el nombre de la persona
            }
        }
        
    }
}
```

*Ejemplo ArrayList*

```Java

import java.util.HashMap;
import java.util.Scanner;

public class inventados2 {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        HashMap<String, Integer> personas = new HashMap<>();

        while (true) {
            System.out.print("Ingresa un nombre o presiona Enter para salir: ");
            String nombre = scanner.nextLine();

            if (nombre.isEmpty()) {
                break;
            }

            System.out.print("Ingresa la edad de " + nombre + ": ");
            int edad = Integer.parseInt(scanner.nextLine());

            personas.put(nombre, edad);
        }

        HashMap<String, Integer> mayoresDe18 = new HashMap<>();
        HashMap<String, Integer> menoresDe18 = new HashMap<>();

        for (HashMap.Entry<String, Integer> entry : personas.entrySet()) {
            String nombre = entry.getKey();
            int edad = entry.getValue();

            if (edad >= 18) {
                mayoresDe18.put(nombre, edad);
            } else {
                menoresDe18.put(nombre, edad);
            }
        }

        System.out.println("Las personas mayores a 18 años son: " + mayoresDe18.keySet());
        System.out.println("Las personas menores de 18 años son: " + menoresDe18.keySet());

        scanner.close();
    }
}
```