#题目
环形链表
## 问题： 
给定一个链表，判断链表中是否有环。
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
    bool hasCycle(ListNode *head) {
       if(head==NULL || head->next==NULL)
                return false;
            ListNode *slow=head;
            ListNode *fast=head;
            while(fast != NULL && fast->next !=NULL){
                slow = slow->next;
                fast = fast->next->next;
                if(slow == fast){
                    return true;  
       }
     } 
    return false;    
  }     
};
```
##总结
设置两个指针，快慢指针，当快指针追上慢指针时，即形成了环。