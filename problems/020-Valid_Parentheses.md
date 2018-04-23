#  Valid Parentheses


Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

    Open brackets must be closed by the same type of brackets.
    Open brackets must be closed in the correct order.

Note that an empty string is also considered valid.

Example:
```
Input: "([)]"
Output: false

Input: "{[]}"
Output: true
```

**Solution:**
```java
public class Solution{
    
    public static boolean isValid01(String str){
        Stack<Character> stack = new Stack<Character>();
        char[] chars = str.toCharArray();
        for(char c : chars){
            if(c == '('){
                stack.push(')');
            }else if(c == '{'){
                stack.push('}');
            }else if(c == '['){
                stack.push(']');
            }else if(stack.isEmpty() || stack.pop() != c){
                return false;
            }
        }
        return stack.isEmpty();
    }


    public static boolean isValid(String str) {
        Stack stack = new Stack();
        char[] chars = str.toCharArray();
        for(int i = 0; i < chars.length; i ++){
            if(stack.isEmpty()){
                stack.push(chars[i]);
                continue;
            }else{
                if(chars[i] == ')' && (char)stack.peek() == '('){
                    stack.pop();
                }else if(chars[i] == '}' && (char)stack.peek() == '{'){
                    stack.pop();
                }else if (chars[i] == ']' && (char)stack.peek() == '['){
                    stack.pop();
                }else if(chars[i] == '(' || chars[i] == '{' || chars[i] == '['){
                    stack.push(chars[i]);
                }else{
                    return false;
                }
            }
        }
        return stack.isEmpty() ? true : false;
    }

}
```