#题目
平衡二叉树
## 问题： 
给定一个二叉树，判断它是否是高度平衡的二叉树。

本题中，一棵高度平衡二叉树定义为：

一个二叉树每个节点 的左右两个子树的高度差的绝对值不超过1。
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
    bool isBalanced(TreeNode* root) {
        if(check(root) == -1) 
            return false;  
        else return true;  
    }      
    int check(TreeNode* t) {  
        if(t == NULL) 
            return 0;  
        int ret = 0, l, r;  
        l = check(t->left);  
        r = check(t->right);  
        if(l == -1||r == -1) 
            return -1;  
        if(abs(l-r) > 1)
            return -1;  
        return max(l, r)+1;   
    }
};
```
##总结
通过函数检查二叉树的最大深度，如果左子树右子树的差的绝对值大于1，函数返回-1，在调用该函数后，如果返回值为-1，就返回false，否则返回true。