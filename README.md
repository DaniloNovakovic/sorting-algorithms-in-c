# Sorting algorithms in C (DEPRECATED)

[![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/)

Original goal of this project was for me to learn sorting algorithms (at the time i was first year of university), but now it serves as a reference, or a quick reminder in case i ever need one of these algorithms again. It could also have an educational value since it could be of use to students / beginners starting out with their programming journey.

---

## O(n) Sorting algorithms

### 1) Counting sort 
  - is applicable when each input is known to belong to a particular set, S, of possibilities.
  The algorithm runs in O(|S| + n) time and O(|S|) memory where n is the length of the input. 
  It works by creating an integer array of size |S| and using the ith bin to count the occurrences of the ith member of S in the input. 
  Each input is then counted by incrementing the value of its corresponding bin. 
  Afterward, the counting array is looped through to arrange all of the inputs in order. 
  This sorting algorithm often cannot be used because S needs to be reasonably small for the algorithm to be efficient, 
  but it is extremely fast and demonstrates great asymptotic behavior as n increases. 
  It also can be modified to provide stable behavior.
  
### 2) Bucket sort
  - is a divide and conquer sorting algorithm that generalizes counting sort by partitioning an array into a 
  finite number of buckets. Each bucket is then sorted individually, either using a different sorting algorithm, 
  or by recursively applying the bucket sorting algorithm.
  A bucket sort works best when the elements of the data set are evenly distributed across all buckets
 
### 3) Radix sort 
  - is an algorithm that sorts numbers by processing individual digits. n numbers consisting of k digits each are sorted in O(n · k) time. 
  Radix sort can process digits of each number either starting from the least significant digit (LSD) or starting from the most 
  significant digit (MSD). The LSD algorithm first sorts the list by the least significant digit while preserving their relative order 
  using a stable sort. Then it sorts them by the next digit, and so on from the least significant to the most significant, 
  ending up with a sorted list. While the LSD radix sort requires the use of a stable sort, the MSD radix sort algorithm does not 
  (unless stable sorting is desired). In-place MSD radix sort is not stable. It is common for the counting sort algorithm to be used 
  internally by the radix sort. 
  A hybrid sorting approach, such as using insertion sort for small bins improves performance of radix sort significantly.
 
---

## O(nlogn) Sorting algorithms

### 1) Quick Sort 
  - is a divide and conquer algorithm which relies on a partition operation: to partition an array an element called a
  pivot is selected. All elements smaller than the pivot are moved before it and all greater elements are moved after it.
  This can be done efficiently in linear time and in-place. The lesser and greater sublists are then recursively sorted. 
  This yields average time complexity of O(n log n), with low overhead, and thus this is a popular algorithm. 
  Efficient implementations of quicksort (with in-place partitioning) are typically unstable sorts and somewhat complex, 
  but are among the fastest sorting algorithms in practice. Together with its modest O(log n) space usage, 
  quicksort is one of the most popular sorting algorithms and is available in many standard programming libraries.
  
### 2) Merge Sort
  - takes advantage of the ease of merging already sorted lists into a new sorted list. 
  It starts by comparing every two elements (i.e., 1 with 2, then 3 with 4...) and swapping them if the first 
  should come after the second. It then merges each of the resulting lists of two into lists of four, 
  then merges those lists of four, and so on; until at last two lists are merged into the final sorted list.
  Of the algorithms described here, this is the first that scales well to very large lists, 
  because its worst-case running time is O(n log n). It is also easily applied to lists, not only arrays, 
  as it only requires sequential access, not random access. 
  However, it has additional O(n) space complexity, and involves a large number of copies in simple implementations.
  
### 3) Heap Sort 
  - Heapsort is a much more efficient version of selection sort. It also works by determining the largest (or smallest) 
  element of the list, placing that at the end (or beginning) of the list, then continuing with the rest of the list, 
  but accomplishes this task efficiently by using a data structure called a heap, a special type of binary tree.
  Once the data list has been made into a heap, the root node is guaranteed to be the largest (or smallest) element. 
  When it is removed and placed at the end of the list, the heap is rearranged so the largest element remaining moves to the root. 
  Using the heap, finding the next largest element takes O(log n) time, instead of O(n) for a linear scan as in simple selection sort. 
  This allows Heapsort to run in O(n log n) time, and this is also the worst case complexity.
  
---  
  
## O(n^2) Sorting Algorithms

### 1) Bubble Sort
  - Bubble sort, sometimes referred to as sinking sort, is a simple sorting algorithm that repeatedly steps through the list 
  to be sorted, compares each pair of adjacent items and swaps them if they are in the wrong order. 
  The pass through the list is repeated until no swaps are needed, which indicates that the list is sorted.
  The algorithm, which is a comparison sort, is named for the way smaller or larger elements "bubble" to the top of the list. 
  Although the algorithm is simple, it is too slow and impractical for most problems even when compared to insertion sort. 
  It can be practical if the input is usually in sorted order but may occasionally have some out-of-order elements nearly in position.

### 2) Insertion Sort
  - is a simple sorting algorithm that is relatively efficient for small lists and mostly sorted lists, 
  and is often used as part of more sophisticated algorithms. It works by taking elements from the list one by one and 
  inserting them in their correct position into a new sorted list. In arrays, the new list and the remaining elements can share 
  the array's space, but insertion is expensive, requiring shifting all following elements over by one.
  Shell sort (see below) is a variant of insertion sort that is more efficient for larger lists.
  
### 3) Selection Sort 
  - Selection sort is an in-place comparison sort. It has O(n2) complexity, making it inefficient on large lists, and generally performs 
  worse than the similar insertion sort. Selection sort is noted for its simplicity, and also has performance advantages 
  over more complicated algorithms in certain situations.
  The algorithm finds the minimum value, swaps it with the value in the first position, and repeats these steps for the
  remainder of the list. It does no more than n swaps, and thus is useful where swapping is very expensive.
  
  
  reference : https://en.wikipedia.org/wiki/Sorting_algorithm
