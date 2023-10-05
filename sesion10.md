<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 10 


**Actividad 10: Prueba, ejecución y explicación de ejercicios de lógica de programación**

**Ejercicios de Lógica de Programación**

### 1. Crear un programa en Java para calcular el interés de un CDT

Un CDT (Certificado de Depósito a Término) es un producto financiero en el que un inversor deposita una cantidad de dinero en un banco por un plazo determinado y a cambio recibe una tasa de interés fija. Al final del plazo, el inversor recupera su inversión inicial más los intereses generados. Aquí hay un ejemplo de cómo crear un programa en Java para calcular el interés de un CDT:

```java
import java.util.Scanner;
import java.text.DecimalFormat;

public class Main {
    public static void main(String[] args) {
        DecimalFormat decimalFormat = new DecimalFormat("#,###");
        Scanner scanner = new Scanner(System.in);

        System.out.println("Bienvenido al calculador de CDT!");

        // Pedir al usuario que ingrese los datos del CDT
        System.out.print("Ingrese el monto del depósito: ");
        double montoDeposito = scanner.nextDouble();

        System.out.print("Ingrese la tasa de interés anual (%): ");
        double tasaInteresAnual = scanner.nextDouble();

        System.out.print("Ingrese el plazo en meses: ");
        int plazoMeses = scanner.nextInt();

        // Calcular el interés y el monto total al vencimiento
        double tasaInteresMensual = tasaInteresAnual / 12 / 100;
        double interesMensual = montoDeposito * tasaInteresMensual;
        double montoTotalVencimiento = montoDeposito + (interesMensual * plazoMeses);

        // Mostrar el resumen del CDT
        System.out.println("Resumen del CDT:");
        System.out.println("- Monto del depósito: $" + decimalFormat.format(montoDeposito));
        System.out.println("- Tasa de interés anual: " + tasaInteresAnual + "%");
        System.out.println("- Plazo en meses: " + plazoMeses);
        System.out.println("- Interés mensual: $" + interesMensual);
        System.out.println("- Monto total al vencimiento: $" + decimalFormat.format(montoTotalVencimiento));
    }
}
```

**Explicación**

Se importan los módulos Scanner y Decimalformat, para pedir entrada por consola al usuario y formatear el número decimal a tres decimales si están presentes y los redondea si hay más de esa cantidad, también se puede usar el patrón O.OO para indicar que queremos que siempre se muestren dos decimales, así no estén presentes y se reemplazan por 0.
Se crean las instancias Decimalformat y Scanner, llamadas decimalformat y scanner, se imprime el mensaje de bienvenida, se pide al usuario que ingrese los datos del monto y el interés anual y se almacenan en una variable cada una de tipo double, se le pide al usuario el plazo a meses y se almacena en una variable tipo entero.

Se crean tres variables tasa interes mensual, interes mensual, monto total vencimiento, todas de tipo double y cada una realiza la operación respectiva para hacer el cálculo de interés y el monto total al vencimiento.

Se imprime por consola el resumen de CDT, en donde monto depósito se formatea con el método DecimalFormat a través de la instancia creada anteriormente, se muestra la tasa de interés ingresada por el usuario, el plazo a meses, el interés mensual y por último el monto total al vencimiento que sería la operación realizada en la variable creada y formateada a 3 decimales.


### 2. Calcular la desviación estándar

La desviación estándar es una medida estadística que indica cuánto varían los valores de un conjunto de datos respecto a la media aritmética. En otras palabras, mide la dispersión de los datos alrededor de la media.

La desviación estándar se calcula tomando la raíz cuadrada de la varianza, donde la varianza es la suma de los cuadrados de las diferencias entre cada valor y la media aritmética, dividido entre el número de valores menos uno.

La fórmula para calcular la desviación estándar es la siguiente:

```git
Desviación estándar = √(Σ(xi - x̄)² / (n - 1))
Donde:
xi: cada valor en el conjunto de datos.
x̄: la media aritmética del conjunto de datos.
n: el número de valores en el conjunto de datos.
Por ejemplo, si tenemos un conjunto de datos {10, 12, 15, 18, 20}, la media aritmética sería (10+12+15+18+20)/5 = 15. La varianza se calcularía de la siguiente manera:
Varianza = [(10 - 15)² + (12 - 15)² + (15 - 15)² + (18 - 15)² + (20 - 15)²] / 4
         = 20.5
Y la desviación estándar sería:
Desviación estándar = √(20.5) ≈ 4.53
```
La desviación estándar se utiliza a menudo en estadísticas para describir la variabilidad de un conjunto de datos. Una desviación estándar más grande indica que los valores están más dispersos alrededor de la media, mientras que una desviación estándar más pequeña indica que los valores están más concentrados alrededor de la media.

