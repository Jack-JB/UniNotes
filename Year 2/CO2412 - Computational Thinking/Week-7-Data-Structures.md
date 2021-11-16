# List-like Data Structures Python Implementation

## Dynamic Arrays

Lists in Python are implemented as dynamic arrays. Their elements behave in the same way as Python variables in general: For elementary data types as as numbers, they contain the value, otherwise they are object references.

Dynamic data structures can change in size and / or structure at runtime. For an array, this can be implemented by **allocating reserve memory** for any elements that may be appended in the future. **When the capacity of the dynamic array is exhausted, all of its contents need to be shifted** to another position in memory.

An array contains a sequence of elements of the same type, arranged **contiguously in memory.** The compiler/interpreter, and in some languages the programmer, can use **pointer arithmetic for converting indices to addresses.**

![image-20211116174808140](C:\src\UniNotes\Year 2\CO2412 - Computational Thinking\images\image-20211116174808140.png)

## Linked Lists

> The list contained a reference to its **head**, and may also contain one to its **tail.**

Linked lists are **dynamic data structures**

They differ from dynamic arrays in that their elements are **not contiguous in memory**. Therefore, pointer increments cannot be used to proceed from one element to the next.

Instead, the linked list consists of **nodes**, where each **item** is combined with a link to the **next node**. When his is all that is provided, the data structure is called a **singly linked list** 

![image-20211116175015329](C:\src\UniNotes\Year 2\CO2412 - Computational Thinking\images\image-20211116175015329.png)

### Singly linked lists

> ### Inserting an element
>
> If a **reference to a node** is given, another item can be **inserted after** that node in constant time; by accessing the linked-list object, it takes constant time to insert a new head at the beginning (**push**) or a new tail at the end (**append**).
>
> Walking `n elements` forward and doing an insertion there takes O(n) time.
>
> **Example: Insert 12 after `node x`, to which we already have a reference**
>
> <img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116175219505.png" alt="image-20211116175219505" style="zoom:80%;" />

> ### Deleting an element
>
> If a **reference to a node** is given, **deleting the subsequent node** from the list takes constant time; by accessing the linked-list object, it takes constant time to remove and return the **head item** (pop operation in a **stack** data structure).
>
> Walking `n elements` forward and doing a deletion there takes O(n) time.
>
> <img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116175528464.png" alt="image-20211116175528464" style="zoom:80%;" />

### Singly linked lists: Summary

In a **singly linked list**, nodes contain references (pointers) to the **next node**. This makes it possible to **iterate forward** in constant time, but not backward. **Insertion/deletion after** a given element (not before it!) takes **constant time.**

Recall that **for dynamic arrays,** general **insertion/deletion takes O(n*) time.**

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116175756453.png" alt="image-20211116175756453" style="zoom:80%;" />

## Doubly Linked Lists

In a **doubly linked list,** each node also contains a reference (or pointer) to the **previous node**. This facilitates traversal in **both directions and inserting** a new data item **before** any given node (rather than only after it), all in constant time.

Singly linked lists require two variables per data item (item and next).

Doubly linked lists require three variables per data item (previous, item and next).

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116180017809.png" alt="image-20211116180017809" style="zoom:80%;" />