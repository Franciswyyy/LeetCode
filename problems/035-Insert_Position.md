# Search Insert Position

Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You may assume no duplicates in the array.
Example:
```
Input: [1,3,5,6], 5
Output: 2

Input: [1,3,5,6], 2
Output: 1

Input: [1,3,5,6], 0
Output: 0
```

**Solution:**
```java
public class Solution{
    
    public static int searchInsert(int[] nums, int target) {
        if(nums == null || nums.length == 0) return 0;

        for(int i  = nums.length - 1; i >= 0;  i--){
            if(nums[i] < target) return i+1;
            else if(nums[i] == target) return i;
        }
        return 0;
    }

   
    //二分查找
    public static int searchInsert1(int[] nums, int target) {
        int lo = 0, hi = nums.length - 1;
        while(lo <= hi){
            int mid = (lo + hi)/2;
            if(nums[mid] == target) return mid;
            else if(nums[mid] > target) hi = mid -1;
            else lo = mid + 1;
        }
        return lo;
    }
}
```