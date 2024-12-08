import java.util.*;
import static java.lang.System.out;
public class DenklemÇözümü {
	public static void main(String[] args) {
		Scanner klavye = new Scanner(System.in);
		double[][] A = new double[2][2];
		double[][] ekA = new double[2][2];
		double[][] x = new double[2][2];
		double[][] b = new double[2][2];
		String[][] bilinmeyen = new String[2][1];
		bilinmeyen[0][0] = "x";
		bilinmeyen[1][0] = "y";
		out.println("2 bilinmeyenli denklem çözümüiçin değer giriniz");
		for(int i=0; i<2; i++) {
			for(int j=0; j<2; j++) {
				out.println("Lütfen "+(i+1)+". denklemde "+bilinmeyen[j][0]+"'in katsayısını giriniz");
				A[i][j] = klavye.nextDouble();
			}
		}
		for(int i=0; i<2; i++) {
			out.println("Lütfen "+(i+1)+". denklem sonucu giriniz");
			b[i][0] = klavye.nextDouble();
		}
		ekA[0][0] = A[1][1];
		ekA[0][1] = -1*A[0][1];
		ekA[1][0] = -1*A[1][0];
		ekA[1][1] = A[0][0];
		double detA = A[0][0]*A[1][1]-(A[0][1]*A[1][0]);
		for(int i=0; i<2; i++) {
			for(int j=0; j<2; j++) {
				x[i][j] *=(1/detA);
			}
		}
		out.println("Denklem: ");
		out.println(A[0][0]+"x+"+A[0][1]+"y="+b[0][0]);
		out.println(A[1][0]+"x+"+A[1][1]+"y="+b[1][0]);
		out.println("Çözüm");
		out.println("x = "+x[0][0]+" y = "+ x[1][0]);		
	}	
}
