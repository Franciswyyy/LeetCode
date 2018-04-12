# 3Sum Closest

Given an array S of n integers, find three integers in S such that the sum is closest to a given number, target. Return the sum of the three integers. You may assume that each input would have exactly one solution.


Example:
```
 For example, given array S = {-1 2 1 -4}, and target = 1.

    The sum that is closest to the target is 2. (-1 + 2 + 1 = 2).
```



```java
public class Solution{


    public static int threeSumClosest(int[] nums, int target) {
        int result = nums[0] + nums[1] + nums[nums.length-1];  //随便定义一个
        Arrays.sort(nums);
        for(int i = 0; i < nums.length - 2; i ++){
           int start = i + 1, end = nums.length - 1;
           while(start < end){
               int sum = nums[i] + nums[start] + nums[end];
               if(sum > target){ end --;}
               else {start ++;}
               //比较这个sum和result那个更接近
               if(Math.abs(sum - target) < Math.abs(result - target)){
                   result = sum;
               }
           }
        }
        return result;
    }
}
```