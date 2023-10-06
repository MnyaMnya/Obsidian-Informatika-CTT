```java
import java.util.*;
public class Main {
	public static void main(String[] args) {
		int result=0;
		int i,temp,size;
		ArrayList<Integer> var = new ArrayList<Integer>(); // Create an ArrayList object
		outer:
		while(true) {
			Scanner input = new Scanner(System.in);
			String str = input.next();
			String[] arrOfStr = str.split("\n\n");
			for (String as : arrOfStr) {
				temp=0;
				i=0;
				String[] arr = as.split("\n");
				for (String d : arr) {
					temp = temp + Integer.parseInt(d);
					i++;
				}
				var.add(temp);
			}
			Collections.sort(var);
				size = var.size();
			System.out.println(var.get(size-1));
			continue outer;
		}
	}
}
```
