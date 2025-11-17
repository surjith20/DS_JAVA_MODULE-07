# Ex6 Right Rotation LinkedList
## DATE: 17-11-2025
## AIM:
To write a Java  program to:
Create a singly linked list.
Rotate the linked list to the right by k positions.
Display the rotated linked list.
## Algorithm
1. Create a singly linked list by inserting nodes one by one.

2. Count the total number of nodes and compute k = k % length to handle large rotations.
   
3. Connect the last node to the head to form a circular linked list.

4. Move (length − k) steps to find the new tail of the rotated list.

5. Set the next node as the new head and break the circular link to complete the rotation.
 

## Program:
```
/*
Program to  Right Rotation LinkedList
Developed by: JANARTHANAN K
RegisterNumber:  212223040072
*/

public class RotateLinkedList {

    // Node class inside the main class
    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    Node head;

    // Insert at end
    public void insert(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        temp.next = newNode;
    }

    // Rotate right by k positions
    public void rotateRight(int k) {
        if (head == null || k == 0) return;

        // Find length and last node
        Node temp = head;
        int length = 1;
        while (temp.next != null) {
            temp = temp.next;
            length++;
        }

        // Make it circular
        temp.next = head;
        k = k % length;

        int steps = length - k;
        while (steps-- > 0) {
            temp = temp.next;
        }

        // New head
        head = temp.next;
        temp.next = null;
    }

    // Display list
    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }

    // MAIN METHOD → This is the entry point
    public static void main(String[] args) {
        RotateLinkedList list = new RotateLinkedList();

        list.insert(10);
        list.insert(20);
        list.insert(30);
        list.insert(40);
        list.insert(50);

        int k = 2;
        list.rotateRight(k);

        System.out.println("Rotated List:");
        list.display();
    }
}


```

## Output:

<img width="1919" height="622" alt="image" src="https://github.com/user-attachments/assets/846de303-9524-4567-a3ba-0362f46c35ca" />


## Result:
Thus, the C program to perfom right rotation on linked list is implemented successfully.
