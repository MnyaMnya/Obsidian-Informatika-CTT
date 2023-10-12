```java
import java.util.HashMap;

import java.util.Iterator;

class Solution {

    public int romanToInt(String s) {

        HashMap<Character,Integer> hash = new HashMap<>();

                hash.put('I',1);

                hash.put('V',5);

                hash.put('X',10);

                hash.put('L',50);

                hash.put('C',100);

                hash.put('D',500);

                hash.put('M',1000);

                int result=0;

                for (int i=0;i<s.length();i++){

                    if(i<s.length()-1&&hash.get(s.charAt(i))<hash.get(s.charAt(i+1))){

                          result-=  hash.get(s.charAt(i));

                    }

                    else{

                        result+=  hash.get(s.charAt(i));

                    }

                }

                return result;

    }

    }
```