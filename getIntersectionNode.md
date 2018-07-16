#题目
相交链表
## 问题： 
编写一个程序，找到两个单链表相交的起始节点。
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
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode *p1 = headA;
        ListNode *p2 = headB;
        while (p1!=NULL&&p2!=NULL)
        {
            p1=p1->next;
            p2=p2->next;
        }
        while (p1!=NULL)
        {
            headA=headA->next;
            p1=p1->next;
        }
        while (p2!=NULL)
        {
            headB=headB->next;
            p2=p2->next;
        }
        while (headA!=NULL&&headB!=NULL)
        {
            if(headA==headB)
                return headA;
            headA=headA->next;
            headB=headB->next;
        }
        return NULL;
    }
};
```
##总结
首先找到两个链表长度差n，然后较长的链表先走n步，然后两个指针同时向前走，如果两个指针相等，则该点为交点的入口，如果遍历完指针仍然不相等，则说明无交点。