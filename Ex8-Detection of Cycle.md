## Ex8: Detection of Cycle and Finding the Starting Node in a Linked List

## AIM:
To write a program that detects a cycle in a linked list and returns the node where the cycle begins. If there is no cycle, the program should return null.

## Algorithm:

Use Floyd’s Cycle Detection Algorithm (slow and fast pointers).

If pointers meet, a cycle exists.

Move one pointer to the head and traverse step by step.

The point where both pointers meet again is the start of the cycle.

## Program:
```
Program that detects a cycle in a linked list and returns the node where the cycle begins
Developed by: Naresh P.S.
RegisterNumber: 212223040127
Date: 11-11-2025

class Node {
    int data;
    Node next;
    Node(int data) { this.data = data; }
}

public class DetectCycle {
    static Node detectCycle(Node head) {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) {
                slow = head;
                while (slow != fast) {
                    slow = slow.next;
                    fast = fast.next;
                }
                return slow;
            }
        }
        return null;
    }

    public static void main(String[] args) {
        Node head = new Node(3);
        head.next = new Node(2);
        head.next.next = new Node(0);
        head.next.next.next = new Node(-4);
        head.next.next.next.next = head.next; // creates a cycle

        Node startNode = detectCycle(head);
        if (startNode != null)
            System.out.println("Cycle starts at node with value: " + startNode.data);
        else
            System.out.println("No cycle detected");
    }
}
```

Output:
Cycle starts at node with value: 2

Result:

The program successfully detects whether a cycle exists in the linked list and identifies the starting node if present.
