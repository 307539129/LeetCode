# Practice
二叉树的最大深度
## 问题分析：
#### 
给定一个二叉树，找出其最大深度。
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
    int maxDepth(TreeNode* root) {
     if(!root)
            return 0;
        int left=maxDepth(root->left);
        int right=maxDepth(root->right);
        return max(left,right)+1;
    }   
};
```
## 总结体会：
本题用递归调用求深度函数，每次调用返回当前根节点的最大深度，当函数运行结束返回最大深度后，再加上根节点，即为该二叉树的深度。