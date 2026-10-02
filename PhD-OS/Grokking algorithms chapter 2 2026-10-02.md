

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


| Operation     | Arrays | Linked Lists | Explanation                                                                                   |
| ------------- | ------ | ------------ | --------------------------------------------------------------------------------------------- |
| **Reading**   | $O(1)$ | $O(n)$       | Arrays calculate addresses instantly; linked lists must follow pointer chains7more_horiz.     |
| **Insertion** | $O(n)$ | $O(1)$       | Arrays must shift elements down (or reallocate memory); linked lists just update pointers910. |
| **Deletion**  | $O(n)$ | $O(1)$       | Arrays must shift remaining items up; linked lists just change pointer targets10.             |

_(Note:_ $O(1)$ _insertion and deletion for linked lists assume direct access to the target position, such as tracking the head or tail_10_.)_




## Selection sort algorithm ##

-  **How it works:**  Selection sort builds a sorted list by repeatedly scanning an unsorted list to find the smallest (or largest ) remaining element and appending it to the new sorted list.
-  **Time complexities analysis:**   
- Finding the smallest item in an unsorted list of $n$ elements  takes $O$ ($n$) **Linear time** 
- Performing this $O(n)$ search across all $n$ items results in $O(n \times n) = O(n^2)$ **quadratic time**
- 











# Chapter 2 Study Note: Selection Sort & Fundamental Data Structures

## 1. How Computer Memory Works

- Computer memory resembles a **giant set of drawers**, where each drawer has a specific memory address (e.g., `fe0ffeeb`).
    
- Whenever you want to store items in memory, you ask the computer for space, and it assigns an address where those items reside.
    
- When storing multiple items, the two foundational data structures used are **arrays** and **linked lists**.
    

### Visualisation: Memory as Drawers

```
COMPUTER MEMORY

Memory Address
     ↓
┌──────────┬─────────────────┐
│  1000    │     Alice       │
├──────────┼─────────────────┤
│  1004    │      Bob        │
├──────────┼─────────────────┤
│  1008    │     Carol       │
├──────────┼─────────────────┤
│  1012    │     David       │
└──────────┴─────────────────┘

Each location has:
ADDRESS  → where the data is
VALUE    → what is stored there
```

---

## 2. Arrays vs. Linked Lists

### Arrays

- **Contiguous Memory:** All elements are stored **right next to each other** in sequential memory slots.
    
- **Memory Allocation Issues:** If you run out of space in an array and want to add an item, you may need to request a new, larger block of contiguous memory and **move the existing items there**.
    
- **Workaround ("Holding Seats"):** You can reserve extra memory slots in advance, though this risks wasting memory if unused or still overflowing if the input exceeds the reserved capacity.
    

### Visualisation: Array

```
ARRAY — CONTIGUOUS MEMORY

Address:
 1000       1004       1008       1012
   ↓          ↓          ↓          ↓

┌─────────┬─────────┬─────────┬─────────┐
│  Alice  │   Bob   │  Carol  │  David  │
└─────────┴─────────┴─────────┴─────────┘
 Index 0     Index 1    Index 2    Index 3

All elements sit next to each other in memory.
```

If we know the starting address and the size of each element:

```
address = base address + (index × element size)

Example:

base address  = 1000
element size  = 4 bytes
wanted index  = 2

address = 1000 + (2 × 4)
        = 1008

                    ↓
┌─────────┬─────────┬─────────┬─────────┐
│  Alice  │   Bob   │  CAROL  │  David  │
└─────────┴─────────┴─────────┴─────────┘
                         ↑
                  Directly accessed
```

Therefore, array random access is:

**O(1)**

---

### Linked Lists

- **Scattered Memory:** Elements can be located **anywhere in memory**.
    
- **Pointer Connections:** Each element contains its data value plus the **memory address of the next item in the list**.
    
