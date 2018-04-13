#  4Sum II

Given four lists A, B, C, D of integer values, compute how many tuples (i, j, k, l) there are such that A[i] + B[j] + C[k] + D[l] is zero.
Example:
```
Input:
A = [ 1, 2]
B = [-2,-1]
C = [-1, 2]
D = [ 0, 2]

Output:
2

Explanation:
The two tuples are:
1. (0, 0, 0, 1) -> A[0] + B[0] + C[0] + D[1] = 1 + (-2) + (-1) + 2 = 0
2. (1, 1, 0, 0) -> A[1] + B[1] + C[0] + D[0] = 2 + (-1) + (-1) + 0 = 0
```


```java
public class Solution{

    public int fourSumCount(int[] A, int[] B, int[] C, int[] D) {
        Map<Integer, Integer> map = new HashMap<>();

        for(int i = 0; i < C.length; i ++){
            for(int j = 0; j < D.length; j++){
                int sum = C[i] + D[j];
                //看之前是否有c和d想加的值，没有就是0，有的话在原基础上+1
                map.put(sum, map.getOrDefault(sum, 0) + 1);
                /*
                上述简写
                Integer integer  = map.get(sum);
                if(integer == null){
                    integer = 0;
                }*/
            }
        }

        int res = 0;
        for(int i = 0; i < A.length; i++){
            for(int j = 0; j < B.length; j++){
                //因为要和上面的相反才为0 ，这时负号不就是相等了嘛，这只是取值，没有放值
                res = res + map.getOrDefault(-1 * (A[i] + B[j]), 0);
            }
        }
        return res;
    }
}
```