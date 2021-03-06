# Data Structures and Algorithms

## Data Structures

- Data structure is a systematic way of organizing and accessing data.

### Array

- An ordered collection of data.
- It has indices for access the elements, usually starts at 0 from left to right.
- It has a fixed size, defined when the array is declared.

### List

- like an array but its size can be changed after the declaration.
- The first element in the list has index = 0.
- Every element on the list other than the first has a predecessor.
- Every element on the list other than the last has a successor.

#### Array List

- They are Lists data structures designed base on array data structures.
- Also known as vector in C++ or earliest versions of Java.
- It internally declares a new array everything when the list size changes.
- Dynamic array is a technique used to improve the data structure. It always declares some empty elements on both sides of the array to lower the chances for creating and copying the array, every time the array change sizes.
- It uses contiguous allocation, list elements occupy consecutive memory locations.
  - Insertion or deletion of elements in the middle of the list involves the laborious relocation of all elements that come after.
- It allows random access access elements by jumping to any given element without going through its predecessors.

#### Linked List

- A type of list that treats all of its elements as nodes.
- The nodes not only has the value for the element, it also stores a reference(link) to its adjacent elements.
- The reference to a linked list is just the reference to the head node.
- It uses linked allocation.
- It uses sequential access, it accesses nodes starting from the head all the time.
- This type of data structure is referred to a self-referential structure or recursive data structure.
- An empty list is represented with a head reference whose value is null.
- Link Lists have the following types:
  - Singly Linked Lists - All of its node has a reference to the next node of the list.
    - The first node is called the head, the last node is call the tail.
    - The tail node has a null reference.
  - Circularly Linked Lists - When a singly linked list has its tail node reference to the head node, the head and the tail are connected to form a circularly linked list.
  - Doubly Linked Lists - All of its node not only has a reference to the next node, but also has a reference to the previous node.
    - provide easy access to both side of certain node.
    - There is header node at the beginning and tailer node at the end.
    - Header node and tailer node do not store data. Together, they are called sentinels or guards, to protect the boundary, because either next node or previous node of the sentinels are not defined.
- Removing Nodes
  - To remove the first node of a list, set the head reference to its successor.
  - To remove a node other than the first, set a reference to the predecessor of the targeted node. Route the successor link in the predecessor around the targeted node.

#### Positional List

- It uses a cursor instead of indices to locate each elements.

### Stack

- It is a collection of objects are inserted and removed according to the last-in, first-out principle.
- It is originated from a stack of plates in a spring-loaded, cafeteria plate dispenser.
- Inserting data is called push, removing data is called pop.
- A stack can be implemented by using an array to hold the items being stored.
  - need a variable called `top` which stores the end index(the first empty slot) for the stack in the array.
  - The exception thrown when an attempt is made to push a value onto a stack whose array if full is called a stack overflow exception.
  - The exception thrown when an attempt is made to pop an empty stack is sometimes called stack underflow.
- ArrayList can be used to create a generic stack structure.
- A linked list can be used to implement a stack by using the head node object of the list as the "top" of the stack.

### Queue

- Queues are first-in, first-out. It has a first come, first server principle.
- Adding data to the `rear` is called enqueue, removing data from the `front` is call dequeue.
- For an array-based implementation, it should:
  - track the front and rear of the array. Adding new elements and removing old elements in order of increasing index.
  - wrap around to the beginning of the array when the queue reaches the end.
  - Use an integer variable to track the size.
- A linked list can be used to implement a queue.
  - The head of the linked list is used as the front of the queue.
  - The end of the linked list is used as the rear of the queue.

#### Priority Queue

- A queue that has all of its element with a priority key.
- When dequeuing an element the priority key is considered first. Then, among all the elements with the highest priority, first-in, first-out.
- The key can be called minimal key. When represented by an integer, usually a lower number has a higher priority.

### Deck

- It also known as double-ended queues.
- It supports insertion and deletion at both the front and the end of the queue.

### Tree

- It stores objects in a hierarchical structure, like a tree.
- The top node is called the root.
- Each node(except root) has one parent node, and zero or more child node.
- All nodes with a common parent are called siblings.
- A node is called internal if it has a child node.
- A node is called external or leaf if it has no child node.
- An edge of a tree is a pair of a node with parent and child relationship, the order does not matter.
- A path of a tree is a serial of nodes with direct parent and child relationships.
- The depth is used to describe how many levels a node is below the root node.
- The height is used to describe the max depth among all nodes for a tree.
- The subtree is generated by treating a tree's node as the root of a new tree.
- nodes on one the same path have the ancestor and descendant relationship.

#### Ordered Tree

- A tree structure that place all the sibling nodes in an order.

