#题目
相同的树
## 问题： 
给定两个二叉树，编写一个函数来检验它们是否相同。

如果两个树在结构上相同，并且节点具有相同的值，则认为它们是相同的。
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
    bool isSameTree(TreeNode* p, TreeNode* q) {
        if(p == NULL || q == NULL)
            if(p == q)
                return true;
            else
                return false;
        return (p->val==q->val && isSameTree(p->left, q->left) && isSameTree(p->right, q->right));
    }
};
```
##总结
首先判断两个二叉树是否为空如果不为空就进行递归调用，如果根节点具有相同的值，再判断根的左右子树，如果根的左子树是相同的和根的右子树是相同的返回true，否则返回false。