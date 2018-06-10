#题目
路径总和
## 问题： 
给定一个二叉树和一个目标和，判断该树中是否存在根节点到叶子节点的路径，这条路径上所有节点值相加等于目标和。
说明: 叶子节点是指没有子节点的节点。
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
    bool hasPathSum(TreeNode* root, int sum) {
       if(!root) return false;
        if(!root->left && !root->right) return sum==root->val;
        if(root->left && hasPathSum(root->left,sum-root->val)) return true;
        return (root->right && hasPathSum(root->right,sum-root->val)); 
    }
};
```
##总结
首先判断二叉树是否为空，再判断是否只有一个节点，其他情况通过递归调用，判断是否满足条件，每一次递归，输入的值为减去当前节点值的sum。