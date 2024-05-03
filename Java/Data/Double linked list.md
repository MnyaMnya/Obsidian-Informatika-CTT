> Doubly linked list is a data structure that has reference to both the previous and next nodes in the list. It provides simplicity to traverse, insert and delete the nodes in both directions in a list.

In a doubly linked list, each node contains three data members:

- **data:** The data stored in the node
- **next:** It refers to the reference to the next node
- **prev:** It refers to the reference to the previous node

### **Creation of Doubly Linked Lists in Java:**

To create a doubly linked list, first, we need to define a Node class that has three data members that will store the data stored in the node, the reference to the next node, and the reference to the previous node.



```java

public class Node { 
    int data; 
    Node prev; 
    Node next; 
  
    public Node(int data) 
    { 
        this.data = data; 
        this.prev = null; 
        this.next = null; 
    } 
} 

```

Now we need to create a doubly linked list class that will contain two variables head and tail which will be referenced to the first and last node of the list respectively and also a constructor which will initialize both head and tail to the null.

```java
public class DoublyLinkedList {

    Node head;

    Node tail;

    public DoublyLinkedList()

    {

        this.head = null;

        this.tail = null;

    }

}
```



### **Traversing a Doubly Linked List in Java:**

> To traverse in a doubly linked list, we will start from the head node and follow the next reference until we reach the end of the list similarly, we can also start from the tail node and follow the prev until we reach the head of the node.

Below is the code to traverse a linked list:

```java

// Traversing from head to the end of the list 
public void traverseForward() 
{ 
    Node current = head; 
    while (current != null) { 
        System.out.print(current.data + " "); 
        current = current.next; 
    } 
} 
// Traversing from tail to the head 
public void traverseBackward() 
{ 
    Node current = tail; 
    while (current != null) { 
        System.out.print(current.data + " "); 
        current = current.prev; 
    } 
} 

```


### **Insertion in a Doubly Linked List in Java:**

> To insert a node in a doubly linked list, first, we will need to create a new node that is going to be inserted and update the references of the adjacent nodes to add the new node and will update the head or tail of the list if the new node is being inserted at the beginning or end of the list.

A node can be added to a Doubly Linked List in three ways:

- Insertion at the beginning of the list
- Insertion at a specific position in the list
- Insertion at the end of the list

**1) Insertion at the beginning of the list:**

Create a new node to be inserted. Set the next pointer of the new node to the current head of the doubly linked list. Set the previous pointer of the new node to null, as it will be the new head. If the doubly linked list is not empty (i.e., the current head is not null), set the previous pointer of the current head to the new node.

![Insertion at the beginning of the list](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL_add_front1.png)

 Insertion at the beginning of the list

Below is the code to insert a node at the front of the linked list:

```java

public void insertAtBeginning(int data) 
{ 
    Node temp = new Node(data); 
    if (head == null) { 
        head = temp; 
        tail = temp; 
    } 
    else { 
        temp.next = head; 
        head.prev = temp; 
        head = temp; 
    } 
} 

```

**2) Insertion at a specific position in the list:**

Create a new node with the data to be inserted. Set the next pointer of the new node to the next node of the node at given position. Set the previous pointer of the new node to the node at given position. Set the next pointer of the node at the given position to the new node. If the next node of the new node is not null, set its previous pointer to the new node.

![Insertion at a specific position in the list](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL_add_middle1.png)

Insertion at a specific position in the list

Below is the code to insert a node at a specific position in the linked list:

```java

public void insertAtPosition(int data, int position) 
{ 
    Node temp = new Node(data); 
    if (position == 1) { 
        insertAtBeginning(data); 
    } 
    else { 
        Node current = head; 
        int currPosition = 1; 
        while (current != null && currPosition < position) { 
            current = current.next; 
            currPosition++; 
        } 
        if (current == null) { 
            insertAtEnd(data); 
        } 
        else { 
            temp.next = current; 
            temp.prev = current.prev; 
            current.prev.next = temp; 
            current.prev = temp; 
        } 
    } 
} 

```

**3) Insertion at the end of the list:**

First, we create a new node temp with the given data and then we will check if the list is empty or not. If it is empty then we will set both the head and tail to the new node temp, and if the list is not empty, traverse to the last node of the doubly linked list. Set the next pointer of the last node to the new node. Set the previous pointer of the new node to the current last node. Set the next pointer of the new node to null, as it will be the last node in the list.

