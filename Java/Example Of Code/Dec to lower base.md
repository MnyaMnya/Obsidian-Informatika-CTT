```java
package intToBin;

import java.util.Scanner;

public class IntToBin {
	public static void main(String[] args) {
		int a,b,ref;
		String bin="";
		System.out.print("Ketik nilai yang mau di biner kan:");
		Scanner input = new Scanner(System.in); 
		 a = Integer.parseInt(input.next());
		 System.out.print("Biner basis brp: ");
		 b = Integer.parseInt(input.next());
		while (a >= 1){
				ref = a;
				a= a/b;
				back:
				do {
				if (ref % b <= b){
						bin =  Integer.toHexString(ref%b)+ bin;
					}
					if(ref >= b && ref%b >= b){
						ref= ref/10;
						continue back;
					}
				}while(false);
		}
			System.out.println("Hasilnya adalah "+ bin);
			input.close();
	}
}
```
