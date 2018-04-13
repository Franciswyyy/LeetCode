#  3Sum Smaller

Given an array of n integers nums and a target, find the number of index triplets i, j, k with 0 <= i < j < k < n that satisfy the condition nums[i] + nums[j] + nums[k] < target.

For example, given nums = [-2, 0, 1, 3], and target = 2.

Return 2. Because there are two triplets which sums are less than 2:
Example:
```
[-2, 0, 1]
[-2, 0, 3]
```


```java
public class Solution{

    public static int threeSumSmaller(int[] nums, int target) {
        Arrays.sort(nums);

        int n = nums.length, count = 0;
        for(int i = 0; i < n -2; i ++){
            int j = i + 1, k = n -1;

            while(j < k){
                int sum = nums[i] + nums[j] + nums[k];

                if(sum >= target) {
                    k--;
                }else{
                    count  = count + (k - j);
                    //意思就是k都满足了那么  k和j中间肯定是满足的，否则j不懂，把j到k之间又遍历一遍
                    j ++;
                }
            }
        }
        return count;
    }
}
```

