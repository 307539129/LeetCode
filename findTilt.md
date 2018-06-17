#题目
二叉树的坡度
## 问题： 
给定一个二叉树，计算整个树的坡度。

一个树的节点的坡度定义即为，该节点左子树的结点之和和右子树结点之和的差的绝对值。空结点的的坡度是0。

整个树的坡度就是其所有节点的坡度之和
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
    int findTilt(TreeNode* root) {
       int res = 0;
        postorder(root, res);
        return res;
    }
    int postorder(TreeNode* node, int& res) {
        if (!node) return 0;
        int leftSum = postorder(node->left, res);
        int rightSum = postorder(node->right, res);
        res += abs(leftSum - rightSum);
        return leftSum + rightSum + node->val; 
    }
};
```
##总结
通过后续遍历函数，不断地累加左子树右子树节点，累加结束后再计算左子树右子树的差的绝对值，返回即可。