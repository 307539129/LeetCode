#题目
删除排序链表中的重复元素
## 问题：
#### 
给定一个排序链表，删除所有重复的元素，使得每个元素只出现一次。
## 编程实现：
```C++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
       if(!head || !head->next) 
           return head; 
        ListNode* l = head;
        while(l->next)
        {  
            if(l->val == l->next->val)  
                l->next = l->next->next;   
            else  
                l = l->next;
        }  
        return head;   
    }
};
```
##总结
先判断头结点是否为空，如果不是则进入循环，判断相邻值是否相等，如果相等则则改变前一节点的指向，使它指向后一节点的后继节点，如果不相等再判断下一节点。