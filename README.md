#Ejercicios academicos en Java sobre Hilos

CLASE HILO
package vmc.tp2hilos;

public class Hilo implements Runnable{
    String name;
    
    Hilo(String nombre){
        name=nombre;
    }
    
    public void run(){
        System.out.println("iniciando hilo "+name);
        try {
            for (int cont=0;cont<5;cont++){
                int random = (int) (Math.random()* 2000 - 100 + 1) + 100;
                Thread.sleep(random);
                System.out.println("En el hilo " +name+ ", el recuento es "+cont);
            }
        } catch (InterruptedException exc){
            System.out.println("Hilo " +name+ " interrumpido.");
        }
            System.out.println("Hilo " +name+ " finalizando.");
    }
}


CLASE MAIN
package vmc.tp2hilos;

public class TP2hilos {

    public static void main(String[] args) {
        System.out.println("Iniciando hilo principal.");
        
        Hilo hilo = new Hilo("#1");
        
        Thread nuevoHilo = new Thread(hilo);
        
        nuevoHilo.start();
        
        for (int i=0;i<10;i++){
            System.out.println("En el hilo principal, el recuento es "+i);
        try {
                int random = (int) (Math.random()* 2000 - 100 + 1) + 100;
                Thread.sleep(random);
            }catch (InterruptedException exc) {
               System.out.println("Hilo principal interrumpido");
            }
        }
        System.out.println("Hilo principal finalizado");
    }
}

