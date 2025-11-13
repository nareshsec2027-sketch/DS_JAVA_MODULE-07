## Ex7: Removal of Nodes with a Specific Value from a Linked List

## AIM:
To write a Java program that removes all nodes from a linked list whose value matches a given integer (val).

## Algorithm:

Create a linked list.

Traverse through the list.

If a node’s data equals val, remove that node.

Continue until the end of the list.

Display the modified linked list.

## Program:
```
Program to remove all nodes with a specific value from a Linked List
Developed by: Naresh P.S.
RegisterNumber: 212223040127
Date: 11-11-2025

class Node {
    int data;
    Node next;
    Node(int data) { this.data = data; }
}

public class RemoveNodes {
    static Node removeElements(Node head, int val) {
        Node dummy = new Node(0);
        dummy.next = head;
        Node current = dummy;

        while (current.next != null) {
            if (current.next.data == val)
                current.next = current.next.next;
            else
                current = current.next;
        }
        return dummy.next;
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
        head.next.next = new Node(10);
        head.next.next.next = new Node(30);

        int val = 10;
        head = removeElements(head, val);
        System.out.print("Updated Linked List: ");
        printList(head);
    }
}
```

Output:
Updated Linked List: 20 30

Result:

The Java program successfully removes all nodes with the specified value from the linked list.
