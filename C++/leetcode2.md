# Problem Link 
https://leetcode.com/problems/add-two-numbers/

## SS of submission
![LeetCode Submission](./imagaes/leetcode2.png)

```C++
#include<iostream>
using namespace std;

class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode resultLL(0);
        ListNode* ptr = &resultLL;
        int carry = 0;
        while(l1 != nullptr || l2 != nullptr){
            int sum = 0 + carry;

            if(l1 != nullptr){
                sum += l1->val;
                l1 = l1->next;
            }
            if(l2 != nullptr){
                sum += l2->val;
                l2 = l2->next;
            }

            carry = sum / 10;
            sum %= 10;

            ptr->next = new ListNode(sum);
            ptr = ptr->next;
        }
        if(carry == 1){
            ptr->next = new ListNode(1);
        }
        return resultLL.next;
    }
};
```
## Helpful Resources
<p>
    Youtube video link : https://youtu.be/KMS0WFxrsT8
</p>