Un ejemplo para entender la desviación estándar sería el siguiente:

Supongamos que tenemos un conjunto de datos que representan el número de horas que un grupo de estudiantes estudia por semana. El conjunto de datos es el siguiente:

```git
{5, 10, 12, 15, 20}
Primero, calculamos la media aritmética del conjunto de datos:
Media aritmética = (5 + 10 + 12 + 15 + 20) / 5
                  = 12
```

```git
La media aritmética nos indica que, en promedio, los estudiantes estudian 12 horas por semana.
A continuación, calculamos la varianza del conjunto de datos:
Varianza = [(5 - 12)² + (10 - 12)² + (12 - 12)² + (15 - 12)² + (20 - 12)²] / 4
         = 52.5
```

La varianza nos indica cuánto varían los datos con respecto a la media. En este caso, la varianza es relativamente grande, lo que sugiere que los datos están bastante dispersos alrededor de la media.

Finalmente, calculamos la desviación estándar del conjunto de datos:

```git
Desviación estándar = √(52.5) ≈ 7.24
```

La desviación estándar nos indica cuánto se desvían los datos de la media. En este caso, la desviación estándar es relativamente grande, lo que confirma que los datos están bastante dispersos alrededor de la media.

En resumen, la desviación estándar es una medida estadística que indica cuánto varían los datos de la media. En el ejemplo anterior, la desviación estándar nos indica que los datos están bastante dispersos alrededor de la media, lo que sugiere que hay una gran variabilidad en el número de horas que los estudiantes estudian por semana.

Ejemplo en Java para calcular la desviación estándar de un conjunto de datos:

```java
import java.util.Scanner;

class Main{
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    
    System.out.print("Ingresar datos separados por comas: "); 
    String input = scanner.nextLine();
    
    String[] dataStr = input.split(","); 
    double[] data = new double[dataStr.length];
    
    for (int i = 0; i < dataStr.length; i++) {
       data[i] = Double.parseDouble(dataStr[i]);
    }
      
    int n = data.length;  
    double mean = 0, sum = 0, standardDeviation = 0;
      
    // Calcula la media aritmética   
    for (double num : data) {   
       sum += num;
    } 
    mean = sum / n;
      
    // Calcula la varianza      
    for (double num : data) {
         standardDeviation += Math.pow(num - mean, 2);       
     }
     standardDeviation /= n - 1;    
     standardDeviation = Math.sqrt(standardDeviation);  
     
     System.out.println("Mean = " + mean);     
     System.out.println("Standard deviation = " + standardDeviation);
  }  
}
```

Este código primero calcula la media aritmética del conjunto de datos y luego calcula la desviación estándar utilizando la fórmula que se explicó anteriormente. Finalmente, muestra la media aritmética y la desviación estándar en la consola.

```git
El resultado para el conjunto de datos {5, 10, 12, 15, 20} sería:
Media aritmética = 12.0
Desviación estándar = 7.236
```

**Explicación**

Se importa un módulo Scanner para pedir entrada por consola al usuario. Se crea la instancia Scanner y se le pide al usuario que ingrese los datos por consola almacenandolo en una variable llamada input de tipo string y se imprime el mensaje de ingresar datos separados por coma. Luego, se crea dos array. El primero, llamado dataStr que almacena los datos ingresados por el usuario en el array usando el metodo split para separar los datos por coma (delimitador) y el segundo es un array llamado data que se inicializa y se le asigna la longitud del array dataStr. Posteriormente, se crea un for en el que la variable i inicializa en 0 y debe ser menor a la longitud del dataStr y se incrementa en 1, en el bloque del código del for-each asignamos al array data la variable i que seria cada item iterado en el array anterior y se ejecuta el método parseDouble para asignarle cada dato del dataStr al array data. Luego se crea una variable tipo entero llamada n que es igual a la longitud del array data creando tambien tres variables de tipo double que inicializan en 0. Se crea un for-each para calcular la media aritmética donde se define una variable llamada num de tipo double para el array data y en el bloque de código a la variable sum le sumamos numero, lo que daria como resultado la suma de todos los datos ingresados por el usuario y a la variable mean se le asigna el valor de suma dividido n que es la longitud del array data. Luego, se crea un segundo for-each donde se asignan los mismos datos del for-each anterior y en el bloque de código a la variable standardDeviation se le suma el resultado de la variable num, menos la variable mean pontencia de 2. Despues, la viaraible standardDeviation se divide por la longirus del array data menos 1 que es la formula para calcular la viarianza de una población en especifico y ese resultado es igual a la raiz cuadrada de standardDeviation. Finalmente, se imprimen los resultados. La media igual a la viariable mean y la standardDeviation igual a la standardDeviation.