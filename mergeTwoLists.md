#题目
合并两个有序链表
## 问题：
#### 
将两个有序链表合并为一个新的有序链表并返回。新链表是通过拼接给定的两个链表的所有节点组成的。
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
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
       if(l1 == '\0')
            return l2;
        else if(l2 == '\0')
            return l1;
        ListNode *dummy = new ListNode(0);
        ListNode *runNode = dummy;
        while(l1 != '\0' && l2 != '\0')
        {            
            if(l1->val < l2->val)
            {
                runNode->next = l1;
                l1 = l1->next;
            }
            else
            {
                runNode->next = l2;
                l2 = l2->next;
            }            
            runNode = runNode->next;
        }
        if(l1!='\0')
            runNode->next = l1; 
            else runNode->next = l2;
        return dummy->next; 
    }
};
```
##总结
依次遍历两个链表，先比较链表1和链表2当前结点值的大小，选择较小的节点排在新节点后，生成一个新的链表。