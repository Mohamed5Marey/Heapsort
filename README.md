A. Heapsort Algorithms

Heapify: Ensures that a subtree is a heap.

Build Max-Heap: Builds a max-heap from the unsorted array.

Heap Sort: Sorts the array by repeatedly extracting the maximum element and re-heapifying the remaining elements.

B. Analysis of Algorithms

Heapify:

* Time Complexity: O(log n) because it deals with the height of the heap.

* Space Complexity: O(1) as it's an in-place algorithm.

Build Max-Heap:

* Time Complexity: O(n) because we are heapifying n elements in a tree.

* Space Complexity: O(1) as it works in-place.

Heap Sort:

* Time Complexity: O(n log n) because we build the heap (O(n)) and then perform n-1 heapify operations (O(log n)).

* Space Complexity: O(1) as it is an in-place sorting algorithm.

c. Implementation in Python
Here’s the full implementation combining the above algorithms:

#include <iostream>
using namespace std;

void heapify(int arr[], int n, int i) {
    int largest = i;
    int left = 2 * i + 1;
    int right = 2 * i + 2;

    if (left < n && arr[left] > arr[largest])
        largest = left;

    if (right < n && arr[right] > arr[largest])
        largest = right;

    if (largest != i) {
        swap(arr[i], arr[largest]);
        heapify(arr, n, largest);
    }
}

void buildMaxHeap(int arr[], int n) {
    int startIdx = (n / 2) - 1;
    for (int i = startIdx; i >= 0; i--) {
        heapify(arr, n, i);
    }
}

void heapSort(int arr[], int n) {
    buildMaxHeap(arr, n);
    for (int i = n - 1; i > 0; i--) {
        swap(arr[0], arr[i]);
        heapify(arr, i, 0);
    }
}

void printArray(int arr[], int n) {
    for (int i = 0; i < n; ++i)
        cout << arr[i] << " ";
    cout << endl;
}

int main() {
    int arr[] = { 12, 11, 13, 5, 6, 7 };
    int n = sizeof(arr) / sizeof(arr[0]);

    heapSort(arr, n);

    cout << "Sorted array is: \n";
    printArray(arr, n);
}


