# LeetCode 83 — Remove Duplicates from Sorted List

**Difficulty:** Easy  
**Topic:** Linked List  
**Language:** C++

## Problem Statement

Given the head of a sorted linked list, remove duplicate nodes so that each value appears only once. Return the modified linked list.

## Example 1

**Input:**
```text
head = [1,1,2]
```

**Output:**
```text
[1,2]
```

## Example 2

**Input:**
```text
head = [1,1,2,3,3]
```

**Output:**
```text
[1,2,3]
```

## Approach

1. Start from the head using a pointer called `current`.
2. Traverse the list while the current node and its next node exist.
3. Compare the current node's value with the next node's value.
4. If both values are equal, skip the next node by updating the pointer.
5. Otherwise, move `current` to the next node.
6. Return the original head of the modified list.

## C++ Solution

```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode* current = head;

        while (current != nullptr && current->next != nullptr) {
            if (current->val == current->next->val) {
                current->next = current->next->next;
            } else {
                current = current->next;
            }
        }

        return head;
    }
};
```

## Complexity Analysis

- **Time Complexity:** `O(n)` — each node is processed at most a constant number of times.
- **Auxiliary Space Complexity:** `O(1)` — only one extra pointer is used.

## Key Concepts Learned

- Linked list traversal
- Pointer manipulation
- Removing duplicate nodes
- The `while` loop and `if-else` conditions
- In-place modification of a linked list

## Key Takeaway

Since the linked list is sorted, duplicate values appear next to each other. Comparing adjacent nodes allows us to remove duplicates in a single traversal without using extra data structures.
