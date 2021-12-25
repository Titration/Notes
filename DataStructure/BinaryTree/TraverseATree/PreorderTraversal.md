## Binary Tree Preorder Traversal
Given a binary tree, return the preorder traversal of its nodes' values.

Example:
```
Input: [1,null,2,3]

   1
    \
     2
    /
   3

Output: [1,2,3]
```

Java:
```
// Definition for a binary tree node.
public class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode() {}
    TreeNode(int val) { this.val = val; }
    TreeNode(int val, TreeNode left, TreeNode right) {
        this.val = val;
        this.left = left;
        this.right = right;
    }
}

class Solution {
    public List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> list = new ArrayList<Integer>();
        List<TreeNode> stack = new ArrayList<TreeNode>();
        
        if (root == null) {
            return list;
        }
        else {
            TreeNode temp = root;
            stack.add(temp);
            while(stack.size() > 0) {
                temp = stack.get(stack.size() -1);
                list.add(temp.val);
                stack.remove(stack.size() - 1);
                if (temp.right != null) {
                    stack.add(temp.right);
                }
                if (temp.left != null) {
                    stack.add(temp.left);
                }
            }
        }
        return list;
    }
}
```
