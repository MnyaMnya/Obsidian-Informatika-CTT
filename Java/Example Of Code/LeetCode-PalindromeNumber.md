```java
class Solution {

    public boolean isPalindrome(int num) {

       long ref = 0, digit;

                int n=num;

    do

    {

        digit = num % 10;

        ref = (ref * 10) + digit;

        num = num / 10;

    }

    while (num != 0);

    if (n == ref && n>=0)

    {

        return true;

    }

    else

    {

        return false;

    }

    }  

}
```