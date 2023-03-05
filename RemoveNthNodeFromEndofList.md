Remove Nth Node From End of List Leetcode-19

Given the head of a linked list, remove the nth node from the end of the list and return its head.

Example 1:

<img src="https://assets.leetcode.com/uploads/2020/10/03/remove_ex1.jpg" alt="example"/>

```
Input: head = [1,2,3,4,5], n = 2
Output: [1,2,3,5]
```

## Code :
```Javascript
var removeNthFromEnd = function(head, n) {
    let curr = head;
	while (n--) {
	  curr = curr.next;
	}
	if (!curr) return head.next;
	let temp = head;
    while (curr.next) {
	  curr = curr.next;
	  temp = temp.next;
	}
    temp.next = temp.next.next;
    return head;
}
```

![nth node from node](https://user-images.githubusercontent.com/96117746/222969180-f0ffb28d-9593-4fa9-ad1b-d949be0fd52d.png)
