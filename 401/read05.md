

  
# Implementation: Linked Lists 

## Linked Lists 

> ### What is a Linked List 
***A Linked List is a sequence of Nodes that are connected/linked to each other.*** 

> ### Terminology : 
* Linked List - A data structure that contains nodes that links/points to the next node in the list.

* Singly - Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list. 

* Doubly - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node. 

* Node - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link. 

* Next - Each node contains a property called Next. This property contains the reference to the next node. 

* Head - The Head is a reference of type Node to the first node in a linked list. 

* Current - The Current is a reference of type Node to the node that is currently being looked at. When traversing, you create a new Current variable at the Head to guarantee you are starting from the beginning of the linked list. 

> ### What does it look like 
![Like This](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/images/LinkedList1.PNG) 

> ### Prerequisites 
***When making your Node class, consider requiring a value to be passed in to require that each node has a value.*** 

## What’s a Linked List, Anyway pt1 

> ### Linear data structures 
***is a sequence and an order to how they are constructed and traversed.*** 


> ### Memory management 
**The biggest differentiator between arrays and linked lists is the way that they use memory in our machines.** 

**when a linked list is born, it doesn’t need 7 bytes of memory all in one place. One byte could live somewhere, while the next byte could be stored in another place in memory altogether! Linked lists don’t need to take up a single block of memory; instead, the memory that they use can be scattered throughout.** 


> ### Parts of a linked list 
***A linked list can be small or huge, but no matter the size, the parts that make it up are actually fairly simple. A linked list is made up of a series of nodes, which are the elements of the list.*** 

## What’s a Linked List, Anyway pt2 

> ### what even is BigO ? 
***There are two major points to consider when thinking about how an algorithm performs: how much time it requires at runtime given how much time and memory it needs.*** 

***One way to think about Big O notation is a way to express the amount of time that a function, action, or algorithm takes to run based on how many elements we pass to that function.*** 

> ### Growing a linked list 
1. First, we find the head node of the linked list.
2. Next, we’ll make our new node, and set its pointer to the current first node of the list.
3. Lastly, we rearrange our head node’s pointer to point at our new node. 


> ### To list or not to list ? 
***a linked list is usually efficient when it comes to adding and removing most elements, but can be very slow to search and find a single element.*** 
