Given two single linked lists determine if the lists intersect and return the intersecting node.
The intersection is based on the reference value and not the value stored in the node

/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 
//structure to hold the length and tail of a given list
struct result {
    int len;
    ListNode *tail;
    result(int x): len(x), tail(NULL){}
};
*/
class Solution {
public:
    
    int getLength(ListNode *head)
    {
        int count = 0;
        ListNode *cur = head;
        while (cur)
        {
            count++;
            cur = cur->next;
        }
        //result *list = new result(count);
        //list->tail = cur;
        return count;
    }
    
    ListNode *getTail (ListNode *head)
    {
        ListNode *cur = head;
        while (cur)
        {
            cur = cur->next;
        }
        
        return cur;
    }
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode *shorter, *longer, *tailA, *tailB;
        int lenA, lenB;
        
        if (headA == nullptr || headB == nullptr)
        {
            return nullptr;
        }
        
        //Get the length 
        lenA = getLength (headA);
        lenB = getLength (headB);
        
         //Get the tail
        tailA = getTail (headA);
        tailB = getTail (headB);
        
        
        if (tailA != tailB)
        {
            return nullptr;
        }
        
        shorter =  (lenA < lenB)? headA: headB;
        longer = (lenA > lenB) ? headA : headB;
        
        int k = abs(lenA - lenB);
        while (k > 0 && longer)
        {
            longer = longer->next;
            k--;
            
        }
        while (shorter && longer)
        {
            if (shorter->next == longer->next)
            {
                break;
            }
            shorter = shorter->next;
            longer = longer->next;
       }
        return shorter->next;
    }
};


