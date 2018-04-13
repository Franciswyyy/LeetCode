#  Subarray Sum Equals K

Given an array of integers and an integer k, you need to find the total number of continuous subarrays whose sum equals to k.
Example:
```
Input:nums = [1,1,1], k = 2
Output: 2
```


```java
public class Solution{

    public static int subarraySum(int[] nums, int k) {

        int res = 0;
        int len = 0;            
        while(len < nums.length){
            for(int i = len; i < nums.length; i ++){
                int sum = 0;
                int j = len;
                while(j >= 0){
                    sum += nums[i-j];
                    j--;
                }
                if(sum == k) res++;
            }
            len++;
        }
        return res;
    }
}
```

```java
public static int subarraySum(int[] nums, int k){
	int count = 0;
	for(int i = 0; i < nums.length; i ++){
		int sum = nums[i];
		if(sum == k) count++;
		for(int j = i + 1; j < nums.length; j ++){
			sum = sum + nums[j];
			if(sum == k) count ++;
		}
	}
	return count;
}
```

```java
public static int subarraySum(int[] nums, int k){
	int sum = 0, result = 0;
	Map<Integer, Integer> map = new HashMap<>();
	map.put(0,1);                           // 作用是当 k等于一个数的时候，等于0算一个数了
	for(int i= 0; i < nums.length; i ++){
		sum += nums[i];
		if(map.containsKey(sum - k)){
			result = result + map.get(sum - k);
		}
		map.put(sum, map.getOrDefault(sum, 0) + 1);    // 有几种情况能到达这个值，有的话就加1
	}
	return result;
}
```