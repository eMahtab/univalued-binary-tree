# Univalued Binary Tree

A binary tree is univalued if every node in the tree has the same value.

Return true if and only if the given tree is univalued.

Note:

1. The number of nodes in the given tree will be in the range [1, 100].

2. Each node's value will be an integer in the range [0, 99].


## Implementation :

```java
public boolean isUnivalTree(TreeNode root) {
        Queue<TreeNode> q = new LinkedList<>();
        q.offer(root);
        while (!q.isEmpty()) {
            TreeNode n = q.poll();
            if (n.val != root.val) { return false; }
            if (n.left != null) { q.offer(n.left); }        
            if (n.right != null) { q.offer(n.right); }        
        }
        return true;
}
```
**What if the root is null?**
We can add the following statement as the first line in isUnivalTree(TreeNode)
if (root == null) return true;
In fact, the problem description states 
"The number of nodes in the given tree will be in the range [1, 100].", which implies root != null.


The above implementation have runtime complexity of O(n) and space complexity of O(n).

```
Runtime Complexity = O(n)
Space Complexity   = O(n)
```




# References :
https://massivealgorithms.blogspot.com/2019/01/leetcode-965-univalued-binary-tree.html
