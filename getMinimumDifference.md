#题目
二叉搜索树的最小绝对差
## 问题： 
给定一个所有节点为非负值的二叉搜索树，求树中任意两节点的差的绝对值的最小值。
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
     int min_dif = INT_MAX, val = -1;
    int getMinimumDifference(TreeNode* root) {
        if (root->left != NULL) getMinimumDifference(root->left);
        if (val >= 0) 
            min_dif = min(min_dif, root->val-val);
        val = root->val;
        if (root->right != NULL)
            getMinimumDifference(root->right);
        return min_dif;
    }
};
```
##总结
通过递归调用，依次求左子树右子树的最小绝对差，通过调用求最小值函数，更新最小值，最后返回即可。