# SueldoyBono

package ventas;

public class Sueldo {
    private int ventas;
    private int horas;
	
	
	public Sueldo(int vent, int hor) {
		ventas=vent;
		horas=hor;		
	}	
	
	public int Total(){
		if (horas<=40){
			return  horas*2000;
		}else{
			return ((horas-40)*3000)+80000;
		}
	}
	
	public double Bono(){
		
		if (ventas>300000 && ventas<=500000) {
			return ventas*0.05;
		}else if (ventas>500000){
			return ventas*0.1;
		}else{
			return 0;
		}
	}
}

--------------------------------------------------------------
package ventas;
import java.util.Scanner;

public class ventas {

	public static void main(String[] args) {
		

		int hh, ventas;
		
		Scanner sc=new Scanner(System.in);
		
		do{
			System.out.print("Ingrese horas trabajadas a la semana: ");
			hh=sc.nextInt();
			if (hh<1 || hh>80) System.out.println("Horas ingresadas incorrectas");
		}while(hh<1 || hh>80);
		
		do{
			System.out.print("Ingrese ventas por semana (en dinero): ");
			ventas=sc.nextInt();
			if (ventas<0) System.out.println("Ventas incorrectas");
		}while(ventas<0);
		
		Sueldo suel=new Sueldo(ventas, hh);
		
		System.out.println("\nSueldo semanal: $" + (suel.Total()+suel.Bono()));
		System.out.println("Sueldo mensual: $" + ((suel.Total()+suel.Bono()))*4);
		
		

	}

}

 
 
