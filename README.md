```markdown
# Introductory Guide to Data Structures in Python

This is a comprehensive overview with practical examples of fundamental data structures and algorithms implemented in Python. It is designed to help users understand the core concepts and applications of various data structures.

## Table of Contents
1. [Arrays & Linked Lists](#arrays--linked-lists)
2. [Heap & Stack](#heap--stack)
3. [Binary Search](#binary-search)
4. [Recursion](#recursion)
5. [Sorting Algorithms](#sorting-algorithms)
6. [Conclusion](#conclusion)

## 1. Arrays & Linked Lists

### Arrays
- **Definition:** A collection of elements stored in contiguous memory locations.
- **Characteristics:**
  - Fixed size.
  - Fast access by index.
- **Example:**
  ```python
  arr = [1, 2, 3, 4, 5]
  print(arr[0])  # Access the first element
  ```

### Linked Lists
- **Definition:** A sequence of nodes, where each node contains data and a reference to the next node.
- **Characteristics:**
  - Dynamic size.
  - Efficient insertion and deletion, with slower access.
- **Example:**
  ```python
  class Node:
      def __init__(self, data):
          self.data = data
          self.next = None

  class LinkedList:
      def __init__(self):
          self.head = None

      def append(self, data):
          new_node = Node(data)
          if not self.head:
              self.head = new_node
              return
          last = self.head
          while last.next:
              last = last.next
          last.next = new_node

      def print_list(self):
          current = self.head
          while current:
              print(current.data)
              current = current.next

  ll = LinkedList()
  ll.append(1)
  ll.append(2)
  ll.print_list()  # Output: 1 2
  ```

## 2. Heap & Stack

### Heap
- **Definition:** A specialized tree-based data structure that adheres to the heap property.
- **Characteristics:**
  - Can be a Max Heap (parent node > child nodes) or Min Heap (parent node < child nodes).
- **Example:**
  ```python
  import heapq

  heap = []
  heapq.heappush(heap, 10)
  heapq.heappush(heap, 30)
  heapq.heappush(heap, 20)
  print(heap)  # Output: [10, 30, 20]
  ```

### Stack
- **Definition:** A linear data structure that follows the Last In, First Out (LIFO) principle.
- **Characteristics:**
  - Operations: Push (add), Pop (remove), Peek (view top element).
- **Example:**
  ```python
  stack = []

  stack.append(1)  # Push
  stack.append(2)
  print(stack.pop())  # Pop, Output: 2
  ```

## 3. Binary Search
- **Definition:** An efficient algorithm for locating an item in a sorted list.
- **Characteristics:**
  - Time complexity: O(log n).
  - Requires a sorted array.
- **Example:**
  ```python
  def binary_search(arr, x):
      low, high = 0, len(arr) - 1
      while low <= high:
          mid = (low + high) // 2
          if arr[mid] == x:
              return mid
          elif arr[mid] < x:
              low = mid + 1
          else:
              high = mid - 1
      return -1

  arr = [1, 2, 3, 4, 5]
  print(binary_search(arr, 3))  # Output: 2
  ```

## 4. Recursion
- **Definition:** A technique where a function solves a problem by calling itself with smaller instances of the same problem.
- **Characteristics:**
  - Requires a base case to terminate recursion.
- **Example: Calculating factorial.**
  ```python
  def factorial(n):
      if n == 1:
          return 1
      else:
          return n * factorial(n-1)

  print(factorial(5))  # Output: 120
  ```

## 5. Sorting Algorithms

### Bubble Sort
- **Definition:** A straightforward comparison-based sorting algorithm.
- **Characteristics:**
  - Time complexity: O(n^2).
  - Repeatedly swaps adjacent elements if they are out of order.
- **Example:**
  ```python
  def bubble_sort(arr):
      n = len(arr)
      for i in range(n):
          for j in range(0, n-i-1):
              if arr[j] > arr[j+1]:
                  arr[j], arr[j+1] = arr[j+1], arr[j]
      return arr

  arr = [5, 1, 4, 2, 8]
  print(bubble_sort(arr))  # Output: [1, 2, 4, 5, 8]
  ```

## Conclusion
- **Arrays:**
  - Fixed size and fast access by index.
  - Suitable for situations where the dataset size is known in advance.

- **Linked Lists:**
  - Dynamic size with efficient insertion and deletion.
  - Better suited for scenarios with frequent size changes.

- **Heaps:**
  - Specialized tree structure with heap properties (Max or Min).
  - Ideal for priority queues and efficient retrieval of min/max elements.

- **Stacks:**
  - Follows Last In, First Out (LIFO) principle.
  - Useful for reversible operations like undo actions or parsing expressions.

- **Binary Search:**
  - Efficient search method for sorted arrays with O(log n) complexity.
  - Requires sorted data for optimal performance.

- **Recursion:**
  - Technique for solving problems by breaking them into smaller sub-problems.
  - Effective for hierarchical problems but may lead to performance issues if not managed carefully.

- **Bubble Sort:**
  - Basic comparison-based sorting algorithm with O(n^2) complexity.
  - Simple to implement but inefficient for large datasets; alternative algorithms offer better performance.
```
