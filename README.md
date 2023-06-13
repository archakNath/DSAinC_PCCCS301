<div align = "center">
  
# PCC-CS301: Data Structure and Algorithm
🔗Link to PCC-CS301 syllabus. [Click here.](http://makautexam.net/aicte_details/Syllabus/IT/sem3.pdf) <br>
🤝Connect with me on Twitter ;) [Click here.](https://twitter.com/NathArchak)

</div>

<code>UNIT 1 : Introduction: Basic Terminologies: Elementary Data Organizations, Data Structure Operations: insertion, deletion, traversal etc.; Analysis of an Algorithm, Asymptotic Notations, Time-Space trade off. Searching: Linear Search and Binary Search Techniques and their complexity analysis. 
</code>

### Data Organizations:

Data organization refers to the way data is structured and stored in a computer system. It involves defining the logical and physical structures to efficiently store and access data. Some common data organizations include arrays, linked lists, stacks, queues, trees, and graphs.

### Data Structure Operations:

Data structure operations are the basic operations performed on data structures to manipulate the data stored in them. These operations include:

Insertion: Adding new data elements into a data structure.<br>
Deletion: Removing data elements from a data structure.<br>
Traversal: Visiting each element in a data structure, usually in a specific order.<br>
Search: Finding a specific element in a data structure.<br>
Update: Modifying the value of an existing element in a data structure.<br>
Sorting: Arranging the elements in a specific order.<br>
Merging: Combining two or more data structures into a single data structure.<br>
Splitting: Dividing a data structure into two or more smaller data structures.<br>
### Analysis of an Algorithm:

The analysis of an algorithm involves evaluating its performance characteristics, such as time complexity and space complexity. It helps in understanding how an algorithm's efficiency changes with the input size and allows us to compare different algorithms based on their efficiency.

### Asymptotic Notations:

Asymptotic notations are used to describe the growth rate or complexity of an algorithm as the input size increases. The three commonly used asymptotic notations are:

Big O notation (O): It provides an upper bound on the growth rate of an algorithm. It describes the worst-case scenario.<br>
Omega notation (Ω): It provides a lower bound on the growth rate of an algorithm. It describes the best-case scenario.<br>
Theta notation (Θ): It provides both upper and lower bounds on the growth rate of an algorithm. It describes the average-case scenario.<br>
These notations help in comparing and analyzing the efficiency of algorithms without getting into the specifics of the hardware or implementation details.

### Time-Space Trade-off in C Language:

Time-space trade-off refers to the relationship between the time complexity and space complexity of an algorithm. In some cases, improving the time efficiency of an algorithm may require using more memory, while reducing the memory usage may lead to slower execution times.

In the C language, you can make trade-offs between time and space by choosing appropriate data structures and algorithms. For example, using an array might provide faster access to elements but consume more memory, whereas using a linked list might have slower access but require less memory.

It's important to consider the requirements of your specific problem and strike a balance between time and space efficiency based on the available resources and constraints.

### Searching: Linear Search and Binary Search

Searching is the process of finding a specific element in a collection of data. Two commonly used searching techniques are Linear Search and Binary Search.

#### Linear Search:
- Linear search is a simple searching algorithm that checks each element in a collection one by one until the target element is found or the end of the collection is reached.
- It is suitable for unordered or unsorted data.
- The time complexity of linear search is O(n), where 'n' is the number of elements in the collection.
- The space complexity of linear search is O(1) since it does not require any additional space.<br>
Here's an example of linear search in C language:

```
#include <stdio.h>

int linearSearch(int arr[], int n, int target) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == target) {
            return i; // Element found, return its index
        }
    }
    return -1; // Element not found
}

int main() {
    int arr[] = {5, 2, 8, 10, 3};
    int n = sizeof(arr) / sizeof(arr[0]);
    int target = 8;
    int result = linearSearch(arr, n, target);
    if (result == -1) {
        printf("Element not found\n");
    } else {
        printf("Element found at index %d\n", result);
    }
    return 0;
}
```

#### Binary Search:
- Binary search is a more efficient searching algorithm that relies on a sorted collection of elements.
- It divides the collection into two halves and repeatedly narrows down the search range by comparing the target element with the middle element.
- It is suitable for sorted data.
- The time complexity of binary search is O(log n), where 'n' is the number of elements in the collection.
- The space complexity of binary search is O(1) since it does not require any additional space.<br>
Here's an example of binary search in C language:

```
#include <stdio.h>

int binarySearch(int arr[], int low, int high, int target) {
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == target) {
            return mid; // Element found, return its index
        } else if (arr[mid] < target) {
            low = mid + 1; // Search in the right half
        } else {
            high = mid - 1; // Search in the left half
        }
    }
    return -1; // Element not found
}

int main() {
    int arr[] = {2, 3, 5, 8, 10};
    int n = sizeof(arr) / sizeof(arr[0]);
    int target = 8;
    int result = binarySearch(arr, 0, n - 1, target);
    if (result == -1) {
        printf("Element not found\n");
    } else {
        printf("Element found at index %d\n", result);
    }
    return 0;
}

```
