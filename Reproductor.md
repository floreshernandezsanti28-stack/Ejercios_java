import java.util.Scanner;
public class Reproductor {
   public void main(String[]args){
    Scanner Scanner = new Scanner(System.in);
    System.out.println("Ingrese el nombre de la cancion que desea reproducir");
    String cancion = Scanner.nextLine();

    System.out.println("Reproducir la cancion:"+ cancion);
    System.out.println("Ingrese el nombre de la cancion que desea pausar");

    String cancionPausar = Scanner.nextLine();

    System.out.println("Pausar la cancion:"+ cancionPausar);
     
    System.out.println("Ingresa el nombre de la cancion que desea cambiar");

    String cancionCambiar = Scanner.nextLine();

    System.out.println("Cambiar la cancion por:" + cancionCambiar);

 
   }
       }
