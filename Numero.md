import java.util.Scanner;

public class Numero {
    public static class ValidadorEntero {
        public ValidadorEntero() {
        }

        public boolean esEntero(String entrada) {
            if (entrada == null || entrada.trim().isEmpty()) {
                return false;
            }

            try {
                Integer.parseInt(entrada.trim());
                return true;
            } catch (NumberFormatException e) {
                return false;
            }
        }
    }

    /**
     * Valida si un número entero se encuentra dentro de un rango permitido.
     * @param numero Número a evaluar.
     * @param min Límite inferior.
     * @param max Límite superior.
     * @return true si está en el rango, false si no.
     */
    public boolean estaEnRango(int numero, int min, int max) {
        return numero >= min && numero <= max;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ValidadorEntero validador = new ValidadorEntero();

        int numeroValido = 0;
        boolean bandera = false;

        System.out.println("=== Sistema de Validación de Enteros (POO) ===");

        while (!bandera) {
            System.out.print("Por favor, introduce un número entero (entre 1 y 100): ");
            String entrada = scanner.nextLine();

            if (validador.esEntero(entrada)) {
                int numero = Integer.parseInt(entrada.trim());

                if (numero >= 1 && numero <= 100) {
                    numeroValido = numero;
                    bandera = true;
                    System.out.println(" ¡Éxito! El número " + numeroValido + " es válido.");
                } else {
                    System.out.println("❌ Error: El número debe estar entre 1 y 100.");
                }
            } else {
                System.out.println("❌ Error: Lo que ingresaste no es un número entero válido.");
            }
        }

        scanner.close();
    }
}
