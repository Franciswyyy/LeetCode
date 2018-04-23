# Implement strStr()


Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.
Example:
```
Input: haystack = "hello", needle = "ll"
Output: 2

Input: haystack = "aaaaa", needle = "bba"
Output: -1
```

**Solution:**
```java
public class Solution{
    
    public static int strStr(String haystack, String needle) {
        return haystack.indexOf(needle);
    }

	
    public static int strStr(String haystack, String needle) {
        for(int i = 0; ; i ++){   //hay的长度
            for(int j = 0; ; j ++){        // need的长度
                if(j == needle.length()) return i;    // 如果已经遍历到了need, 则可以返回了
                if(i + j == haystack.length()) return -1;
                if(needle.charAt(j) != haystack.charAt(i + j)) break;
            }
        }
    }
}
```