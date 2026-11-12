import java.util.Scanner;
public class Circulo {
          // Atributo privado (Encapsulamiento)
    private double radio;

    // Constructor para inicializar el radio
    public Circulo(double radio) {
        this.radio = radio;
    }

    // Método Getter para obtener el radio
    public double getRadio() {
        return radio;
    }

    // Método Setter para modificar el radio si es necesario
    public void setRadio(double radio) {
        this.radio = radio;
    }

    // Método para calcular el área del círculo: Área = π * radio^2
    public double calcularArea() {
        return Math.PI * Math.pow(this.radio, 2);
    }
}

// Clase principal para probar el programa
    class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Solicitamos al usuario que ingrese el radio
        System.out.print("Ingrese el radio del círculo: ");
        double radio = scanner.nextDouble();

        // Creamos una instancia (objeto) de la clase Circulo con el radio ingresado
        Circulo miCirculo = new Circulo(radio);

        // Mostramos el radio y el área utilizando los métodos del objeto
        System.out.println("--- Cálculo del Área del Círculo (POO) ---");
        System.out.println("El radio es: " + miCirculo.getRadio());
        System.out.println("El área es: " + miCirculo.calcularArea());

        // Si quisieras cambiar el radio y recalcular:
        miCirculo.setRadio(10.0);
        System.out.println("\n--- Modificando el Radio ---");
        System.out.println("El nuevo radio es: " + miCirculo.getRadio());
        System.out.println("La nueva área es: " + miCirculo.calcularArea());
    }
}