- **Flexibility:** Adding an item can be fast—you place it in available memory and update the appropriate pointer.
    

### Visualisation: Linked List

```
Address 1000           Address 7820
┌──────────────┐       ┌──────────────┐
│ Alice        │       │ Bob          │
│ next: 7820 ──┼──────▶│ next: 4312 ──┼─────┐
└──────────────┘       └──────────────┘     │
                                            │
                                            ▼
                                      Address 4312
                                    ┌──────────────┐
                                    │ Carol        │
                                    │ next: 2096 ──┼────┐
                                    └──────────────┘    │
                                                        ▼
                                                  Address 2096
                                                ┌──────────────┐
                                                │ David        │
                                                │ next: NULL   │
                                                └──────────────┘
```

The nodes don't need to be physically next to each other.

The pointers create the logical sequence:

```
Alice ─────▶ Bob ─────▶ Carol ─────▶ David ─────▶ NULL
```

---

## 3. Operations & Access Types Comparison

### Random Access

Random access means jumping directly to an index.

Arrays support this because the computer can calculate the address:

```
Want element #3?

ARRAY

[ A ][ B ][ C ][ D ][ E ]
                  ↑
                  │
             jump directly
```

**Array access → O(1)**

---

### Sequential Access

Linked lists require following pointers one after another.

```
Want D?

START
  ↓
[ A ] → [ B ] → [ C ] → [ D ] → [ E ]
  1       2       3       4
                          ↑
                        FOUND
```

There is no direct jump to `D`.

In the worst case, the computer may traverse almost the entire list.

**Linked-list access → O(n)**

---

### Big O Performance Summary

|Operation|Arrays|Linked Lists|Explanation|
|---|---|---|---|
|**Reading by index**|**O(1)**|O(n)|Arrays calculate addresses directly; linked lists follow pointers.|
|**Insertion**|O(n)|**O(1)***|Arrays may shift elements; linked lists can update pointers.|
|**Deletion**|O(n)|**O(1)***|Arrays may shift remaining elements; linked lists can change links.|
|**Traversal**|O(n)|O(n)|Every element must be visited.|

* **Important:** O(1) linked-list insertion/deletion assumes you **already have the appropriate node/reference**. If you first have to search for the node, finding it can take O(n), making the overall operation O(n).

### Visualisation: Why Linked-List Deletion Can Be Fast

Before:

```
┌───┐      ┌───┐      ┌───┐      ┌───┐
│ A │ ───▶ │ B │ ───▶ │ C │ ───▶ │ D │
└───┘      └───┘      └───┘      └───┘
```

Delete `C`:

```
                 ┌───┐
              ╳▶ │ C │
             ╱   └───┘
            ╱
┌───┐      ┌───┐                 ┌───┐
│ A │ ───▶ │ B │ ──────────────▶ │ D │
└───┘      └───┘                 └───┘

Simply change B's pointer:

B.next = D
```

The physical data does not need to be shifted as it would in an array.

---

# 4. Selection Sort Algorithm

### How It Works

Selection sort builds a sorted list by repeatedly scanning the unsorted elements, finding the smallest remaining element, and placing it into the next sorted position.

### Visualisation: Selection Sort

Start with:

```
[ 5 ][ 3 ][ 6 ][ 2 ][ 10 ]
```

### Pass 1

Search everything:

```
[ 5 ][ 3 ][ 6 ][ 2 ][ 10 ]
  ↓    ↓    ↓    ↓     ↓

Smallest = 2
```

Move `2` into the first position:

```
 SORTED │       UNSORTED
        │
[ 2 ]   │ [ 3 ][ 6 ][ 5 ][ 10 ]
  ✓
```

### Pass 2

Find the smallest remaining element:

```
 SORTED │       UNSORTED
        │
[ 2 ]   │ [ 3 ][ 6 ][ 5 ][ 10 ]
              ↑
         smallest = 3
```

Result:

