## Ex6: Right Rotation LinkedList

## AIM:

To write a Java program to create a singly linked list, rotate the linked list to the right by k positions, and display the rotated linked list.

## Algorithm:

Create a singly linked list.

Count the total number of nodes (n).

Compute k = k % n to handle rotations greater than list size.

Find the (n–k)th node and make it the new head.

Link the old tail to the old head to complete rotation.

Display the rotated linked list.

## Program:
```
Program to perform Right Rotation on Linked List
Developed by: Naresh P.S.
RegisterNumber: 1731
Date: 11-11-2025


class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class RightRotationLinkedList {
    static Node rotateRight(Node head, int k) {
        if (head == null || head.next == null || k == 0) return head;
        
        Node temp = head;
        int length = 1;
        while (temp.next != null) {
            temp = temp.next;
            length++;
        }
        temp.next = head;
        k = k % length;
        int stepsToNewHead = length - k;
        Node newTail = temp;
        while (stepsToNewHead-- > 0)
            newTail = newTail.next;
        Node newHead = newTail.next;
        newTail.next = null;
        return newHead;
    }

    static void printList(Node head) {
        while (head != null) {
            System.out.print(head.data + " ");
            head = head.next;
        }
    }

    public static void main(String[] args) {
        Node head = new Node(10);
        head.next = new Node(20);
        head.next.next = new Node(30);
        head.next.next.next = new Node(40);
        head.next.next.next.next = new Node(50);

        int k = 2;
        head = rotateRight(head, k);
        System.out.print("Rotated Linked List: ");
        printList(head);
    }
}
```

Output:
Rotated Linked List: 40 50 10 20 30

Result:

Thus, the Java program to perform right rotation on a linked list is implemented successfully.
