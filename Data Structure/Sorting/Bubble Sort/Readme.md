# Bubble Sort

**Bubble sort** is a sorting algorithm that compares two adjacent elements and
swaps them until they are in the intended order.

## Working of Bubble Sort

Suppose we are trying to sort the elements in **ascending order**.

**1. First Iteration (Compare and Swap)**

1. Starting from the first index, compare the first and the second elements.
2. If the first element is greater than the second element, they are swapped.
3. Now, compare the second and the third elements. Swap them if they are not in
   order.
4. The above process goes on until the last element.

![Compare the Adjacent Elements](./images/1-Bubble-sort-0.png)

**2. Remaining Iteration** The same process goes on for the remaining
iterations.

After each iteration, the largest element among the unsorted elements is placed
at the end.

![Compare the Adjacent Elements](./images/2-Bubble-sort-1.png)

In each iteration, the comparison takes place up to the last unsorted element.

![Compare the Adjacent Elements](./images/3-Bubble-sort-2.png)

The array is sorted when all the unsorted elements are placed at their correct
positions.

![Compare the Adjacent Elements](./images/4-Bubble-sort-3.png)

## Bubble Sort Algorithm

```
bubbleSort(array)
    for i <- 1 to sizeOfArray - 1
        for j <- 1 to sizeOfArray = 1 = i
            of leftElement > rightElement
                swap leftElement and rightElement
end bubbleSort
```
