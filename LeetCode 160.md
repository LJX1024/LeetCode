# LeetCode 160

``` C++
/*
  struct ListNode {
      int val;
     ListNode *next;
     ListNode(int x) : val(x), next(NULL) {}
  };
  */
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
		if (headA == NULL || headB == NULL)
			return NULL;
		ListNode *curA = headA;
		ListNode *curB = headB;
		int lenthA = lenth(headA);
		int lenthB = lenth(headB);
		if (lenthA > lenthB) {
			for (int i = 0; i < lenthA - lenthB; ++i)
				curA = curA->next;
		}
		else {
			for (int i = 0; i < lenthB - lenthA; ++i)
				curB = curB->next;
		}

		while (curA != NULL && curB != NULL) {
		    if (curA == curB){
		        return curA;
		    }
			curA = curA->next;
			curB = curB->next;
		}
	
		return NULL;
	}
	int lenth(ListNode *p) {
		int count = 0;
		while (p != NULL) {
			++count;
			p = p->next;
		}
		return count;
	}
};
```

