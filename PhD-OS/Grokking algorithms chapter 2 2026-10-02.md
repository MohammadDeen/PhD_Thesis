

## How Computer Memory Works ##

- like a giant set of drawers where each drawer has specific memory address (e.g fe0ffeeb)
- To store an item, you ask for space and it assigns and address to where the items will reside
-  When storing multiple items, two foundational data models used are arrays and linked lists.



## Arrays ##


- **Contiguous memory :** All elements are stored right **next to each other** in sequential memory slots
- **Memory allocation issues:** if you run out of memory in an array and want to add an item, you must request a larger block of contiguous memory and more all **existing items there**
- **Workaround ("Holding seats"):** You can reserve extra memory slots in advance ,though this risks wasting memory if unused , or still overflowing if input exceeds the extra slots.


## Linked lists ##

- **Scattered memory:** Elements can be located **anywhere in memory**
- **Pointer connections:** Each element contains its data value plus **memory address of the next item in the list**
- **Flexibility:** Adding an item is fast and easy, you place it anywhere in free memory and update the pointer of the previous item to link to it


## Operations & Access Types Comparison ##

**Access Types:**
- **Random access:** Arrays support random access because you can instantly calculate the memory address of the $i$-th element mathematically
- **Sequential access:** Elements are read one by one from the start. **Linked lists** support only sequential access because finding the $n$-th element requires traversing every preceding node to read its address pointer.

## Big O Performance ##

