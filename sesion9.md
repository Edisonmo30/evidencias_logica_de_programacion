<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 9 


**Actividad 9: Ejecicios de Lógica de Programación**

### 1. Calculadora de resistencias eléctricas

Una resistencia eléctrica es un componente electrónico que se utiliza para limitar el flujo de corriente eléctrica en un circuito. Es decir, su función es oponerse al paso de la corriente eléctrica y disminuir su intensidad.

Las resistencias se componen generalmente de un material conductor, como el carbono o el metal, que se coloca en un cuerpo cerámico o de vidrio. El valor de la resistencia (es decir, la cantidad de oposición que ofrece al paso de la corriente eléctrica) se mide en ohms, y depende de la composición del material y de su geometría.

Las resistencias se utilizan en una gran variedad de circuitos electrónicos, tanto en circuitos analógicos como digitales. Algunas de las aplicaciones más comunes de las resistencias incluyen la limitación de corriente en circuitos de alimentación, el ajuste de niveles de voltaje y corriente en circuitos de amplificación, y la medición de corriente y voltaje en circuitos de control y monitoreo.

Calculadora Código de colores - Online

https://www.digikey.com/es/resources/conversion-calculators/conversion-calculator-resistor-color-code

El objetivo de este ejercicio es crear un programa en Java que permita calcular el valor de una resistencia eléctrica a partir de los colores de sus bandas, y que tenga en cuenta la tolerancia.

Para ello, el programa debe solicitar al usuario que elija los colores de las tres bandas de la resistencia a través de un menú de opciones. Los colores disponibles son: negro, marrón, rojo, naranja, amarillo, verde, azul, violeta, gris y blanco.

Una vez que el usuario ha elegido los colores de las tres bandas, el programa debe pedir al usuario que seleccione la tolerancia de la resistencia a través de otro menú de opciones. Las opciones disponibles son: marrón (1%), rojo (2%), oro (5%) y plata (10%). Si el usuario no selecciona ninguna opción válida, se debe utilizar la tolerancia por defecto del 5%.

Con los colores y la tolerancia seleccionados, el programa debe calcular el valor de la resistencia y mostrarlo en la consola, junto con la tolerancia seleccionada.

Para calcular el valor de la resistencia, se debe utilizar la fórmula: valor = ((valor1 10) + valor2) multiplicador, donde valor1 y valor2 son los valores correspondientes a los dos primeros colores elegidos por el usuario (según la tabla de colores), y multiplicador es el valor correspondiente al tercer color elegido por el usuario (también según la tabla de colores). Finalmente, se debe mostrar el valor de la resistencia en ohms y la tolerancia seleccionada.


```java
import java.util.Scanner;

public class Resistencia {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String[] colores = { "negro", "marrón", "rojo", "naranja", "amarillo", "verde", "azul", "púrpura", "gris",
                "blanco" };
        double[] multiplicador = { 1, 10, 100, 1000, 10000, 100000, 1000000, 0.1, 0.01 };

        System.out.println("Selecciona el color de la primera banda:");
        for (int i = 0; i < colores.length; i++) {
            System.out.println((i + 1) + ". " + colores[i]);
        }
        int banda1 = scanner.nextInt() - 1;

        System.out.println("Selecciona el color de la segunda banda:");
        for (int i = 0; i < colores.length; i++) {
            System.out.println((i + 1) + ". " + colores[i]);
        }
        int banda2 = scanner.nextInt() - 1;

        String c1 = String.valueOf(banda1);
        String c2 = String.valueOf(banda2);

        String conc = c1 + c2;

        int resultado = Integer.parseInt(conc);

        double multi = 1;

        System.out.println("Selecciona el color de la tercera banda (Multiplicador):");
        System.out.println("1. Negro (*1)");
        System.out.println("2. Marrón (*10)");
        System.out.println("3. Rojo (*100)");
        System.out.println("4. Naranja (*1000)");
        System.out.println("5. Amarillo (*10000)");
        System.out.println("6. Verde (*100000)");
        System.out.println("7. Azul (*1000000)");
        System.out.println("8. Púrpura (/10)");
        System.out.println("9. Gris (/100)");
        System.out.println("10. Blanco");
        double seleccionmultiplicador = scanner.nextDouble();

        System.out.println("Selecciona el color de la cuarta banda (tolerancia):");
        System.out.println("1. Marrón (1%)");
        System.out.println("2. Rojo (2%)");
        System.out.println("3. Oro (5%)");
        System.out.println("4. Plata (10%)");
        int seleccionTolerancia = scanner.nextInt();

        double tolerancia = 0;
        switch (seleccionTolerancia) {
            case 1:
                tolerancia = 1;
                break;
            case 2:
                tolerancia = 2;
                break;
            case 3:
                tolerancia = 5;
                break;
            case 4:
                tolerancia = 10;
                break;
        }

        if (seleccionmultiplicador >= 1 && seleccionmultiplicador <= 9) {
            multi = resultado * multiplicador[(int) seleccionmultiplicador - 1];

            if (seleccionmultiplicador == 8 || seleccionmultiplicador == 9) {
                System.out.println("El valor de la resistencia es: " + multi + "Ohms");
            } else if (multi >= 1000) {
                int valorEnKiloOhms = (int) (multi / 1000);
                System.out.println("El valor de la resistencia es: " + valorEnKiloOhms + "kOhms");
            } else {
                System.out.println("El valor de la resistencia es: " + (int) multi + "Ohms");
            }
        }

        System.out.println("Tolerancia: " + tolerancia + "%");

        scanner.close();
    }
}
```

