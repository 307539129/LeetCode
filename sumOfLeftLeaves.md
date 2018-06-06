#题目
左叶子之和
## 问题： 
计算给定二叉树的所有左叶子之和。
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
    int sumOfLeftLeaves(TreeNode* root) {
      int sum = 0;
        if (root != NULL)
        {
            if (root->left !=NULL)
            {
                if (root->left->left ==NULL&& root->left->right ==NULL)
                    sum += root->left->val;
                sum += sumOfLeftLeaves(root->left);
            }
            if (root->right !=NULL)
                sum += sumOfLeftLeaves(root->right);
        }
        return sum;
    }
};
```
##总结
通过递归调用，寻找左子叶，如果当前节点的左右都为空，则该节点为叶子节点，将所有左子叶加起来即可。