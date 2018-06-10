#题目
修剪二叉搜索树
## 问题： 
给定一个二叉搜索树，同时给定最小边界L 和最大边界 R。通过修剪二叉搜索树，使得所有节点的值在[L, R]中 (R>=L) 。你可能需要改变树的根节点，所以结果应当返回修剪好的二叉搜索树的新的根节点。
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
    TreeNode* trimBST(TreeNode* root, int L, int R) {
      if (root == NULL)   return NULL;
        if (root->val < L)  return trimBST(root->right, L, R);
        if (root->val > R)  return trimBST(root->left, L, R);
        root->left = trimBST(root->left, L, R);
        root->right = trimBST(root->right, L, R);
        return root;  
    }
};
```
##总结
遍历二叉树，如果是空，则直接返回空。如果当前节点的值大于R则返回其右节点调用递归函数的值，如果节点的值小于L则返回其左节点调用递归函数的值。如果节点的值在范围内则将左右节点调用递归函数的值赋值给其左右节点，递归结束后级把不在范围内的节点删除，返回该节点。