
# Roman to Integer    

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.


Example:
```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```

Example:
```
Input: "LVIII"
Output: 58
Explanation: C = 100, L = 50, XXX = 30 and III = 3.

Input: "MCMXCIV"
Output: 1994
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
```

**Solution:**
```java
public class Solution{
    

    public int romanToInt(String s) {
        int[] nums = new int[s.length()];
        for(int i = 0; i < s.length(); i ++){
            switch (s.charAt(i)){
                case 'M':
                    nums[i] = 1000;
                    break;
                case 'D':
                    nums[i] = 500;
                    break;
                case 'C':
                    nums[i] = 100;
                    break;
                case 'L':
                    nums[i] = 50;
                    break;
                case 'X':
                    nums[i] = 10;
                    break;
                case 'V':
                    nums[i] = 5;
                    break;
                case 'I':
                    nums[i] = 1;
                    break;
            }
        }
        int res = 0;
        for(int i = 0; i < nums.length-1; i++){
            if(nums[i] < nums[i + 1]){
                res = res - nums[i];
            }else {
                res = res + nums[i];
            }
        }
        return res;

    }
}
```