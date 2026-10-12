public class ListaEnlazada {

    // ===== CLASE INTERNA NODO =====
    // Definir Nodo como clase interna estática es una práctica común:
    // queda encapsulada y solo ListaEnlazada la usa.
    private static class Nodo {
        int dato;
        Nodo siguiente;

        Nodo(int dato) {
            this.dato = dato;
            this.siguiente = null;
        }
    }
      public static void main(String[] args) {
        ListaEnlazada lista = new ListaEnlazada();

        System.out.println("¿Está vacía? " + lista.estaVacia()); // true

        // Insertamos al final
        lista.insertarAlFinal(10);
        lista.insertarAlFinal(20);
        lista.insertarAlFinal(30);
        System.out.print("Tras insertar 10, 20, 30 al final: ");
        lista.imprimir(); // 10 → 20 → 30

        // Insertamos al inicio
        lista.insertarAlInicio(5);
        System.out.print("Tras insertar 5 al inicio: ");
        lista.imprimir(); // 5 → 10 → 20 → 30

        // Buscar
        System.out.println("¿Contiene 20? " + lista.buscar(20)); // true
        System.out.println("¿Contiene 99? " + lista.buscar(99)); // false

        // Contar
        System.out.println("Tamaño: " + lista.contar()); // 4

        // Obtener por índice
        System.out.println("Elemento en índice 2: " + lista.obtener(2)); // 20

        // Eliminar
        lista.eliminar(10);
        System.out.print("Tras eliminar 10: ");
        lista.imprimir(); // 5 → 20 → 30

        lista.eliminar(5); // borra la cabeza
        System.out.print("Tras eliminar la cabeza (5): ");
        lista.imprimir(); // 20 → 30

        lista.eliminar(30); // borra el último
        System.out.print("Tras eliminar el último (30): ");
        lista.imprimir(); // 20

        lista.eliminar(20); // deja la lista vacía
        System.out.print("Tras eliminar todo: ");
        lista.imprimir(); // La lista está vacía.
    }
    // ===== ATRIBUTO =====
    private Nodo cabeza;

    public ListaEnlazada() {
        this.cabeza = null;
    }

    public boolean estaVacia() {
        return cabeza == null;
    }

    public void insertarAlInicio(int dato) {
        Nodo nuevo = new Nodo(dato);
        nuevo.siguiente = cabeza;
        cabeza = nuevo;
    }

    public void insertarAlFinal(int dato) {
        Nodo nuevo = new Nodo(dato);
        if (cabeza == null) {
            cabeza = nuevo;
            return;
        }
        Nodo actual = cabeza;
        while (actual.siguiente != null) {
            actual = actual.siguiente;
        }
        actual.siguiente = nuevo;
    }

    public boolean buscar(int dato) {
        Nodo actual = cabeza;
        while (actual != null) {
            if (actual.dato == dato) return true;
            actual = actual.siguiente;
        }
        return false;
    }

    public boolean eliminar(int dato) {
        if (cabeza == null) return false;

        if (cabeza.dato == dato) {
            cabeza = cabeza.siguiente;
            return true;
        }

        Nodo anterior = cabeza;
        Nodo actual = cabeza.siguiente;

        while (actual != null) {
            if (actual.dato == dato) {
                anterior.siguiente = actual.siguiente;
                return true;
            }
            anterior = actual;
            actual = actual.siguiente;
        }
        return false;
    }

    public int contar() {
        int contador = 0;
        Nodo actual = cabeza;
        while (actual != null) {
            contador++;
            actual = actual.siguiente;
        }
        return contador;
    }

    public int obtener(int indice) {
        if (indice < 0) throw new IndexOutOfBoundsException("Índice negativo");
        Nodo actual = cabeza;
        int posicion = 0;
        while (actual != null) {
            if (posicion == indice) return actual.dato;
            actual = actual.siguiente;
            posicion++;
        }
        throw new IndexOutOfBoundsException("Índice fuera de rango: " + indice);
    }

    public void imprimir() {
        if (cabeza == null) {
            System.out.println("La lista está vacía.");
            return;
        }
        Nodo actual = cabeza;
        while (actual != null) {
            System.out.print(actual.dato);
            if (actual.siguiente != null) System.out.print(" → ");
            actual = actual.siguiente;
        }
        System.out.println();





   
    }
}
