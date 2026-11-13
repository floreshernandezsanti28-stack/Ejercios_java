import java.util.Scanner;
public class Semaforo {
    public static void main(String[] args) {
        Scanner Scanner = new Scanner(System.in);
        System.out.println("Ingrese el color del semaforo(verde, amarillo, rojo): ");
        String color = Scanner.nextLine();

        if(color.equalsIgnoreCase("verde")){
            System.out.println("El semaforo esta en verde, pude pasar");
        } else if(color.equalsIgnoreCase("amarillo")) {
            System.out.println("El semaforo esta en amarillo, precaucion");
        } else if(color.equalsIgnoreCase("rojo")) {
            System.out.println("El semaforo esta en rojo, detente");
        } else {
            System.out.println("Color no valido");
        }
    }
          
            
        
        
     }
