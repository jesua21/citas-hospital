# citas-hospital
almacenamiento de citas hospital
package extra;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.sql.Time;
import java.util.Random;
import java.util.Scanner;

public class extra {
	
	    public static class ClaseColas { 
	         static int max=100;  
	         static int cola[]= new int[max]; 
	         static int frente, fin; 
	         int nombre;
	         
	         ClaseColas() { 
	          frente=0;   fin=0;
	          System.out.println("Cola inicializada !!!");
	         }
	        
	         public static void Insertar(int dato) {
	          if(fin==max) { 
	          System.out.println("\nCola llena !!!");
	           return;
	          }
	          cola[fin++]=dato;
	          System.out.println("Dato insertado !!!");
	         }
	        
	         public static void Eliminar() {
	          System.out.println("\n\n<<< ELIMINAR >>>");
	          if(frente==fin) {  
	           System.out.println("\nCola vacia !!!");
	           return;
	          }
	             System.out.println("Elemento eliminado: "+cola[frente++]);
	         }
	        
	         public static void Mostrar() {
	          int i=0;
	          System.out.println("\n\n<<< MOSTRAR >>>");
	          if(frente==fin)  System.out.println("\nCola vacia !!!");
	          for(i=frente; i<fin; i++) {
	           System.out.println("cola["+i+"]="+" "+cola[i]);
	          }
	          System.out.println("\nFrente= "+frente);
	          System.out.println("Final = "+fin);
	          System.out.println("Max  = "+max);
	         }
	    }
	  
	    static ClaseColas Cola=new ClaseColas();  
	    
	    public static void main(String args[]) throws IOException {
	     int op=0;
	     do {
	           System.out.println("\n\n<<< REGISTRO DE CITA >>>");
	           System.out.println("1.- Altas");
	           System.out.println("2.- Eliminar");
	           System.out.println("3.- Mostrar");
	           System.out.println("0.- Salir");
	           System.out.print("Opcion? ---> ");
	           op=getInt();
	         
	           switch(op) {
	            case 1 : Altas();              break;
	            case 2 : Cola.Eliminar(); break;
	            case 3 : Cola.Mostrar();  break;
	           }
	     }while(op!=0);
	    }
	    
	    public static void Altas() throws IOException {
	    	Scanner leer = new Scanner(System.in);
	    	final Random random = new Random();
	    	
	     int elemento=0;
	     int numero = 0;
	        Random aleatorio;
	        
         
	     System.out.println("\n\n<<< ALTAS >>>");
	     System.out.print("Ingrese numero social ---> ");
	     elemento=getInt();
	     System.out.println("Ingresa Nombre...>");
	     
	     System.out.println("Ingrese Hora Disponible"+  24*60 );
	     final int millisInDay = 24*60*60*1000;
	     Time time = new Time((long)random.nextInt(millisInDay));
	    
	    
	     

	        

	        
	     
	     


	     
	     Cola.Insertar(elemento); 
	    }
	  
	    
	     public static String getString() throws IOException {
	            InputStreamReader isr = new InputStreamReader(System.in);
	            BufferedReader br = new BufferedReader(isr);
	            String s = br.readLine();
	            return s;
	        }   
	      
	       
	        public static int getInt() throws IOException {
	            String s = getString();
	            return Integer.parseInt(s);
	        }   
	}
