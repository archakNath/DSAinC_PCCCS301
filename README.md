<div align = "center">
  
# PCC-CS301: Data Structure and Algorithm 🧑‍💻
⭐Star this repository to appreciate my work. It helps reach greater audience. <br>
🔗Link to PCC-CS301 syllabus. [Click here.](http://makautexam.net/aicte_details/Syllabus/IT/sem3.pdf) <br>
🤝Connect with me on Twitter ;) [Click here.](https://twitter.com/NathArchak)

![pcccs301](https://github.com/archakNath/DSAinC_PCCCS301/assets/112867859/1cb742ca-17e4-4aad-ae74-6475f4c81b19)


</div>

#### 🤖ABOUT: This repository is made in order to help students learn Data Structure and Algorithms in one place. The contents of this documentation strictly adhere to the [MAKAUT(formerly WBUT) syllabus](http://makautexam.net/aicte_details/Syllabus/IT/sem3.pdf) of PCC-CS301 Data Structure and Algorithm taught in all affiliated colleges in 3rd Semester.
#### 📝CONTRIBUTION: Contribution to the betterment of this documentation is highly appreciated. Fork this repo and send push request. You can also connect with me on my socials given above.
<code>⚠️NOTE: This documentation is limited till Linked Lists. Trees, Sorting and Hashing are not yet covered here. Also knowledge of Structure and Pointers is necessary!</code>

<hr>

<code>UNIT 1️⃣ : Introduction: Basic Terminologies: Elementary Data Organizations, Data Structure Operations: insertion, deletion, traversal, etc.; Analysis of an Algorithm, Asymptotic Notations, Time-Space trade-off. Searching: Linear Search and Binary Search Techniques and their complexity analysis. 
</code>

### Data Organizations:

Data organization refers to the way data is structured and stored in a computer system. It involves defining the logical and physical structures to efficiently store and access data. Some common data organizations include arrays, linked lists, stacks, queues, trees, and graphs.

### Data Structure Operations:

Data structure operations are the basic operations performed on data structures to manipulate the data stored in them. These operations include:

- Insertion: Adding new data elements into a data structure.<br>
- Deletion: Removing data elements from a data structure.<br>
- Traversal: Visiting each element in a data structure, usually in a specific order.<br>
- Search: Finding a specific element in a data structure.<br>
- Update: Modifying the value of an existing element in a data structure.<br>
- Sorting: Arranging the elements in a specific order.<br>
- Merging: Combining two or more data structures into a single data structure.<br>
- Splitting: Dividing a data structure into two or more smaller data structures.

```c
#include <stdio.h>

// Function to insert an element into the array at a specific position
void insertElement(int arr[], int size, int element, int position) {
    if (position < 0 || position > size) {
        printf("Invalid position\n");
        return;
    }
    
    for (int i = size - 1; i >= position; i--) {
        arr[i + 1] = arr[i];
    }
    
    arr[position] = element;
}

// Function to delete an element from the array at a specific position
void deleteElement(int arr[], int size, int position) {
    if (position < 0 || position >= size) {
        printf("Invalid position\n");
        return;
    }
    
    for (int i = position; i < size - 1; i++) {
        arr[i] = arr[i + 1];
    }
}

// Function to traverse and print all elements of the array
void traverseArray(int arr[], int size) {
    printf("Array elements: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
}

// Function to search for an element in the array
int searchElement(int arr[], int size, int element) {
    for (int i = 0; i < size; i++) {
        if (arr[i] == element) {
            return i;
        }
    }
    return -1;
}

// Function to update the value of an element at a specific position in the array
void updateElement(int arr[], int size, int element, int position) {
    if (position < 0 || position >= size) {
        printf("Invalid position\n");
        return;
    }
    
    arr[position] = element;
}

// Function to perform bubble sort on the array
void bubbleSort(int arr[], int size) {
    for (int i = 0; i < size - 1; i++) {
        for (int j = 0; j < size - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

// Function to merge two arrays into a new array
void mergeArrays(int arr1[], int size1, int arr2[], int size2, int merged[]) {
    int i = 0, j = 0, k = 0;
    
    while (i < size1 && j < size2) {
        if (arr1[i] < arr2[j]) {
            merged[k++] = arr1[i++];
        } else {
            merged[k++] = arr2[j++];
        }
    }
    
    while (i < size1) {
        merged[k++] = arr1[i++];
    }
    
    while (j < size2) {
        merged[k++] = arr2[j++];
    }
}

// Function to split an array into two separate arrays
void splitArray(int arr[], int size, int splitIndex, int arr1[], int *size1, int arr2[], int *size2) {
    if (splitIndex < 0 || splitIndex > size) {
        printf("Invalid split index\n");
        return;
    }
    
    *size1 = splitIndex;
    *size2 = size - splitIndex;
    
    for (int i = 0; i < splitIndex; i++) {
        arr1[i] = arr[i];
    }
    
    for (int i = 0; i < *size2; i++) {
        arr2[i] = arr[splitIndex + i];
    }
}

int main() {
    int arr[10] = {5, 3, 8, 2, 1, 9, 7, 6, 4, 0};
    int size = 10;
    
    // Insertion
    insertElement(arr, size, 10, 2);
    size++;
    
    // Deletion
    deleteElement(arr, size, 4);
    size--;
    
    // Traversal
    traverseArray(arr, size);
    
    // Search
    int searchIndex = searchElement(arr, size, 6);
    if (searchIndex != -1) {
        printf("Element found at index %d\n", searchIndex);
    } else {
        printf("Element not found\n");
    }
    
    // Update
    updateElement(arr, size, 15, 3);
    
    // Sorting
    bubbleSort(arr, size);
    printf("Sorted array: ");
    traverseArray(arr, size);
    
    // Merging
    int arr1[5] = {1, 3, 5, 7, 9};
    int arr2[5] = {2, 4, 6, 8, 10};
    int merged[10];
    mergeArrays(arr1, 5, arr2, 5, merged);
    printf("Merged array: ");
    traverseArray(merged, 10);
    
    // Splitting
    int splitIndex = 3;
    int arr3[3];
    int size3;
    int arr4[7];
    int size4;
    splitArray(merged, 10, splitIndex, arr3, &size3, arr4, &size4);
    printf("Split array 1: ");
    traverseArray(arr3, size3);
    printf("Split array 2: ");
    traverseArray(arr4, size4);
    
    return 0;
}

```

### Analysis of an Algorithm:

The analysis of an algorithm involves evaluating its performance characteristics, such as time complexity and space complexity. It helps in understanding how an algorithm's efficiency changes with the input size and allows us to compare different algorithms based on their efficiency.

### Asymptotic Notations:

Asymptotic notations are used to describe the growth rate or complexity of an algorithm as the input size increases. The three commonly used asymptotic notations are:

- Big O notation (O): It provides an upper bound on the growth rate of an algorithm. It describes the worst-case scenario.
- Omega notation (Ω): It provides a lower bound on the growth rate of an algorithm. It describes the best-case scenario.
- Theta notation (Θ): It provides both upper and lower bounds on the growth rate of an algorithm. It describes the average-case scenario.

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

```c
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

```c
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
<hr>
<code>UNIT 2️⃣ : Stacks and Queues: ADT Stack and its operations: Algorithms and their complexity analysis, Applications of Stacks: Expression Conversion and evaluation - corresponding algorithms and complexity analysis. ADT queue, Types of Queue: Simple Queue, Circular Queue, Priority Queue; Operations on each types of Queues: Algorithms and their analysis.</code>


### ADT Stack and its operations:

ADT (Abstract Data Type) Stack is a data structure that follows the Last-In-First-Out (LIFO) principle. It allows insertion and deletion of elements from only one end, called the top of the stack. The basic operations of the stack are:

- Push: Insert an element onto the top of the stack.
- Pop: Removes and returns the top element from the stack.
- Peek or Top: Returns the value of the top element without removing it.
- IsEmpty: Checks if the stack is empty.
- Size: Returns the number of elements in the stack. <br>
Here's an example implementation of the ADT Stack in C language:
```c
#include <stdio.h>
#define MAX_SIZE 100

typedef struct {
    int arr[MAX_SIZE];
    int top;
} Stack;

void initialize(Stack *stack) {
    stack->top = -1;
}

void push(Stack *stack, int data) {
    if (stack->top == MAX_SIZE - 1) {
        printf("Stack Overflow\n");
        return;
    }
    stack->arr[++stack->top] = data;
}

int pop(Stack *stack) {
    if (stack->top == -1) {
        printf("Stack Underflow\n");
        return -1;
    }
    return stack->arr[stack->top--];
}

int peek(Stack *stack) {
    if (stack->top == -1) {
        printf("Stack is empty\n");
        return -1;
    }
    return stack->arr[stack->top];
}

int isEmpty(Stack *stack) {
    return stack->top == -1;
}

int size(Stack *stack) {
    return stack->top + 1;
}

int main() {
    Stack stack;
    initialize(&stack);

    push(&stack, 5);
    push(&stack, 10);
    push(&stack, 15);

    printf("Top element: %d\n", peek(&stack));
    printf("Stack size: %d\n", size(&stack));

    while (!isEmpty(&stack)) {
        printf("Popped element: %d\n", pop(&stack));
    }

    return 0;
}
```

### Applications of Stacks: Expression Conversion and Evaluation:

#### Expression Conversion:

- Stack can be used to convert an infix expression to postfix or prefix notation.
- Algorithms like Shunting Yard or Reverse Polish Notation (RPN) can be employed.
- Complexity analysis depends on the length of the expression.

#### Expression Evaluation:

- Stack can be used to evaluate postfix or prefix expressions.
- Algorithms like Postfix Evaluation or Prefix Evaluation can be used.
- Complexity analysis depends on the length of the expression.


### ADT Queue and its Types:

ADT Queue is a data structure that follows the First-In-First-Out (FIFO) principle. It allows insertion at one end, called the rear, and deletion at the other end, called the front. There are different types of queues:

#### Simple Queue:

A simple queue is a basic queue where elements are inserted at the rear and removed from the front.
Complexity analysis for enqueue and dequeue operations is O(1).

```c
#include <stdio.h>
#define MAX_SIZE 100

typedef struct {
    int arr[MAX_SIZE];
    int front, rear;
} Queue;

void initialize(Queue *queue) {
    queue->front = queue->rear = -1;
}

void enqueue(Queue *queue, int data) {
    if (queue->rear == MAX_SIZE - 1) {
        printf("Queue Overflow\n");
        return;
    }
    if (queue->front == -1) {
        queue->front = 0;
    }
    queue->arr[++queue->rear] = data;
}

int dequeue(Queue *queue) {
    if (queue->front == -1 || queue->front > queue->rear) {
        printf("Queue Underflow\n");
        return -1;
    }
    return queue->arr[queue->front++];
}

int isEmpty(Queue *queue) {
    return queue->front == -1 || queue->front > queue->rear;
}

int size(Queue *queue) {
    return queue->rear - queue->front + 1;
}

int main() {
    Queue queue;
    initialize(&queue);

    enqueue(&queue, 5);
    enqueue(&queue, 10);
    enqueue(&queue, 15);

    printf("Queue size: %d\n", size(&queue));

    while (!isEmpty(&queue)) {
        printf("Dequeued element: %d\n", dequeue(&queue));
    }

    return 0;
}
```

#### Circular Queue:

A circular queue is an optimized queue that reuses the empty spaces in the queue by circling around.
Complexity analysis for enqueue and dequeue operations is O(1).

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 5

// Structure to represent a circular queue
typedef struct {
    int data[MAX_SIZE];
    int front;
    int rear;
} CircularQueue;

// Function to initialize the circular queue
void initialize(CircularQueue* queue) {
    queue->front = -1;
    queue->rear = -1;
}

// Function to check if the circular queue is empty
int isEmpty(CircularQueue* queue) {
    return (queue->front == -1 && queue->rear == -1);
}

// Function to check if the circular queue is full
int isFull(CircularQueue* queue) {
    return ((queue->rear + 1) % MAX_SIZE == queue->front);
}

// Function to insert an element into the circular queue
void enqueue(CircularQueue* queue, int value) {
    if (isFull(queue)) {
        printf("Circular queue is full. Cannot enqueue element.\n");
        return;
    } else if (isEmpty(queue)) {
        queue->front = 0;
        queue->rear = 0;
    } else {
        queue->rear = (queue->rear + 1) % MAX_SIZE;
    }
    queue->data[queue->rear] = value;
}

// Function to remove an element from the circular queue
void dequeue(CircularQueue* queue) {
    if (isEmpty(queue)) {
        printf("Circular queue is empty. Cannot dequeue element.\n");
        return;
    } else if (queue->front == queue->rear) {
        queue->front = -1;
        queue->rear = -1;
    } else {
        queue->front = (queue->front + 1) % MAX_SIZE;
    }
}

// Function to get the front element of the circular queue
int getFront(CircularQueue* queue) {
    if (isEmpty(queue)) {
        printf("Circular queue is empty. No front element.\n");
        return -1;
    }
    return queue->data[queue->front];
}

// Function to display the elements of the circular queue
void display(CircularQueue* queue) {
    if (isEmpty(queue)) {
        printf("Circular queue is empty.\n");
        return;
    }
    printf("Circular queue: ");
    int i = queue->front;
    do {
        printf("%d ", queue->data[i]);
        i = (i + 1) % MAX_SIZE;
    } while (i != (queue->rear + 1) % MAX_SIZE);
    printf("\n");
}

int main() {
    CircularQueue queue;
    initialize(&queue);

    enqueue(&queue, 10);
    enqueue(&queue, 20);
    enqueue(&queue, 30);
    display(&queue); // Output: 10 20 30

    dequeue(&queue);
    display(&queue); // Output: 20 30

    enqueue(&queue, 40);
    enqueue(&queue, 50);
    enqueue(&queue, 60);
    display(&queue); // Output: 20 30 40 50 60

    enqueue(&queue, 70); // Output: Circular queue is full. Cannot enqueue element.

    return 0;
}

```

In this example, we define a structure CircularQueue to represent the circular queue. It contains an array to store the elements, and front and rear indices to keep track of the front and rear positions of the circular queue.

We have the following functions for a circular queue:

- initialize() initializes the circular queue by setting front and rear to -1.
- isEmpty() checks if the circular queue is empty.
- isFull() checks if the circular queue is full.
- enqueue() inserts an element into the circular queue.
- dequeue() removes an element from the circular queue.
- getFront() retrieves the front element of the circular queue.
- display() displays the elements of the circular queue.

In the main() function, we initialize the circular queue and perform enqueue and dequeue operations. We display the circular queue after each operation.

#### Priority Queue:

A priority queue assigns priority to each element and processes them based on their priority.
Complexity analysis depends on the implementation (e.g., binary heap) and the number of elements.

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 100

// Structure to represent a priority queue element
typedef struct {
    int data;
    int priority;
} PriorityQueueElement;

// Structure to represent a priority queue
typedef struct {
    PriorityQueueElement elements[MAX_SIZE];
    int size;
} PriorityQueue;

// Function to initialize the priority queue
void initialize(PriorityQueue* queue) {
    queue->size = 0;
}

// Function to check if the priority queue is empty
int isEmpty(PriorityQueue* queue) {
    return (queue->size == 0);
}

// Function to check if the priority queue is full
int isFull(PriorityQueue* queue) {
    return (queue->size == MAX_SIZE);
}

// Function to enqueue an element with its priority into the priority queue
void enqueue(PriorityQueue* queue, int data, int priority) {
    if (isFull(queue)) {
        printf("Priority queue is full. Cannot enqueue element.\n");
        return;
    }
    PriorityQueueElement newElement;
    newElement.data = data;
    newElement.priority = priority;
    int i = queue->size;
    while (i > 0 && queue->elements[(i - 1) / 2].priority < priority) {
        queue->elements[i] = queue->elements[(i - 1) / 2];
        i = (i - 1) / 2;
    }
    queue->elements[i] = newElement;
    queue->size++;
}

// Function to dequeue the element with the highest priority from the priority queue
void dequeue(PriorityQueue* queue) {
    if (isEmpty(queue)) {
        printf("Priority queue is empty. Cannot dequeue element.\n");
        return;
    }
    PriorityQueueElement lastElement = queue->elements[queue->size - 1];
    queue->size--;
    int i = 0;
    while (2 * i + 1 < queue->size) {
        int child = 2 * i + 1;
        if (child + 1 < queue->size && queue->elements[child + 1].priority > queue->elements[child].priority) {
            child++;
        }
        if (lastElement.priority >= queue->elements[child].priority) {
            break;
        }
        queue->elements[i] = queue->elements[child];
        i = child;
    }
    queue->elements[i] = lastElement;
}

// Function to get the element with the highest priority from the priority queue
int getHighestPriorityElement(PriorityQueue* queue) {
    if (isEmpty(queue)) {
        printf("Priority queue is empty. No highest priority element.\n");
        return -1;
    }
    return queue->elements[0].data;
}

// Function to display the elements of the priority queue
void display(PriorityQueue* queue) {
    if (isEmpty(queue)) {
        printf("Priority queue is empty.\n");
        return;
    }
    printf("Priority queue: ");
    for (int i = 0; i < queue->size; i++) {
        printf("%d ", queue->elements[i].data);
    }
    printf("\n");
}

int main() {
    PriorityQueue queue;
    initialize(&queue);

    enqueue(&queue, 10, 3);
    enqueue(&queue, 20, 2);
    enqueue(&queue, 30, 5);
    display(&queue); // Output: Priority queue: 30 10 20

    dequeue(&queue);
    display(&queue); // Output: Priority queue: 20 10

    enqueue(&queue, 40, 4);
    enqueue(&queue, 50, 1);
    display(&queue); // Output: Priority queue: 50 20 40 10

    return 0;
}
```
In this example, we define a structure PriorityQueueElement to represent an element in the priority queue. It contains two fields: data to store the actual data, and priority to store the priority of the element. We also define a structure PriorityQueue to represent the priority queue, which contains an array of PriorityQueueElement and a size variable to keep track of the number of elements in the queue.

We have the following functions for a priority queue:

- initialize() initializes the priority queue.
- isEmpty() checks if the priority queue is empty.
- isFull() checks if the priority queue is full.
- enqueue() inserts an element with its priority into the priority queue.
- dequeue() removes the element with the highest priority from the priority queue.
- getHighestPriorityElement() retrieves the element with the highest priority from the priority queue.
- display() displays the elements of the priority queue.

In the main() function, we initialize the priority queue and perform enqueue and dequeue operations. We display the priority queue after each operation.

The complexity analysis for queues depends on the specific operations and their implementations.

<hr>

<code>UNIT 3️⃣ : Linked Lists: Singly linked lists: Representation in memory, Algorithms of several operations: Traversing, Searching, Insertion into, Deletion from  linked list; Linked representation of Stack and Queue, Header nodes, Doubly linked list: operations on it and algorithmic analysis; Circular Linked Lists: all operations their algorithms and the complexity analysis.</code>

### Singly Linked Lists:

A singly linked list is a data structure where each node contains a data element and a pointer/reference to the next node in the sequence. Here's an overview of the operations on singly linked lists:

#### Representation in Memory:

- Each node of a singly linked list contains two fields: a data field to store the element and a next field to store the address/reference of the next node.
- The last node's next field is typically set to NULL to indicate the end of the list.
### Algorithms for Operations:

#### Traversing:

- To traverse a linked list, you start from the head node and visit each node successively until reaching the end (NULL).
- Complexity: O(n), where n is the number of nodes in the list.
#### Searching:

- To search for a specific element in a linked list, you iterate through each node and compare the target element with the data of each node.
- Complexity: O(n), where n is the number of nodes in the list.
#### Insertion:

- Insertion can be done at different positions: at the beginning (prepend), at the end (append), or at a specific position (insert after/before a node).
- Complexity: O(1) for prepend/append, O(n) for insert at a specific position.
#### Deletion:

- Deletion can be done at different positions: at the beginning, at the end, or at a specific position (delete after/before a node).
- Complexity: O(1) for delete at the beginning, O(n) for delete at the end or at a specific position.

```c
#include <stdio.h>
#include <stdlib.h>

// Structure to represent a node
typedef struct Node {
    int data;
    struct Node* next;
} Node;

// Function to create a new node
Node* createNode(int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the beginning of the linked list
Node* insertAtBeginning(Node* head, int data) {
    Node* newNode = createNode(data);
    if (head == NULL) {
        head = newNode;
    } else {
        newNode->next = head;
        head = newNode;
    }
    return head;
}

// Function to insert a node at the end of the linked list
Node* insertAtEnd(Node* head, int data) {
    Node* newNode = createNode(data);
    if (head == NULL) {
        head = newNode;
    } else {
        Node* temp = head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
    return head;
}

// Function to delete a node from the linked list
Node* deleteNode(Node* head, int data) {
    if (head == NULL) {
        printf("Linked list is empty. Cannot delete node.\n");
        return head;
    }
    Node* temp = head;
    Node* prev = NULL;
    if (temp != NULL && temp->data == data) {
        head = temp->next;
        free(temp);
        return head;
    }
    while (temp != NULL && temp->data != data) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Node not found in the linked list.\n");
        return head;
    }
    prev->next = temp->next;
    free(temp);
    return head;
}

// Function to display the linked list
void display(Node* head) {
    Node* temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

// Function to search for an element in the linked list
int search(Node* head, int data) {
    Node* temp = head;
    int position = 0;
    while (temp != NULL) {
        if (temp->data == data) {
            return position;
        }
        temp = temp->next;
        position++;
    }
    return -1; // Element not found
}

int main() {
    Node* head = NULL;

    head = insertAtBeginning(head, 10);
    head = insertAtEnd(head, 20);
    head = insertAtEnd(head, 30);
    display(head); // Output: 10 20 30

    head = deleteNode(head, 20);
    display(head); // Output: 10 30

    int position = search(head, 10);
    if (position != -1) {
        printf("Element found at position %d\n", position);
    } else {
        printf("Element not found in the linked list.\n");
    }

    return 0;
}
```
In this example, we define a structure Node to represent a node in the linked list. Each node contains a data element and a pointer to the next node.

We have several functions:

- createNode() creates a new node with the given data.
- insertAtBeginning() inserts a node at the beginning of the linked list.
- insertAtEnd() inserts a node at the end of the linked list.
- deleteNode() deletes a node with the given data from the linked list.
- display() displays the elements of the linked list.
- search() searches for an element in the linked list and returns its position.

In the main() function, we create a linked list by inserting nodes at the beginning and end. We display the linked list, delete a node, and display the updated linked list. Finally, we search for an element in the linked list and display the result.

### Linked Representation of Stack and Queue:

- Stack and Queue can be implemented using a linked list by considering specific rules for insertion and deletion.
- In a linked representation of a stack, insertion and deletion are performed at the same end, usually the head of the linked list.
- In a linked representation of a queue, insertion is done at one end (rear) and deletion is done at the other end (front) of the linked list.
### Header Nodes:

- Header nodes are additional nodes added at the beginning of a linked list to simplify operations.
- They contain no data and serve as a dummy node or a sentinel to handle edge cases.

To learn more about header nodes, [click here.](https://www.geeksforgeeks.org/header-linked-list-in-c/)
### Doubly Linked List:

- A doubly linked list is a variation of a linked list where each node contains pointers to both the next and previous nodes.
- It allows traversal in both directions (forward and backward) and enables efficient insertion and deletion at any position.
- Operations on a doubly linked list include traversal, searching, insertion, deletion, etc.

Here's an example of a doubly linked list implementation in C:

```c
#include <stdio.h>
#include <stdlib.h>

// Structure to represent a node
typedef struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
} Node;

// Function to create a new node
Node* createNode(int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the beginning of the linked list
Node* insertAtBeginning(Node* head, int data) {
    Node* newNode = createNode(data);
    if (head == NULL) {
        head = newNode;
    } else {
        newNode->next = head;
        head->prev = newNode;
        head = newNode;
    }
    return head;
}

// Function to insert a node at the end of the linked list
Node* insertAtEnd(Node* head, int data) {
    Node* newNode = createNode(data);
    if (head == NULL) {
        head = newNode;
    } else {
        Node* temp = head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->prev = temp;
    }
    return head;
}

// Function to delete a node from the linked list
Node* deleteNode(Node* head, int data) {
    if (head == NULL) {
        printf("Linked list is empty. Cannot delete node.\n");
        return head;
    }
    Node* temp = head;
    if (temp != NULL && temp->data == data) {
        head = temp->next;
        if (head != NULL) {
            head->prev = NULL;
        }
        free(temp);
        return head;
    }
    while (temp != NULL && temp->data != data) {
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Node not found in the linked list.\n");
        return head;
    }
    if (temp->prev != NULL) {
        temp->prev->next = temp->next;
    }
    if (temp->next != NULL) {
        temp->next->prev = temp->prev;
    }
    free(temp);
    return head;
}

// Function to display the linked list in forward direction
void displayForward(Node* head) {
    Node* temp = head;
    printf("Linked list (forward): ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

// Function to display the linked list in reverse direction
void displayBackward(Node* head) {
    Node* temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    printf("Linked list (backward): ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->prev;
    }
    printf("\n");
}

int main() {
    Node* head = NULL;

    head = insertAtBeginning(head, 10);
    head = insertAtEnd(head, 20);
    head = insertAtEnd(head, 30);
    displayForward(head);  // Output: 10 20 30
    displayBackward(head); // Output: 30 20 10

    head = deleteNode(head, 20);
    displayForward(head);  // Output: 10 30

    return 0;
}
```
In this example, the Node structure has an additional pointer called prev, which points to the previous node.

We have similar functions as in the singly linked list implementation, with some modifications to handle the doubly linked list:

- createNode() creates a new node with the given data and initializes the prev and next pointers to NULL.
- insertAtBeginning() inserts a node at the beginning of the linked list and updates the prev and next pointers accordingly.
- insertAtEnd() inserts a node at the end of the linked list and updates the prev and next pointers accordingly.
- deleteNode() deletes a node with the given data from the linked list and updates the prev and next pointers of adjacent nodes.
- displayForward() displays the elements of the linked list in the forward direction, starting from the head.
- displayBackward() displays the elements of the linked list in the reverse direction, starting from the last node.

In the main() function, we create a doubly linked list by inserting nodes at the beginning and end. We display the linked list in both forward and backward directions. We then delete a node from the list and display the updated linked list.

### Circular Linked Lists:

- In a circular linked list, the last node's next pointer is connected to the first node, forming a circular structure.
- It allows continuous traversal from any node to any other node in the list.
- Operations on a circular linked list include traversal, searching, insertion, deletion, etc.
- The complexity analysis for linked list operations depends on the specific operation and the position of the element in the list.
```c
#include <stdio.h>
#include <stdlib.h>

// Structure to represent a node
typedef struct Node {
    int data;
    struct Node* next;
} Node;

// Function to create a new node
Node* createNode(int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the beginning of the circular linked list
Node* insertAtBeginning(Node* last, int data) {
    Node* newNode = createNode(data);
    if (last == NULL) {
        last = newNode;
        last->next = last;
    } else {
        newNode->next = last->next;
        last->next = newNode;
    }
    return last;
}

// Function to insert a node at the end of the circular linked list
Node* insertAtEnd(Node* last, int data) {
    Node* newNode = createNode(data);
    if (last == NULL) {
        last = newNode;
        last->next = last;
    } else {
        newNode->next = last->next;
        last->next = newNode;
        last = newNode;
    }
    return last;
}

// Function to delete a node from the circular linked list
Node* deleteNode(Node* last, int data) {
    if (last == NULL) {
        printf("Linked list is empty. Cannot delete node.\n");
        return last;
    }
    Node* temp = last->next;
    Node* prev = last;
    if (temp->data == data) {
        if (temp == last) {
            last = NULL;
        } else {
            prev->next = temp->next;
        }
        free(temp);
        return last;
    }
    while (temp != last && temp->data != data) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == last && temp->data != data) {
        printf("Node not found in the circular linked list.\n");
        return last;
    }
    prev->next = temp->next;
    if (temp == last) {
        last = prev;
    }
    free(temp);
    return last;
}

// Function to display the circular linked list
void display(Node* last) {
    if (last == NULL) {
        printf("Circular linked list is empty.\n");
        return;
    }
    Node* temp = last->next;
    printf("Circular linked list: ");
    do {
        printf("%d ", temp->data);
        temp = temp->next;
    } while (temp != last->next);
    printf("\n");
}

int main() {
    Node* last = NULL;

    last = insertAtBeginning(last, 10);
    last = insertAtEnd(last, 20);
    last = insertAtEnd(last, 30);
    display(last);  // Output: 10 20 30

    last = deleteNode(last, 20);
    display(last);  // Output: 10 30

    return 0;
}
```
In this example, the Node structure is similar to the one used in a singly linked list.

We have the following functions for a circular linked list:

- createNode() creates a new node with the given data and initializes the next pointer to NULL.
- insertAtBeginning() inserts a node at the beginning of the circular linked list and updates the next pointers accordingly.
- insertAtEnd() inserts a node at the end of the circular linked list and updates the next pointers accordingly.
- deleteNode() deletes a node with the given data from the circular linked list and updates the next pointers accordingly.
- display() displays the elements of the circular linked list.

In the main() function, we create a circular linked list by inserting nodes at the beginning and end. We display the circular linked list, delete a node, and display the updated circular linked list.
