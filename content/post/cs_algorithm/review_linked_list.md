+++
author = "ykhorizon"
date = "2018-10-11T10:41:20+08:00"
title = "Review Linked List Fundamental Concepts and Operation"
categories = ["data-structure","data-structure/linked-list"]
tags = ["review","interview"]
type = "post"
draft = true
+++




## Pointer 
In computer science, pointer is an important idea that underpin the behavior of reference as well as address. Pointer is a address that pointing to data. In many data structure, we call it "structure" means data organizing with certain way. The way of organizing is common implemented by "pointer". 

However, not all the programming language has concept of pointer, but they all firmly contain "behavior reference". You can check out the keyword "comparison of reference by value between reference by pointer".Some of language hidden the pointer concept due to security consideration and abstraction.

## Pros and Cons (Compare to Array)

Pros

- Overflow on linked structures can never occur unless the memory is actually full 
- With large records, moving pointers is easier and faster than moving the items themselves. 
- Insertions and deletions are simpler than for contiguous (array) lists. 

Cons

- Linked structures require extra space for storing pointer fields. 
- Linked lists do not allow efficient random access to items. 
- Arrays allow better memory locality and cache performance than random pointer jumping. 

## Linked List

__Linked List in Python__
```python
class ListNode:
     def __init__(self, x):
         self.val = x
         self.next = None
```

__the diagram describe the linked list__
![](/content_img/review_linked_list/visualization.png)

## Operation 

### Search

### Insertion

### Deletion






