# Univalued Binary Tree
## https://leetcode.com/problems/univalued-binary-tree

A binary tree is univalued if every node in the tree has the same value.

Return true if and only if the given tree is univalued.

Note:

1. The number of nodes in the given tree will be in the range [1, 100].

2. Each node's value will be an integer in the range [0, 99].


## Implementation : BFS

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
The above implementation have runtime complexity of O(n) and space complexity of O(n).

```
Runtime Complexity = O(n)
Space Complexity   = O(n)
```


## Implementation : DFS

```java
public boolean isUnivalTree(TreeNode root) {
        return dfs(root, root.val);
}

private boolean dfs(TreeNode n, int v) {
        if (n == null) { return true; }
        if (n.val != v) { return false; }
        return dfs(n.left, v) && dfs(n.right, v);
}    
```

The above implementation have runtime complexity of O(n) and space complexity of O(n).

```
Runtime Complexity = O(n)
Space Complexity   = O(n)
```


**What if the root is null?**

We can add the following statement as the first line in `isUnivalTree(TreeNode)`
if (root == null) return true;
In fact, the problem description states 
"The number of nodes in the given tree will be in the range [1, 100].", which implies root != null.


# References :
https://massivealgorithms.blogspot.com/2019/01/leetcode-965-univalued-binary-tree.html
