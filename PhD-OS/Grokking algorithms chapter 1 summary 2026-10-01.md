## what is an algorithm? ##

A set of instructions for accomplishing a task. you usually want techniques that solves complex problems, are  fast , efficient or all 3.

## Binary search algorithm ##

Accepts a list of sorted items as input and returns the index of an element if it's present else null or none (python). ==It only works on sorted list==

*How it works*
It guesses the middle element of a sorted list and eliminates half of the remaining items with every step. 
Simple search or linear search in comparison searches items sequentially from the beginning eliminating one element per step or guess


## Performance comparison ##

- Simple search requires a linear time (O(n)) : up to n steps to get to the item of interest in the worst case
- Binary search requires a Logarithmic time (O(log n)) : up to O log n steps at most


## Execution examples ##

- 100 items; simple search up to 100 guesses, binary takes at most 7 guesses
- 240000 items (eg dictionary) 240000 guesses in simple search, at most 18 guesses for binary search

## Big O Notation ##

- measures the speed in terms of the growth rate of operations as the input size expands 
- Does not measure actual clock time in seconds
- Worst case scenario: establishes an upper-bound reassurance ensuring that the algorithm will never be slower than its worst-case run time.
- Ignoring constants : Constant values (added, subtracted, divide or multiplied) are dropped in Big O notation(e.g O(n/26) is O(n))

## 5 Common Big O run times (fastest to slowest) ##

- $O (log n)$ Logarithmic time e.g Binary search
- $O (n)$ Linear time e.g simple search
- $O (n log n)$ e.g fast sorting algorithms like quick sort
-  $O (n^2)$  Quadratic time e.g slow sorting algorithms like selection sort
- $O (n !)$ Factorial time : e.g extremely slow sorting algorithms like the travelling salesman problem


## Key takeaways ##

- An algorithms efficiency is measured by how rapidly the number of operations grow as input grows
- As datasets grow larger, logarithmic algorithms  ($O (log n$)) become vastly faster than linear algorithms ($O (n)$)

## Question ##

-  Why is Big O notation expressed in terms of the number of operations instead of measuring speed in seconds?

## Answer 

- Big O notation measures how quickly the running time of an algorithm increases as the size of the input increases, rather than its absolute speed. Using seconds is unreliable because different hardware configurations have different processing speeds, whereas counting operations provides a consistent way to compare the growth rates of algorithms.

### Explanation

- The focus of Big O is the relationship between input size and growth in operations, which remains constant across different hardware, unlike execution time in seconds.