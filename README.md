a. Heapsort Algorithms
Heapify: Ensures that a subtree is a heap.

Build Max-Heap: Builds a max-heap from the unsorted array.

Heap Sort: Sorts the array by repeatedly extracting the maximum element and re-heapifying the remaining elements.

b. Analysis of Algorithms
Heapify:

Time Complexity: O(log n) because it deals with the height of the heap.

Space Complexity: O(1) as it's an in-place algorithm.

Build Max-Heap:

Time Complexity: O(n) because we are heapifying n elements in a tree.

Space Complexity: O(1) as it works in-place.

Heap Sort:

Time Complexity: O(n log n) because we build the heap (O(n)) and then perform n-1 heapify operations (O(log n)).

Space Complexity: O(1) as it is an in-place sorting algorithm.
