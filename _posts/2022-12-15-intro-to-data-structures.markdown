---
layout: post
title:  "Intro to data structure"
date:   2022-12-25 10:55 +0800
categories: programming
---

Data structures are the fundamental building blocks of any program or software application. They are used to store, retrieve, and manipulate data in an organized and efficient manner. Data structures are classified into two main categories: linear data structures and non-linear data structures.

Linear data structures are those in which data elements are stored and accessed in a linear fashion, such as arrays, linked lists, and stacks. An array is a collection of elements of the same data type that are stored in contiguous memory locations. Linked lists are collections of data elements known as nodes, where each node contains a data field and a reference (or pointer) to the next node in the list. Stacks are collections of elements in which the last element added to the stack is the first element to be removed.

Non-linear data structures are those in which data elements are not stored and accessed in a linear fashion, such as trees and graphs. Trees are hierarchical data structures in which each node has one or more child nodes. The topmost node in a tree is called the root, and the nodes below the root are called child nodes. Graphs are collections of nodes and edges, where nodes represent data elements and edges represent the relationships between nodes.

There are several factors to consider when choosing a data structure for a particular problem, including the size of the data set, the frequency of data insertion and deletion, and the type of data being stored. Some common data structures and their characteristics include:

* Arrays: Arrays are simple data structures that are efficient for storing and accessing large amounts of data. However, they are not well suited for frequent insertions or deletions, as these operations can be time-consuming.

* Linked lists: Linked lists are dynamic data structures that can be easily resized and are well suited for frequent insertions*  and deletions. However, they are not as efficient as arrays for accessing and searching data.

* Stacks: Stacks are useful for storing and manipulating data in a last-in, first-out (LIFO) manner. They are commonly used in programming for tasks such as evaluating expressions and reversing lists.

* Queues: Queues are similar to stacks, but they operate on a first-in, first-out (FIFO) principle. They are often used for tasks such as scheduling jobs or managing requests.

* Trees: Trees are useful for storing and organizing hierarchical data, such as file systems or organizational charts. They are efficient for searching, inserting, and deleting data, but they require more memory than some other data structures.

* Graphs: Graphs are useful for representing relationships between data elements, such as social networks or transportation systems. They are efficient for searching and traversing data, but they can be more complex to implement than some other data structures.

In summary, data structures are essential tools for storing, retrieving, and manipulating data in an efficient manner. Choosing the right data structure for a particular problem can significantly impact the performance and scalability of a program or application.


# Stack 

- operatations: 
	- push: on top of stack 
	- pop: removes form the top of the stack(last item added).
- applications
	- when a function is called, it enters the calling stack. the function leaves the calling stack is always the last one entered (among functions still in the stack). 
	- provide a non-recursive implementations for problems that need a recursive solution 
	- reverse order (reverse string)
	- check if balanced parenthesis
	- retrace your steps (and try a different action)
	- interpretation and evaluation of symbolic expression: 
		- evaluate expressions like (5+2)*(12-3), or 
		- parse c code
	- search methods: travese a search graph

## implementing stacks
- stack can be implemented using: single linked list or arrays


### Linked list 
- linked list implementation 
- what is a stack: essentially a list 
- push(& stack item)
- O(1); 
- pop(& stack)
- O(1); frequent operation for this data structure

