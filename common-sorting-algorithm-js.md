1. Bubble Sort:

```javascript
function bubbleSort(arr) {
  const len = arr.length;
  for (let i = 0; i < len - 1; i++) {
    for (let j = 0; j < len - 1 - i; j++) {
      if (arr[j] > arr[j + 1]) {
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
      }
    }
  }
  return arr;
}

const array = [5, 3, 8, 4, 2];
console.log(bubbleSort(array)); // Output: [2, 3, 4, 5, 8]
```

Explanation: Bubble sort works by repeatedly swapping adjacent elements if they are in the wrong order. It iterates over the array multiple times, comparing each element with its adjacent element and swapping them if necessary. In each iteration, the largest element "bubbles" up to its correct position at the end of the array. The process is repeated until the entire array is sorted. The time complexity of bubble sort is O(n^2) in the worst case.

2. Selection Sort:

```javascript
function selectionSort(arr) {
  const len = arr.length;
  for (let i = 0; i < len - 1; i++) {
    let minIndex = i;
    for (let j = i + 1; j < len; j++) {
      if (arr[j] < arr[minIndex]) {
        minIndex = j;
      }
    }
    if (minIndex !== i) {
      [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]];
    }
  }
  return arr;
}

const array = [5, 3, 8, 4, 2];
console.log(selectionSort(array)); // Output: [2, 3, 4, 5, 8]
```

Explanation: Selection sort works by repeatedly finding the minimum element from the unsorted part of the array and swapping it with the element at the beginning of the unsorted part. It maintains two subarrays: the sorted part on the left and the unsorted part on the right. In each iteration, it finds the minimum element from the unsorted part and swaps it with the first unsorted element. The sorted part grows from left to right until the entire array is sorted. The time complexity of selection sort is O(n^2) in the worst case.

3. Insertion Sort:

```javascript
function insertionSort(arr) {
  const len = arr.length;
  for (let i = 1; i < len; i++) {
    const key = arr[i];
    let j = i - 1;
    while (j >= 0 && arr[j] > key) {
      arr[j + 1] = arr[j];
      j--;
    }
    arr[j + 1] = key;
  }
  return arr;
}

const array = [5, 3, 8, 4, 2];
console.log(insertionSort(array)); // Output: [2, 3, 4, 5, 8]
```

Explanation: Insertion sort works by dividing the array into a sorted and an unsorted part. It iterates over the unsorted part, comparing each element with the elements in the sorted part and inserting it into its correct position. It shifts the elements greater than the current element to the right to make space for the insertion. The sorted part expands by one element in each iteration until the entire array is

sorted. The time complexity of insertion sort is O(n^2) in the worst case.

4. Merge Sort:

```javascript
function mergeSort(arr) {
  if (arr.length <= 1) {
    return arr;
  }

  const mid = Math.floor(arr.length / 2);
  const left = mergeSort(arr.slice(0, mid));
  const right = mergeSort(arr.slice(mid));

  return merge(left, right);
}

function merge(left, right) {
  const merged = [];
  let i = 0;
  let j = 0;

  while (i < left.length && j < right.length) {
    if (left[i] <= right[j]) {
      merged.push(left[i]);
      i++;
    } else {
      merged.push(right[j]);
      j++;
    }
  }

  while (i < left.length) {
    merged.push(left[i]);
    i++;
  }

  while (j < right.length) {
    merged.push(right[j]);
    j++;
  }

  return merged;
}

const array = [5, 3, 8, 4, 2];
console.log(mergeSort(array)); // Output: [2, 3, 4, 5, 8]
```

Explanation: Merge sort is a divide-and-conquer algorithm that recursively divides the array into two halves, sorts them independently, and then merges them to produce the sorted array. It uses a helper function `merge` to merge the two sorted halves by comparing the elements. The process is repeated until the array is divided into single elements, which are then merged back up to form the final sorted array. The time complexity of merge sort is O(n log n) in all cases.

5. Quick Sort:

```javascript
function quickSort(arr, low = 0, high = arr.length - 1) {
  if (low < high) {
    const pivotIndex = partition(arr, low, high);
    quickSort(arr, low, pivotIndex - 1);
    quickSort(arr, pivotIndex + 1, high);
  }
  return arr;
}

function partition(arr, low, high) {
  const pivot = arr[high];
  let i = low - 1;
  for (let j = low; j < high; j++) {
    if (arr[j] < pivot) {
      i++;
      [arr[i], arr[j]] = [arr[j], arr[i]];
    }
  }
  [arr[i + 1], arr[high]] = [arr[high], arr[i + 1]];
  return i + 1;
}

const array = [5, 3, 8, 4, 2];
console.log(quickSort(array)); // Output: [2, 3, 4, 5, 8]
```

Explanation: Quick sort is a divide-and-conquer algorithm that selects a pivot element and partitions the array into two subarrays, one with elements less than the pivot and the other with elements greater than the pivot. It then recursively applies the same process to the subarrays until the entire array is sorted. The partitioning process is performed by moving the elements around the pivot so that all elements on the left are less than the pivot, and all elements on the right are greater than the pivot. The time complexity of quick sort is O(n log n) in the average case and O(n^2) in the worst case.

These examples provide implementations of common sorting algorithms in JavaScript along with explanations of how they work. You can use these code examples as a reference to understand the algorithms and their implementation details.
