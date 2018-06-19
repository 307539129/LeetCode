#题目
二叉搜索树结点最小距离
## 问题： 
给定一个二叉搜索树的根结点 root, 返回树中任意两节点的差的最小值。
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
    int minDiffInBST(TreeNode* root) {
       int res = INT_MAX, pre = -1;
        helper(root, pre, res);
        return res;
    }
    void helper(TreeNode* node, int& pre, int& res) 
    {
        if (!node) return;
        helper(node->left, pre, res);
        if (pre != -1) 
            res = min(res, node->val - pre);
        pre = node->val;
        helper(node->right, pre, res); 
    }
};
```
##总结
首先遍历左子树，再遍历右子树，求出当前节点的值跟当前节点的根节点的差，保存到res中，每次遍历都会更新数值，遍历结束后返回。