
# Palindrome Number

Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.


Example:
```
Input: 121
Output: true

Input: -121
Output: false
```

**Solution:**
```java
public class Solution{ 

    //判断回文  1.常见方法   2.转字符串，要额外空间   3.数字反转，会发生溢出
    public static boolean isPalindrome(int x) {
       if(x < 0) return false;
        char[] chars = Integer.toString(x).toCharArray();
        int i = 0, j = chars.length-1;
        while(i < j){
            if(chars[i] != chars[j]) return false;
            i++;
            j--;
        }
        return true;
    }

    //依次从个位数开始取到第一位
    public static boolean isPalindrome02(int x){
        if(x < 0) return false;
        int ans = 0;
        int num = x;
        while(num != 0){
            ans = ans * 10 + num % 10;
            num = num / 10;
        }
        return ans == x ? true : false;
    }
}
```
   































}