![Insertion at the end of the list](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL_add_end1.png)

Insertion at the end of the list

Below is the code to insert a node at the end of the linked list:

```java

public void insertAtEnd(int data) 
{ 
    Node temp = new Node(data); 
    if (tail == null) { 
        head = temp; 
        tail = temp; 
    } 
    else { 
        tail.next = temp; 
        temp.prev = tail; 
        tail = temp; 
    } 
} 

```


### **Deletion in a Doubly Linked List in Java:**

> To delete a node in a doubly linked list, first, we need to update the references of the adjacent nodes to delete the node and will update the head or tail of the list if the new node is being inserted at the beginning or end of the list.

The deletion of a node in a doubly-linked list can be divided into three main categories:

- Deletion of the first node in the list.
- Deletion of a node at a specific position in the list.
- Deletion of the last node in the list.

**Example:**

![](https://media.geeksforgeeks.org/wp-content/uploads/Delete_lincked_list.jpg)

**1) Deletion of the first node in the list:**

First, we will check if the list is empty if it is then we return, and if there is only one node in the list then we will set both the head and tail to null otherwise we will simply set the head node to the next node of the current head in the list, and set the previous reference of the new head node to null.

- **After the deletion of the first node.**

![Deletion of the first node in the list](https://media.geeksforgeeks.org/wp-content/uploads/20200318143640/linked11.png)

Deletion of the first node in the list

Below is the code of Deletion of the first node in the list:

```java

public void deleteAtBeginning() 
{ 
    if (head == null) { 
        return; 
    } 
  
    if (head == tail) { 
        head = null; 
        tail = null; 
        return; 
    } 
  
    Node temp = head; 
    head = head.next; 
    head.prev = null; 
    temp.next = null; 
}

```


**2) Deletion of a node at a specific position in the list:**

If the given position is 1 (i.e., the first node), update the head of the doubly linked list to be the next node of the current head. Traverse to the node at the given position, keeping track of the previous node. Set the next pointer of the previous node to the next node of the node to be deleted. If the next node of the node to be deleted is not null, set its previous pointer to the previous node. Delete the node.

- **After the deletion of the 2nd node.**

![Deletion of a node at a specific position in the list](https://media.geeksforgeeks.org/wp-content/uploads/Delete_lincked_list3.jpg)

Deletion of a node at a specific position in the list

Below is the code of Deletion of a node at a specific position in the list:

```java

public void delete(int pos) 
{ 
    if (head == null) { 
        return; 
    } 
  
    if (pos == 1) { 
        deleteAtBeginning(); 
        return; 
    } 
  
    Node current = head; 
    int count = 1; 
  
    while (current != null && count != pos) { 
        current = current.next; 
        count++; 
    } 
  
    if (current == null) { 
        System.out.println("Position wrong"); 
        return; 
    } 
  
    if (current == tail) { 
        deleteAtEnd(); 
        return; 
    } 
  
    current.prev.next = current.next; 
    current.next.prev = current.prev; 
    current.prev = null; 
    current.next = null; 
} 

```



**3) Deletion of the last node in the list:**

First, we will check if the list is empty if it is then we return, and if there is only one node in the list then we will set both the head and tail to null otherwise we will simply set the tail node to the previous node of the current tail node in the list, set the prev of the current tail node as null and set the next reference of the new tail node to null.

