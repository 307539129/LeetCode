#题目
对称二叉树
## 问题： 
给定一个二叉树，检查它是否是镜像对称的。
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
    bool isSymmetric(TreeNode* root) {
        if( root == '\0')
            return true;
        return symmetric(root->left,root->right);
    }
    bool symmetric(TreeNode* l,TreeNode* r){
        if(l=='\0' && r=='\0')
            return true;
        if(l=='\0' || r=='\0')
            return false;
        return (l->val == r->val)&&symmetric(l->right,r->left)&&symmetric(l->left,r->right) ;
    }
};
```
##总结
首先写一个判断对称的函数，通过递归调用，判断左子树的左子叶和右子树的右子叶是否相等，再判断左子树的右子叶和右子树的左子叶是否相等，如果都相等，则表明该二叉树是镜像对称的。