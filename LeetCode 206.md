# LeetCode 206



##  [Reference 1](http://algorithms.tutorialhorizon.com/reverse-a-linked-list/) 



## [Reference 2](https://segmentfault.com/a/1190000004708243)



看不懂了，就看reference1, reference2. 

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
        ListNode* current = head;
        ListNode* pre = NULL;
        ListNode * next = NULL;
        while( current != NULL){
            next = current->next;
            current->next = pre;
            pre = current;
            current = next;
            
        }
        head= pre;
        return head;
    }
};

/*
---------------------------------------------------------------------
*/
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        
        if(head == NULL || head->next == NULL)
            return head;
        
        return getReverseList(head, NULL);  // because prev needs be null at the first time.
        
    }
    
    ListNode* getReverseList(ListNode* curr, ListNode* prev){
        if (curr->next == NULL){
            curr->next = prev;
            return curr;
        } 
        else{
            ListNode* temp = curr->next;  // store next node
            curr->next = prev;
           return  getReverseList(temp, curr);
        }
        
    }
};
```

