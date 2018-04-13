# Two Sum II - Input array is sorted

Given a Binary Search Tree and a target number, return true if there exist two elements in the BST such that their sum is equal to the given target.
Example:
```
Input: 
    5
   / \
  3   6
 / \   \
2   4   7

Target = 9

Output: True
```
```
Input: 
    5
   / \
  3   6
 / \   \
2   4   7

Target = 28

Output: False
```


```java
public class Solution{

    class TreeNode {
      int val;
      TreeNode left;
      TreeNode right;
      TreeNode(int x) { val = x; }
    }
    
    public boolean findTarget(TreeNode root, int k) {
        if(root == null) return false;

        List<Integer> list = new ArrayList<>();
        inOrder(root, list);

        int i = 0, j = list.size() - 1;
        while(i < j){
            int sum = list.get(i) + list.get(j);
            if(sum == k) return true;
            if(sum < k) i++;
            else j--;
        }
        return false;
    }
    public void inOrder(TreeNode root, List<Integer> list){
        if(root == null) return;
        inOrder(root.left, list);
        list.add(root.val);
        inOrder(root.right,list);
    }
}
```