![Deletion of the last node in the list](https://media.geeksforgeeks.org/wp-content/uploads/Delete_lincked_list4.jpg)

Deletion of the last node in the list

Below is the code for the Deletion of the last node in the list:

```java

public void deleteAtEnd() 
{ 
    if (tail == null) { 
        return; 
    } 
  
    if (head == tail) { 
        head = null; 
        tail = null; 
        return; 
    } 
  
    Node temp = tail; 
    tail = tail.prev; 
    tail.next = null; 
    temp.prev = null; 
}

```


Below is the code to test the above functions:

```java

// Java program for the above approach 
import java.io.*; 
  
class node { 
    node prev; 
    int data; 
    node next; 
  
    // A constructor is called here 
    node(int value) 
    { 
  
        // By default previous pointer is 
        // pointed to NULL 
        prev = null; 
  
        // Value is assigned to the data 
        data = value; 
  
        // By default next pointer is pointed 
        // to NULL 
        next = null; 
    } 
} 
  
class GFG { 
  
    // Declaring an empty doubly linked list 
    static node head = null; 
    static node tail = null; 
    static void insertAtBeginning(int data) 
    { 
        node temp = new node(data); 
        if (head == null) { 
            head = temp; 
            tail = temp; 
        } 
        else { 
            temp.next = head; 
            head.prev = temp; 
            head = temp; 
        } 
    } 
  
    static void insertAtEnd(int data) 
    { 
        node temp = new node(data); 
        if (tail == null) { 
            head = temp; 
            tail = temp; 
        } 
        else { 
            tail.next = temp; 
            temp.prev = tail; 
            tail = temp; 
        } 
    } 
  
    static void insertAtPosition(int data, int position) 
    { 
        node temp = new node(data); 
        if (position == 1) { 
            insertAtBeginning(data); 
        } 
        else { 
            node current = head; 
            int currPosition = 1; 
            while (current != null
                   && currPosition < position) { 
                current = current.next; 
                currPosition++; 
            } 
            if (current == null) { 
                insertAtEnd(data); 
            } 
            else { 
                temp.next = current; 
                temp.prev = current.prev; 
                current.prev.next = temp; 
                current.prev = temp; 
            } 
        } 
    } 
  
    static void deleteAtBeginning() 
    { 
        if (head == null) { 
            return; 
        } 
  
        if (head == tail) { 
            head = null; 
            tail = null; 
            return; 
        } 
  
        node temp = head; 
        head = head.next; 
        head.prev = null; 
        temp.next = null; 
    } 
  
    static void deleteAtEnd() 
    { 
        if (tail == null) { 
            return; 
        } 
  
        if (head == tail) { 
            head = null; 
            tail = null; 
            return; 
        } 
  
        node temp = tail; 
        tail = tail.prev; 
        tail.next = null; 
        temp.prev = null; 
    } 
  
    static void deleteAtSpecificPosition(int pos) 
    { 
        if (head == null) { 
            return; 
        } 
  
        if (pos == 1) { 
            deleteAtBeginning(); 
            return; 
        } 
  
        node current = head; 
        int count = 1; 
  
        while (current != null && count != pos) { 
            current = current.next; 
            count++; 
        } 
  
        if (current == null) { 
            System.out.println("Position wrong"); 
            return; 
        } 
  
        if (current == tail) { 
            deleteAtEnd(); 
            return; 
        } 
  
        current.prev.next = current.next; 
        current.next.prev = current.prev; 
        current.prev = null; 
        current.next = null; 
    } 
  
    static void display(node head) 
    { 
        node temp = head; 
        while (temp != null) { 
            System.out.print(temp.data + " --> "); 
            temp = temp.next; 
        } 
        System.out.println("NULL"); 
    } 
  
    // Drivers code 
    public static void main(String[] args) 
    { 
        insertAtEnd(1); 
        insertAtEnd(2); 
        insertAtEnd(3); 
        insertAtEnd(4); 
        insertAtEnd(5); 
  
        System.out.print("After insertion at tail: "); 
        display(head); 
  
        System.out.print("After insertion at head: "); 
        insertAtBeginning(0); 
        display(head); 
  
        insertAtPosition(6, 2); 
        System.out.print( 
            "After insertion at 2nd position: "); 
        display(head); 
  
        deleteAtBeginning(); 
        System.out.print( 
            "After deletion at the beginning: "); 
        display(head); 
  
        deleteAtEnd(); 
        System.out.print("After deletion at the end: "); 
        display(head); 
  
        deleteAtSpecificPosition(2); 
        System.out.print( 
            "After deletion at 2nd position: "); 
        display(head); 
    } 
}

```


**Output**

After insertion at tail: 
1 --> 2 --> 3 --> 4 --> 5 --> NULL
After insertion at head: 
0 --> 1 --> 2 --> 3 --> 4 --> 5 --> NULL
After insertion at 2nd position: 
0 --> 6 --> 1 --> 2 --> 3 --> 4 --> 5 --> NULL
After deletion at the beginning: 
6 --> 1 --> 2 --> 3 --> 4 --> 5 --> NULL
After deletion at the end: 
6 --> 1 --> 2 --> 3 --> 4 --> NULL
After deletion at 2nd position: 
6 --> 2 --> 3 --> 4 --> NULL