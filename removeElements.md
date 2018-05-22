#题目
删除链表中的节点
## 问题：
#### 
删除链表中等于给定值 val 的所有节点。
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
    ListNode* removeElements(ListNode* head, int val) {
          ListNode FirstNode(0);
          FirstNode.next = head;
        ListNode* p = &FirstNode;
        while(p != NULL)
         {
             ListNode* tmp = p->next;
             if(tmp !=  NULL && tmp->val == val )
             {
                 p->next = tmp->next;
                 delete tmp; 
             }
             else
                p= p->next;
        }
         return FirstNode.next;
    }
};
```
##总结
创建一个新节点，新节点的next指向head，遍历链表，判断链表的值如果等于val，则令前一链表的next等于当前链表的next，即保存了当前链表的下一个值，删除当前节点即可。