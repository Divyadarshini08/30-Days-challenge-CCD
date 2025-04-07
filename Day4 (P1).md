Day 4 of 30 days challenge CCD

**PROBLEM**
Given the heads of two singly linked-lists headA and headB, return the node at which the two lists intersect. If the two linked lists have no intersection at all, return null.

**PROBLEM LINK:** https://leetcode.com/problems/intersection-of-two-linked-lists/description/ 

**SAMPLE INPUT**
IntersectVal = 8, listA = [4,1,8,4,5], listB = [5,6,1,8,4,5], skipA = 2, skipB = 3

**OUTPUT**
Intersected at '8'.

**APPROACH**
1. Count lengths:
      Traverse List A and count the number of nodes (cnt1).
      Traverse List B and count the number of nodes (cnt2).
2. Find difference: Calculate the difference diff = abs(cnt1 - cnt2).
3. Align pointers: Move the pointer of the longer list ahead by diff steps.
4. Traverse together: Move both pointers one step at a time.
5. When they meet, that's the intersection node.
6. If both pointers reach NULL, there is no intersection.

**CODE**
```cpp
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode* temp1=headA;
        ListNode* temp2=headB;
        int cnt1=0,cnt2=0;
        while(temp1!=NULL)
        {
            cnt1++;
            temp1=temp1->next;
        }
        while(temp2!=NULL)
        {
            cnt2++;
            temp2=temp2->next;
        }
        temp1=headA;
        temp2=headB;
        int diff=0;
        if(cnt1>cnt2)
        {
            diff=cnt1-cnt2;
            while(diff!=0)
            {
                temp1=temp1->next;
                diff--;
            }
        }
        else{
            diff=cnt2-cnt1;
            while(diff!=0)
            {
                temp2=temp2->next;
                diff--;
            }
        }

        while((temp1!=NULL || temp2!=NULL)&&temp1!=temp2)
        {
            temp1=temp1->next;
            temp2=temp2->next;
        }
        return temp1;
    }
};
