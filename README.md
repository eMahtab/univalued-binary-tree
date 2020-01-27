# Univalued Binary Tree

A binary tree is univalued if every node in the tree has the same value.

Return true if and only if the given tree is univalued.

**Note:
1. The number of nodes in the given tree will be in the range [1, 100].
2. Each node's value will be an integer in the range [0, 99].
**



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