#### Binary Tree

- All of the nodes have at most two children.
- The children of the nodes are described as the left child and the right child.
  - The left child may be a root of a left subtree, the same for the right child.
- The children are ordered as the left child is the first child.
- For a proper binary tree, all of its internal nodes have two children. Otherwise, it can be called an improper binary tree.
- Traversal of a tree is a way of access all nodes of a tree.
- It can be implemented using the same concept as a linked-list. Each node will have a value and two links to the left child node and right child node.
  - A binary tree is represented by a reference to its root node.
  - An empty binary tree is represented with a reference whose value is null.
- There are three recursive traversal techniques for binary tree:
  - `Preorder traversal` - visits the root first, and then recursively traverses the left and right subtrees.(recursive methods for left and right subtree run last)
  - `Inorder traversal` - traverses the left subtree, then visits the root, and then traverses the right subtree.(recursive methods for left subtree run first, recursive methods for right subtree run last)
    - traverses in a sorted order, from smallest to largest.
  - `Postorder traversal` - traverses the left and right subtrees, and then visits the root.(recursive methods for left and right subtree run first)
- Application of binary tree:
  - `Binary Search Tree` - Used in many search applications where data is constantly entering/leaving, such as the map and set objects in many languages' libraries.
    - Left child is always smaller than the root, Right child is always bigger than the root.
    - To implement the binary search tree, adding and searching methods are recursive with base cases that check if the root is empty and non-base case that traverses the tree.
    - To remove a node in the binary search tree. There are three cases:
      - Removal of a Leaf Node
      - Removal of a Node with a single Child
      - Removal of a node with two child node
        - For this case, the node will be replaced by the largest node from its left subtree. Then, reorganinze the rest.
  - `Binary Space Partition` - Used in almost every 3D video game to determine what objects need to be rendered.
  - `Binary Tries` - Used in almost every high-bandwidth router for storing router-tables.
  - `Hash Trees` - used in p2p programs and specialized image-signatures in which a hash needs to be verified, but the whole file is not available.
  - `Huffman Coding Tree` - used in compression algorithms, such as those used by the .jpeg and .mp3 file-formats.
  - `Syntax Tree` - Constructed by compilers and (implicitly) calculators to parse expressions.
  - `T-tree` - Though most databases use some form of B-tree to store data on the drive, databases which keep all (most) their data in memory often use T-trees to do so.

#### Heap

- It can be used to improve the performance of a priority queue.
- It is a binary that stores a key and a value in all of its nodes.
- It also need to satisfy the following requirement.
  - The child node key is always greater or equal to its parent node key.
  - Except the nodes with the highest depth of the tree, all nodes have two children(full). This guarantee the tree has minimal height.

### Maps

- It has a collection of key-value pairs(also called entries or mapping).
- Key can be of any data type, and they are unique.
- It is also known as associative arrays.
- The key and value are generally not stored in the same object.

#### Hash table

- A structure that help implement maps.
- In a hash table all possible keys in a map can found its associated integer values in the table.
- It use hash function or hash algorithm is consist of hash code and compression function.
  - Hashcode finds or converts the integer value of all keys in the ordered hash table.
    - A good hash code can avoid getting the same integer value as much as possible(avoid collisions).
    - For Integer objects, you can use the integer value of the object (or its absolute value).
    - For Character objects, you can use the UNICODE value for the character.
    - For String objects, you can use a function that takes into account the UNICODE values of the characters that make up the string, as well as the position occupied by each character.
    - For Object types, you can use some function on the non-mutable components of the object.
  - Compression function generate and rearrange the new collection that has the same length as the map.

#### Multimap

- They are maps that allows a key maps to multiple values.

#### Linked Map

- A ordered map.
- Generally based on the insertion order.

### Set

- A unordered collection of elements, contains unique values only.
- Support membership operation for sets defined in Math.
- Internally Set are treated as Keys of a map.
- The hash function for HashSet has the following features.
  - Elements are usually broken down into groups by the compression function, then they are stored in an array of bucket.
  - Each bucket can have an array of element for the same group.
  - Each bucket has an array of elements with the same length.

#### Multiset

- Also known as bag, are set that allow duplicated values.

#### Linked Set

- An ordered Set.
- Generally based on the insertion order.

## Algorithm

- An algorithm is a step-by-step procedure for performing some task in a finite amount of time.
- Shorter running time is the major indication of a better data structure or algorithm.

### Iteration

- A method that called repeatedly in a loop.

### Recursion

- A method that calls itself is a recursive method.
- It has a base case, the method will called itself until the base case is reached and solved.
- Recursive methods can have the following types:
  - Linear Recursion - Each recursive method call itself once.
  - Binary Recursion - Each recursive method call itself twice.
  - Multiple Recursion - Each recursive method call itself more than twice.
