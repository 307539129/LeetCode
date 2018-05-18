#题目
反转链表
## 问题：
#### 
反转一个单链表。
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
    ListNode* reverseList(ListNode* head) {
       ListNode* pre = NULL;
       ListNode* next = NULL;
       while( head != NULL)
      {
           next = head->next;     
           head->next = pre;       
           pre = head;                
           head = next;              
      }
      return pre;                    
    }
};
```
##总结
首先定义两个节点，先保存后继节点，再令head指向前驱节点，然后对前驱节点和当前节点更新，完成循环后就将链表翻转。