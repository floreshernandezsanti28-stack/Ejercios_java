public class Lampara {
    public boolean estado;

    public Lampara() {
        this.estado = false;
    }

    public void interutor(boolean estado) {
        this.estado = estado;
    }

    public void informacion() {
        if (this.estado) {
            System.out.println("La Lampara esta encendida");
        } else {
            System.out.println("La Lampara esta apagada");
        }
    }

    public static void main(String[] args) {
        Lampara lamp = new Lampara();
        lamp.informacion();
    }
}
