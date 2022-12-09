## Inorder Traversal
Link : [Leetcode](https://leetcode.com/problems/binary-tree-inorder-traversal/)
<br />

### Two Solutions
1. Recursive
2. Iterative

#### Recursive
```
class Solution {

    private void inorder(TreeNode root, List<Integer> res) {
        if(root == null) {
            return;
        }
        inorder(root.left, res);
        res.add(root.val);
        inorder(root.right, res);
    }

    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> res = new ArrayList<>();
        inorder(root, res);
        return res;
    }
}
```

#### Iterative
```
class Solution {

    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> res = new ArrayList<>();
        LinkedList<TreeNode> stk = new LinkedList<>();

        while( true ) {
            while( root != null ) {
                stk.push(root);
                root = root.left;
            }

            if( stk.isEmpty() ) {
                return res;
            }

            root = stk.pop();
            res.add(root);
            root = root.right;
        }
    }
}
```

