#题目
二叉树的最小深度
## 问题： 
给定一个二叉树，找出其最小深度。

最小深度是从根节点到最近叶子节点的最短路径上的节点数量。
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
    int minDepth(TreeNode* root) {
        if (root == NULL) 
            return 0;
        if (root->left == NULL && root->right == NULL) 
            return 1;
        if (root->left == NULL)
            return minDepth(root->right) + 1;
        else if (root->right == NULL)
            return minDepth(root->left) + 1;
        else
            return 1 + min(minDepth(root->left), minDepth(root->right));  
    }
};
```
##总结
通过递归调用进行寻找叶子节点，求出左右子树的深度，通过最小值函数求出最小值返回。