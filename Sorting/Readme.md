# Sorting Algorithm

A Sorting algorithm is used to arrange elements of an array/lst in a specific
order. For example, ![Sorting an Array](./images/1-sorting.png)

Here, we are sorting the array in ascending order.

There are various sorting algorithms that can be used to complete this
operation. And, we can use any algorithm based on the requirement.

- Bubble Sort
- Selection Sort
- Insertion Sort
- Merge Sort
- Quicksort
- Counting Sort
- Radix Sort
- Bucket Sort
- Heap Sort
- Shell Sort

## Complexity of Sorting Algorithms

The efficiency of any sorting algorithms is determined by the **time
complexity** and **space complexity** of the algorithm.

**1. Time Complexity:** Time complexity refers to the time taken by an algorithm
to complete its execution with respect to the size of the input. It can be
represented in different forms:

- Big-O notation(O)
- Omega notation (Ω)
- Theta notation (Θ)

**2. Space Complexity:** Space complexity referse to the total amount of memory
used by the algorithm for a complete execution. It includes both the auxiliary
memory and the input.

The auxiliary memory is the additional space occupied by the algorithm apart
from the input data. Usually, auxiliary memory is considered for calculation the
space complexity of an algorithm.

| Sorting Algorithm | Time Complexity - Best | Time Complexity - Worst | Time Complexity - Average | Space Complexity |
| ----------------- | ---------------------- | ----------------------- | ------------------------- | ---------------- |
| Bubble Sort       | n                      | n<sup>2</sup>           | n<sup>2</sup>             | 1                |
| Selection Sort    | n<sup>2</sup>          | n<sup>2</sup>           | n<sup>2</sup>             | 1                |
| Insertion Sort    | n                      | m<sup>2</sup>           | n<sup>2</sup>             | 1                |
| Merge Sort        | nlog n                 | nlog n                  | nlog n                    | n                |
| Quicksort         | nlog n                 | n<sup>2</sup>           | nlog n                    | log n            |
| Counting Sort     | n+k                    | n+k                     | n+k                       | max              |
| Redix Sort        | n+k                    | n+k                     | n+k                       | max              |
| Bucket Sort       | n+k                    | n<sup>2</sup>           | n                         | n+k              |
| Heap Sort         | nlog n                 | nlog n                  | nlog n                    | 1                |
| Shell Sort        | nlog n                 | n<sup>2</sup>           | nlog n                    | 1                |

## Stability of Sorting Algorithm

A sorting algorithm is considered stable if the two or more items with the same
value maintain the same relative position even after sorting.

For example, in the image below, there are two items with the same value 3. An
unstable sorting algorithm allows two possibilities where the two positions of 3
may or may not be maintained.
![Unstable Sorting](./images/2-unstable-sorting.png)

However, after a stable sorting algorithm, there is always one possibility where
the position are maintained as in the original array.
![Stable Sorting](./images/3-stable-sorting.png)

Here's a table howing the stability of different sorting algorithm.

| Sorting Algorithm | Stability |
| ----------------- | --------- |
| Bubble Sort       | Yes       |
| Selection Sort    | No        |
| Insertion Sort    | Yes       |
| Merge Sort        | Yes       |
| Quicksort         | No        |