```
    SORTED    │    UNSORTED
              │
[ 2 ][ 3 ]    │ [ 6 ][ 5 ][ 10 ]
  ✓    ✓
```

### Pass 3

```
[ 2 ][ 3 ] │ [ 6 ][ 5 ][ 10 ]
                       ↑
                  smallest = 5

                     ↓

[ 2 ][ 3 ][ 5 ] │ [ 6 ][ 10 ]
  ✓    ✓    ✓
```

### Pass 4

```
[ 2 ][ 3 ][ 5 ] │ [ 6 ][ 10 ]
                         ↑
                    smallest = 6

                         ↓

[ 2 ][ 3 ][ 5 ][ 6 ] │ [ 10 ]
  ✓    ✓    ✓    ✓
```

### Finished

```
┌─────┬─────┬─────┬─────┬──────┐
│  2  │  3  │  5  │  6  │  10  │
└─────┴─────┴─────┴─────┴──────┘
   ✓     ✓     ✓     ✓      ✓

              SORTED
```

### Selection Sort Mental Model

```
UNSORTED LIST
      │
      ▼
┌──────────────────────┐
│ Find smallest item   │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Put it next in the   │
│ sorted portion       │
└──────────┬───────────┘
           │
           ▼
    Anything left?
       │       │
      YES      NO
       │       │
       └──↺    ▼
             DONE
```

---

## 5. Why Selection Sort is O(n²)

Finding the smallest element requires scanning the unsorted portion.

The amount of searching decreases on every pass:

```
Pass 1    ██████████    n
Pass 2    █████████     n - 1
Pass 3    ████████      n - 2
Pass 4    ███████       n - 3
Pass 5    ██████        n - 4
  ⋮           ⋮
Last      █             1
```

So the total work is approximately:

[  
n+(n-1)+(n-2)+...+1  
]

This equals:

[  
\frac{n(n+1)}{2}  
]

Expanding:

[  
\frac{n^2+n}{2}  
]

For large values of (n), the (n^2) term dominates.

Big O ignores constants and lower-order terms:

[  
O\left(\frac{n^2+n}{2}\right)  
\rightarrow  
\boxed{O(n^2)}  
]

### Visual Intuition for Quadratic Growth

```
Input size             Approximate n² work

n = 10                 100
                       ██

n = 100                10,000
                       ██████████

n = 1,000              1,000,000
                       ████████████████████
```

If the input grows **10×**, an O(n²) algorithm performs approximately **100× as much work**.

[  
(10n)^2=100n^2  
]

This is why quadratic algorithms become problematic as datasets become large.

---

## 6. Key Takeaways

### Arrays

```
CONTIGUOUS MEMORY
        ↓
FAST RANDOM ACCESS
        ↓
       O(1)
```

Use arrays when your workload benefits from frequent indexed/random access.

### Linked Lists

```
SCATTERED NODES
        ↓
CONNECTED BY POINTERS
        ↓
FAST LOCAL INSERT/DELETE
WHEN POSITION IS ALREADY KNOWN
```

Linked lists trade random-access performance for flexible pointer-based insertion and deletion.

### Selection Sort

```
Find smallest
     ↓
Place it
     ↓
Find next smallest
     ↓
Place it
     ↓
Repeat
     ↓
SORTED

Repeated O(n) searches
        ×
approximately n passes
        ↓
      O(n²)
```

### Core Engineering Lesson

Choosing a data structure is a **trade-off decision**.

Don't ask only:

> “Which data structure is fastest?”

Ask:

> **“Which operations does my application perform most frequently?”**

Then reason:

```
REQUIREMENTS
     ↓
COMMON OPERATIONS
     ↓
DATA STRUCTURE
     ↓
TIME / SPACE COMPLEXITY
     ↓
TRADE-OFFS
```

Arrays and linked lists are foundational structures underlying more advanced structures and abstractions such as hash tables, queues, stacks, and various tree structures.