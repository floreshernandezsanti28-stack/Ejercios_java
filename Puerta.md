import java.util.Scanner;
public class Puerta {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Ingrese el estado de la puerta (abrir, cerrar):");
        String estado = scanner.nextLine();

        if (estado.equalsIgnoreCase("abrir")) {
            System.out.println("La puerta está abierta");
        } else if (estado.equalsIgnoreCase("cerrar")) {
            System.out.println("La puerta está cerrada");
        } else {
            System.out.println("Estado no válido");
        }
    }
}
