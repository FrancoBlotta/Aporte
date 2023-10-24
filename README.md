#Ejercicios academicos en Java sobre Hilos

package vmc.tp2hilos;

public class TP2hilos {

    public static void main(String[] args) {
        System.out.println("Iniciando hilo principal.");
        Hilo hilo1 = new Hilo("#1");
        Hilo hilo2 = new Hilo("#2");
        Hilo hilo3 = new Hilo("#3");
        
        hilo1.start();
        hilo2.start();
        hilo3.start();
        
        for (int i=0;i<10;i++){
            System.out.println("En el hilo principal, el recuento es "+i);
        try {
                int max = 2000;
                int min = 100;
                int random = (int) (Math.random()* max - min + 1) + min;
                Thread.sleep(random);
            }catch (InterruptedException exc) {
               System.out.println("Hilo principal interrumpido");
            }
        }
        System.out.println("Hilo principal finalizado");
    }
}