- For binary and multiple recursion, the methods call itself as deep as possible than call the sibiling methods after all its recursive methods are called.

### Algorithm Analysis

It is used to tell if a data structure or Algorithm is good.

- Experimental studies, run methods, output current time before and after the operation, calculate and record the elapsed time for comparison. All irrelevant conditions are controlled.

  - Different elapsed time may obtained among identical tests due to background services of the testing device.
  - the biggest issue with experimental analysis is the Algorithm must be completed for testing.
  - IDEs like NetBeans contains a profiler that will indicate the amount of time spent in each function and on what lines in a function.

- Counting Primitive Operations, an algorithm can be measured by counting the following primitive operations it has:

  - Assigning a value to a variables
  - Following an object reference
  - Performing an arithmetic operation
  - Comparing two numbers
  - Accessing a single element of an array by index
  - Method overhead
    - Calling a method - allocate memory for parameters and local variables
    - Returning from a method - store the address of where control returns after the method terminates.

- Asymptotic Analysis
  - A computational problem is a problem that is meant to be solved by an algorithm.
  - A computational problem is described by specifying the data to be input to the algorithm, and the output that should be produced by the algorithm
  - Each possible input is called an instance of the problem. For analysis the instance size `N` is only taken into consideration.
  - There are two types of complexity:
    - the time complexity is the computational complexity that describes the amount of time it takes to run an algorithm.
    - Space complexity is a measure of the amount of working storage an algorithm needs.

#### Time Complexity

- Generally larger input run slower.
- This method focus on studying the growth rate of primitive operation count related to the growth of input size.
- When convert operation count into running time. For inputs with the same sizes, running time may vary. However, the worst-case is usually taken as the running time for this input size. It is good for code improvement.
- For logarithm function in computer science, the 2 in base 2 is often omitted. It looks similar to LOG with base 10.
- The Big O math model is used to simplify operation count functions for comparison.
  - A function `f(x)` can be converted to the big-Oh of another function `g(x)`. if the y value of `f(x)` is always smaller or equal than `g(x)` times a constant for all x value greater than certain constant.
    - Then the generalized big-Oh function can be used to represent the complexity of the algorithm.
    - In terms of the complexity, `O(1)<O(log(n))<O(n)<O(nlog(n))<O(n^2)<O(2^n)<O(n!)`.
    - `O(1)` Constant Time: means the number of operations has no thing to do with input size.
    - `O(n)` Linear Time: means the number of operations is linear input size.
    - `O(log n)` Logarithmic Time: means the input size is equals 2 to the power of the number of operations.
    - `O(n log n)` usually means a `O(log n)` algorithm has an `O(n)` as its inner loop or outer loop.
    - `O(n^2)` Quadratic Time: means the number of operations is equals the input size times itself.
    - When finding Big O, `g(x)` should be in its simplest form.
  - Big-Omega function is found if `f(x)` is greater or equal than `g(x)` time constant `c`.
  - Big-Theta is found if `f(x)` can be in between a function `g(x)` times two different constant.

### Search Algorithm

- A search algorithm is a method of locating a specific item in a larger collection of data.
- This type of algorithm is referred to as "Brute Force" as potentially all elements need to be visited.

#### Sequential Search

- It use a loop to: sequentially step through an array.
- compare each element with the search value
- stop when the value is found or the end of the array is encountered.
- It can be used with any array.
- Sequential Search searches from one end to another end, it has the following two types.
  - findFirst return the index for the first found value, -1 if not found. Worst case `O(n)`.
  - findAll - When X is found record the position and continue. At the end of the array return all the positions. If X is never found, return an empty list of position, for all cases `O(n)`.

#### Binary Search

- It can only be used with sorted arrays, but is much faster than Sequential Search.
- Steps for binary search:
  1. compare target value with the median values(round down if the mid position is not an integer). check equality first, if not determine the location the target in either upper or lower section
  2. compare the target with the median of the lower or upper section until it is found.
- Example of Recursive Binary Search:
  ```java
  int binarySearch(int A[], int lower, int upper, int X){
    // check base case for missing X
    if (lower > upper)
      return -1;
    // check if X is at the middle
    int middle = (lower + upper)/2;
    if (A[middle] == X)
      return middle;
    // determine which segment to continue search in
    if (A[middle] < X)
      return binSearch(A, middle+1, upper, X);
    else
      return binSearch(A, lower, middle-1, X);
  }
  ```
- Worst case `O(logN)`.

### Sort

An array is sorted in ascending order if the array entries increase as indices increase.

#### Bubble Sort

