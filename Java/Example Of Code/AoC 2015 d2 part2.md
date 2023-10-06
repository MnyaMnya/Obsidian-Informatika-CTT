```java
import java.util.Scanner;
import java.util.*;
public class Main {
	static int[] discard(int[] disc) {
		Arrays.sort(disc);
		int[] var = {disc[0],disc[1]};
		return var;
	}
	static int Wrap(int x, int y) {
		return (2*x)+(2*y);
	}
	public static void main(String[] args) {
		int[] var = {0,0,0};
		int result=0;
		int i;
		outer:
		while(true) {
			Scanner input = new Scanner(System.in);
			String str = input.next();
			String[] arrOfStr = str.split("\n");
			for (String as : arrOfStr) {
			i=0;
			String[] arr = as.split("x");
			for (String d : arr) {
				if(i==0) {var[0] = Integer.parseInt(d);}
				if(i==1) {var[1] = Integer.parseInt(d);}
				if(i==2) {var[2] = Integer.parseInt(d);}
				i++;
			}
			int[] low= discard(var);
			result = result + (var[0]*var[1]*var[2]) + Wrap(low[0],low[1]);
		}
			System.out.println(result);
			continue outer;
	}
}
```
