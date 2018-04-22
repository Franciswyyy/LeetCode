#  Longest Common Prefix

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

Example:
```
Input: ["flower","flow","flight"]
Output: "fl"

Input: ["dog","racecar","car"]
Output: ""
```

**Solution:**
```java
public class Solution{
 
    public static String longestCommonPrefix(String[] strs) {
        if(strs == null || strs.length == 0) return  "";
        String pre = strs[0];
        for(int i = 1; i < strs.length; i ++){
            while(strs[i].indexOf(pre) != 0){  //因为是公共前缀，肯定是在第一个就匹配了
                pre = pre.substring(0, pre.length() - 1); //长了就缩短一个
            }
        }
        return pre;
    }

}
```
```
String的indexOf方法： 是查找子串开始的位置，没有的话就返回-1
   Java中查找子串共4种方法：  一个向前，一个向后
1. int indexOf(String str)
2、int indexOf(String str, int startIndex)：从指定的索引处开始，返回第一次出现的指定子字符串在此字符串中的索引。
3、int lastIndexOf(String str) ：返回在此字符串中最右边出现的指定子字符串的索引。
4、int lastIndexOf(String str, int startIndex) ：从指定的索引处开始向后搜索，返回在此字符串中最后一次出现的指定子字符串的索引。
```