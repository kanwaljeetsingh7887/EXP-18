# EXP-18


#### Aim 
To study and implement Linked List in C++.

#### Software 
Visual Studio Code 

#### Theory 
<ul>
  A linked list is a fundamental data structure. It mainly allows efficient insertion and deletion operations compared to arrays. Like arrays, it is also used to implement other data structures like stack, queue and deque.
Linked lists are of several types, including:

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

</li>
</ul>

#### Code 

(A) <br> 
```cpp
//Kanwaljeet singh
//23070123124
//EXP 18 A
//ENTCB2
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

#### Output 
(A) <br> 
![image](https://github.com/user-attachments/assets/d2260541-21d8-4728-bd00-62880ab1f58e)




(B) <br> 
```cpp
//Kanwaljeet singh
//23070123124
//EXP 18 B
//ENTC B2
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

#### Output 
(B) <br> 
<img width="634" alt="EXP 17 B OUTPUT" src="https://github.com/user-attachments/assets/f31632a8-583f-46ef-8a3f-6f99c422fb06">


#### Conclusion 
I learnt the study and implement Linked List in C++.
