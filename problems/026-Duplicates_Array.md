# Remove Duplicates from Sorted Array


Given a sorted array nums, remove the duplicates in-place such that each element appear only once and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.
Example:
```
Given nums = [0,0,1,1,1,2,2,3,3,4],
[0,1,2,3,4]
```

**Solution:**
```java
public class Solution{
    
    public int removeDuplicates(int[] nums) {
        if(nums.length == 0)return 0;
        int count = 1;
        for(int i = 1; i < nums.length; i ++){
            if(nums[i] == nums[i - 1]) continue;
            nums[count++] = nums[i];
        }
        return count;
    }
}
```