#  Move Zeroes


Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

For example, given nums = [0, 1, 0, 3, 12], after calling your function, nums should be [1, 3, 12, 0, 0]. 


**Solution:**
```java
public class Solution{
    
    public static void moveZeroes(int[] nums) {

        int count = 0;
        for(int i = 0; i < nums.length; i ++){
            if(nums[i] == 0) continue;
            nums[count++] = nums[i];
        }
        while(count < nums.length){
            nums[count++] = 0;
        }
    }
}
```