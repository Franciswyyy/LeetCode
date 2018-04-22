# Reverse Integer    

Given a 32-bit signed integer, reverse digits of an integer.


Example:
```
Input: 123
Output: 321

Input: 120
Output: 21
```

**Solution:**
```java
public class Solution{
    
    // 考虑溢出溢出情况
    public static int reverse(int x) {
        long res = 0;
        while(x != 0){
            res = res * 10 + x % 10;
            x = x / 10;
            if(res > Integer.MAX_VALUE || res < Integer.MIN_VALUE){
                return 0;
            }

        }
        return (int)res;

        /* long res = 0;
        while(x != 0){
            res = res*10 + x%10;
            x = x/10;
            if(res > Integer.MAX_VALUE || res < Integer.MIN_VALUE)
                return 0;
        }
        return (int)res;*/
    }
}
```