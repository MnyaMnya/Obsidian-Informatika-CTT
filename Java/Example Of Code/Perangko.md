```java
package mtkDis;
import java.util.Scanner;
public class Num2 {

	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		int input = scan.nextInt();
		int counter4 = 0;
		int counter5 = 0;
		boolean found = false;
		scan.close();
		counter5 = input / 5;
		if(input % 5==0) {
			found = true;
		}
		else {counter4 = 1;}
		if(input % 4==0) {
			found=true;
			counter4=input/4;
			counter5=0;
		}
		while(found == false||counter5<0) {
			if((input-(5*counter5))%4==0) {
				counter4=(input-(5*counter5))/4;
				found=true;
			}
			else {
				counter5-=1;
			}
		}
		if(4*counter4+5*counter5!=input) {
			System.out.println("Tidak ditemukan");
		}
		else {
		System.out.println(4+"="+counter4+" "+5+"="+counter5);
		}
}
}
```