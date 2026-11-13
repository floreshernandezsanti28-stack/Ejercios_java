import java.util.Scanner;
public class Termometro {
    public static void main(String[] args) {
        Scanner Scanner  = new Scanner(System.in);
        System.out.println("Ingresa la temperatura ");
        double temperatura = Scanner.nextDouble();

        System.out.println("La temperatura es: " + temperatura);

        double fahrenheit =(temperatura * 9/5) + 32;

        System.out.println("La temperatura en grados Fahrenheit es: " + fahrenheit);
        double kelvin = temperatura + 273.15;

        System.out.println("La temperatura en grados Kelvin es: " + kelvin);

        System.out.println("La temperatura en grados Rankine es :"+ (temperatura * 9/5)+ 491.67);
        double reaumur = temperatura * 4/5;
        System.out.println("La temperatura en grados Réaumur es: " + reaumur);

        Scanner.close();
        System.out.println("Gracias por usar el programa de conversion de temperatura");
        

         

    }
}
