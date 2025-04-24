# exp-18
Aim

To study and implement Linked List in C++.

Software

Visual Studio Code

Theory

A linked list is a fundamental data structure. It mainly allows efficient insertion and deletion operations compared to arrays. Like arrays, it is also used to implement other data structures like stack, queue and deque. Linked lists are of several types, including:
Singly Linked List: Each node points to the next node in the sequence.

Doubly Linked List: Each node has pointers to both the next and the previous node.

Circular Linked List: The last node points back to the first node, forming a circle.

Comparison of Linked List and Arrays

Linked List:

Data Structure: Non-contiguous

Memory Allocation: Typically allocated one by one to individual elements

Insertion/Deletion: Efficient

Access: Sequential

Array:

Data Structure: Contiguous

Memory Allocation: Typically allocated to the whole array

Insertion/Deletion: Inefficient

Access: Random

Code

(A)
```
// LINKED LIST 

#include<iostream>
using namespace std; 
 
 class Link {
    public:
    int data;
    Link* next;
    Link(int num) {
        data=num;
        next=NULL;
    }
 };
 void insert_head(Link* &head, int data) {
    Link* new_node=new Link(data);
    new_node->next = head; 
    head = new_node;
 }
 void disp(Link* head) {
    Link* temp = head;
    while(temp!=NULL) { 
        cout<<temp->data<<"->";
        temp = temp->next;
    } 
    cout<<"NULL"<<endl;
 }

 int main() {
    Link* head = NULL;
    insert_head(head, 30);
    disp(head);
    insert_head(head, 32);
    disp(head);
    insert_head(head, 35);
    disp(head);
    //l1.disp(); 
 }  
```
(B)
```
// LINKED LIST 

#include<iostream>
using namespace std; 
 
class Link {
    public:
    int data;
    Link* next;
    Link(int num) {
        data = num;
        next = NULL;
    }
};

// Function to insert a new node at the head of the list
void insert_head(Link* &head, int data) {
    Link* new_node = new Link(data);
    new_node->next = head; 
    head = new_node;
}

// Function to display the linked list
void disp(Link* head) {
    Link* temp = head;
    while(temp != NULL) { 
        cout << temp->data << "->";
        temp = temp->next;
    } 
    cout << "NULL" << endl;
}

// Function to delete a node with a specific value
void delete_node(Link* &head, int value) {
    if(head == NULL) {
        cout << "List is empty, nothing to delete." << endl;
        return;
    }

    Link* temp = head;
    Link* prev = NULL;

    // If the node to be deleted is the head node
    if(temp != NULL && temp->data == value) {
        head = temp->next; // Change the head
        delete temp;       // Free memory
        return;
    }

    // Search for the node to be deleted, keeping track of the previous node
    while(temp != NULL && temp->data != value) {
        prev = temp;
        temp = temp->next;
    }

    // If the node was not found
    if(temp == NULL) {
        cout << "Node with value " << value << " not found." << endl;
        return;
    }

    // Unlink the node from the linked list
    prev->next = temp->next;

    // Free memory
    delete temp;
}

int main() {
    Link* head = NULL;
    insert_head(head, 30);
    disp(head);
    insert_head(head, 32);
    disp(head);
    insert_head(head, 35);
    disp(head);

    // Delete a node 

    delete_node(head, 32); // Deleting node with value 32
    disp(head);

    delete_node(head, 35); // Deleting node with value 35
    disp(head);

    delete_node(head, 100); // Attempting to delete a non-existent node
    disp(head); 
} 
```
Outputs:
<img width="633" alt="Screenshot 2025-04-24 at 23 27 41" src="https://github.com/user-attachments/assets/4d8552e0-df4e-4d0b-9029-a929a173f18f" />


Conclusion

I learnt the study and implement Linked List in C++.
