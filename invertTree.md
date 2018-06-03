#题目
翻转二叉树
## 问题：
#### 
翻转一棵二叉树。
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
    void exchange(TreeNode* root){
    TreeNode* node=root;
    if(node!=NULL){
        TreeNode* temp=node->left;
        node->left=node->right;
        node->right=temp;
    }
} 
    TreeNode* invertTree(TreeNode* root) {
       TreeNode* node=root;
    if(root==NULL) 
    return root;
    invertTree(node->left);
    invertTree(node->right);
    exchange(node);
    return root;  
    }
};
```
##总结
首先写一个交换二叉树的左子树和右子树函数，再递归调用遍历树的函数，先翻转根节点的左子树，再翻转根节点的右子树，最后交换根节点的左子节点与右子节点。