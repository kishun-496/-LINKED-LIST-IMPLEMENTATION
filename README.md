# -LINKED-LIST-IMPLEMENTATION
COMPANY: CODETECH IT SOLUTIONS

NAME:   KISHUN MURMU

INTERN ID: CT04DG1357

DOMAIN: C Programming

BATCH DURATION: 4 WEEKS

MENTOR NAME: NEELA SANTHOSH

TASK DESCRIPTION:

In C programming, a singly linked list is a fundamental data structure that allows dynamic memory allocation and efficient data handling, especially in scenarios where the number of data elements is not fixed. Unlike arrays, which require contiguous memory and have a fixed size, linked lists consist of nodes that are scattered throughout memory and connected via pointers. Each node in a singly linked list contains two components: the data part, which stores the actual value, and the next pointer, which holds the address of the next node in the sequence. The first node is known as the head, and it acts as the entry point to traverse the entire list. If the list is empty, the head pointer is set to NULL.
To implement a singly linked list in C, the first step is to define the structure of a node using the struct keyword. The structure typically includes an integer field to hold the data and a pointer of the same structure type to represent the next node. For example:
struct Node {
    int data;
    struct Node* next;
};


With the structure defined, the head pointer is initialized to NULL, signifying an empty list. The primary operations in a singly linked list include insertion, deletion, and traversal. These operations allow for dynamic manipulation of the list and are essential for mastering pointer-based programming.

 INSERTION
 
Insertion in a singly linked list can occur at three different locations: at the beginning, at the end, or at a specific position. When inserting at the beginning, a new node is created using malloc() to allocate memory, its data field is set, and its next pointer is assigned the current head. Then, the head is updated to point to the new node. This is the simplest insertion and is often used for building lists in reverse order.
Insertion at the end involves creating a new node and traversing the list using a temporary pointer until the last node is reached (where next is NULL). Once found, the next pointer of the last node is set to the new node, and the new node's next pointer is set to NULL.
Inserting at a specific position requires careful pointer manipulation. The program must first traverse the list up to the desired location while maintaining a counter. A new node is then created and inserted by adjusting the next pointers of surrounding nodes. This operation is more complex due to the need to handle edge cases—such as inserting at the start, in the middle, or beyond the list’s current length.

 DELETION
 
Deletion can also be done in multiple ways: from the beginning, from the end, or by value. Deleting from the beginning involves updating the head pointer to point to the second node and freeing the memory of the original head node using free(). This is a quick operation but must be done carefully to avoid memory leaks.
Deleting from the end requires traversal up to the second-to-last node, whose next pointer is then set to NULL. The last node is then freed using free(). This operation also requires caution as improper pointer manipulation can lead to dangling references or segmentation faults.
Deletion by value involves searching the list for a node containing a specific value and then removing that node while maintaining the integrity of the list. A prev pointer is used to track the node before the one to be deleted. Once found, prev->next is updated to skip the target node, and the target node is freed. If the value doesn’t exist, the program should return a message indicating that the operation was unsuccessful.

 TRAVERSAL

Traversal is the process of visiting each node from the head to the end. A temporary pointer is initialized to head, and a loop is used to print the data field of each node until NULL is encountered. This operation is essential for verifying list contents and debugging. It’s the visual proof that your insertions and deletions are functioning as expected.
For added user-friendliness, a visual separator (like ->) can be printed between nodes to show linkage, e.g., 10 -> 20 -> 30 -> NULL.
 Key Concepts and Memory Management
Memory management is vital in linked list implementation. Every node must be dynamically allocated using malloc(), and every deleted node should be freed using free() to avoid memory leaks. Proper error checking must be in place when allocating memory, such as verifying if malloc() returned NULL. Also, pointer updates must be handled with precision to ensure that the integrity of the list remains intact.
Additionally, because C doesn’t come with garbage collection, the programmer must manage memory manually. That’s why it's common to include a “cleanup” function that deletes the entire list before the program ends.



