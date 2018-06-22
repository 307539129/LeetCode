#题目
另一个树的子树
## 问题： 
给定两个非空二叉树 s 和 t，检验 s 中是否包含和 t 具有相同结构和节点值的子树。s 的一个子树包括 s 的一个节点和这个节点的所有子孙。s 也可以看做它自身的一棵子树。
## 编程实现：
```C++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    bool isSubtree(TreeNode* s, TreeNode* t) {
        if (!s)
            return false;
        if (isSame(s, t)) 
            return true;
        return isSubtree(s->left, t) || isSubtree(s->right, t);
    }
    bool isSame(TreeNode* s, TreeNode* t) {
        if (!s && !t) 
            return true;
        if (!s || !t) 
            return false;
        if (s->val != t->val) 
            return false;
        return isSame(s->left, t->left) && isSame(s->right, t->right);
    }
};
```
##总结
先从s的根结点开始，跟t比较，如果两棵树完全相同，就返回true，否则就分别对s的左子结点和右子结点调用递归再次来判断是否相同，只要有一个相同就返回true。