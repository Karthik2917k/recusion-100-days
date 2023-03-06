Merge Two Sorted Lists  LeetCode-21

You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists in a one sorted list. The list should be made by splicing together the nodes of the first two lists.

```
Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]
```

### Code 
```Javascript

var mergeTwoLists = function(list1, list2) {
    const res = new ListNode(-Infinity);

    let prev = res;

    while(list1 && list2){
        if(list1.val<=list2.val){
            prev.next = list1;
            prev = list1;
            list1 = list1.next;
        }else{
            prev.next = list2;
            prev = list2;
            list2 = list2.next;
        }
    }
    if(!list1) prev.next =list2;
    if(!list2) prev.next =list1;

    return res.next;
};

```

![image](https://user-images.githubusercontent.com/96117746/223107484-689b3ced-9776-40b1-b867-84e8fb2520a1.png)
