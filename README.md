# Univalued Binary Tree


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