- Steps for bubble sort:
  1. compare each value(from left to right one by one) with its next value to the right.
  2. when a bigger value is found, always swap the bigger one to the right, so one biggest value in each iteration should be places the end.
  3. Exclude the value found in the previous iteration by shorten the length of the loop by one
  4. repeat the process n times for n is the number of input.
- The complexity of Bubble Sort is `О(n^2)` (worst case).
- Example:
  ```java
  for (int last=N-1; last>=1; last--){
    // Move the largest entry in A[0...last] to A[last]
    for (int index=0; index <= last-1; index++){     //swap adjacent elements if necessary
      if (A[index] > A[index+1]){
        int temp = A[index];
        A[index] = A[index+1];
        A[index + 1] = temp;
      }
    }
  }
  ```

#### Selection Sort

- Steps for Selection sort:
  1. Reset the leftmost element as the temp max value.
  2. Comparing the temp max value with rest values in the array. If a bigger one is found, set it as the temp max value.
  3. After the comparison in one iteration, swap the max value to its proper location according to a count number that count the rank of the max value of each iteration.
- The time complexity of Selection Sort is `О(n^2)`(worst case).
- Example:
  ```java
  for (last = N -1; last >= 1; last --)
  {
    // Move the largest entry in A[0...last] to A[last]
    // Determine position of largest in A[0..last] and store
    // in maxIndex
    int maxIndex = 0;
    for (int index = 1; index <= last; index++)
    {
      if (A[index] > A[maxIndex])
      maxIndex = index;
    }
    // maxIndex is position of largest in A[0..last]
    // swap A[maxIndex] with A[last]
    int temp = A[maxIndex];
    A[maxIndex] = A[last];
    A[last] = temp;
  }
  ```

#### Insertion Sort

- Steps for insertion sort:
  1. From left to right, starting with the second element, compare it with the first if it is smaller or equals to the first, place it before the first element.
  2. For the third element, compare it with the second, then the first. If the third is smaller than or equals with any element, place it before it.
  3. repeat the process to the last element. In the end all elements are placed into the right location.
- The complexity of Insertion Sort is `О(n^2)` (worst case).
- Example:
  ```java
  //A[0..0] is sorted
  for (index = 1; index <= N-1; index ++)
  {
    // A[0..index-1] is sorted
    // insert A[index] at the right place in A[0..index]
    int unSortedValue = A[index];
    scan = index;
    while (scan > 0 && A[scan-1] > unSortedValue)
    {
      A[scan] = A[scan-1];
      scan --;
    }
    // Drop in the unsorted value
    A[scan] = unSortedValue;
    // Now A[0..index] is sorted
  }
    // Now A[0..N-1] is sorted, so entire array is sorted
  ```

#### Merge Sort

- Steps for merge sort:
  1. treat the array as n arrays, each has a length of one.
  2. create new n/2 arrays, the length of each array is doubled.
  3. compare elements in each array, and place them in order.
  4. create n/4 arrays, merge the n/2 arrays into n/4 array in order.
  5. repeat the process until merging into n/n arrays which is one big sorted array.
- The complexity of Merge Sort is `O(nlog(n))` (worst case).
- Since each compared value is copied to the new array, the merge sort does require new temporary arrays.

#### Quick Sort

- Steps for quick sort:
  1. Set a Pivot point(usually the middle point).
  2. Compare pivot point with rest of the array, move all smaller value to the left and greater values or equal value to the right. Then the pivot point has the sorted index location.(This step is called Partition).
  3. Do the same procedure for the left and right sublists. Get two more sorted points.
  4. Repeat until all sublists has a length of 1 or 0.
- The complexity of Quick Sort is `О(n^2)` (worst case).
- Example:

```java
void doQuicksort(int A[], int start, int end)
{
  if (start < end)
  {
    // partition A[start..end]
    // and get the pivot point
    int pivotPoint = partition(A, start, end);
    // recursively do the first sublist
    doQuicksort(A, start, pivotPoint-1);
    // recursively do the second sublist
    doQuicksort(A, pivotPoint+1, end);
  }
}
int partition(int A[ ], int start, int end)
{
  // See implementation for improved midpoint selection
  int pivotValue = A[start];
  endOfLeftList = start;
  // At this point A[endOfLeftList] == pivotValue
  for (int scan = start + 1; scan <= end; scan ++)
  {
    if (A[scan] < pivotValue)
    {
      endOfLeftList++;
      swap(A, endOfLeftList, scan);
      // At this point A[endOfLeftList] < pivotValue
    }
  }
  // Move the pivotValue between the left and right sublists
  swap(A, start, endOfLeftList);
  return endOfLeftList;
}
```
