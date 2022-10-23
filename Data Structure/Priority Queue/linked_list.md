# Performing some important operations on Linked List in C
## Accessing elements of a linked list
##### Code:
using System;

public class LinkedList { Node head; // head of list


public class Node {
    public int data;
    public Node next;
    public Node(int d)
    {
        data = d;
        next = null;

    } 
}


public void printList()
{
    Node n = head;
    while (n != null) {
        Console.Write(n.data + " ");
        n = n.next;
    }
}

public static void Main(String[] args)
{
    
    LinkedList llist = new LinkedList();

    llist.head = new Node(1);
    Node second = new Node(2);
    Node third = new Node(3);

    llist.head.next = second; 
    second.next
        = third; 
    llist.printList();
}
}

## Print the middle term of a given linked list
##### Code:
using System;

public class ABC {

class Node {
    public int data;
    public Node next;
    public Node(int data)
    {
        this.data = data;
        this.next = null;
    }
}

Node head;


public void pushNode(int data)
{
    Node new_node = new Node(data);
    new_node.next = head;
    head = new_node;
}


public void printNode()
{
    Node temp = head;
    while (temp != null) {
        Console.Write(temp.data + "->");
        temp = temp.next;
    }
    Console.Write("Null"
                  + "\n");
}


public int getLen()
{
    int length = 0;
    Node temp = head;
    while (temp != null) {
        length++;
        temp = temp.next;
    }
    return length;
}


public void printMiddle()
{
    if (head != null) {
        int length = getLen();
        Node temp = head;
        int middleLength = length / 2;
        while (middleLength != 0) {
            temp = temp.next;
            middleLength--;
        }
        Console.Write("The middle element is ["
                      + temp.data + "]");
        Console.WriteLine();
    }
}

static public void Main()
{

    // Code
    ABC list = new ABC();
    for (int i = 5; i >= 1; i--) 
    {
        list.pushNode(i);
        list.printNode();
        list.printMiddle();
    }
}

Flatening a Linked List
Code:
using System; public class List { Node head; // head of list

/* Linked list Node */
public

    class Node {
    public

        int data;
    public

        Node right,
        down;

    public

        Node(int data)
    {
        this.data = data;
        right = null;
        down = null;
    }
}


Node merge(Node a, Node b)
{
   
    if (a == null)
        return b;

    if (b == null)
        return a;

  
    Node result;

    if (a.data < b.data) {
        result = a;
        result.down = merge(a.down, b);
    }

    else {
        result = b;
        result.down = merge(a, b.down);
    }

    result.right = null;
    return result;
}

Node flatten(Node root)
{
    
    if (root == null || root.right == null)
        return root;

   
    root.right = flatten(root.right);

   
    root = merge(root, root.right);

   
    return root;
}


Node Push(Node head_ref, int data)
{
   
    Node new_node = new Node(data);

   
    new_node.down = head_ref;

   
    head_ref = new_node;

    return head_ref;
}

void printList()
{
    Node temp = head;
    while (temp != null) {
        Console.Write(temp.data + " ");
        temp = temp.down;
    }
    Console.WriteLine();
}


public static void Main(String[] args)
{
    List L = new List();


    L.head = L.Push(L.head, 30);
    L.head = L.Push(L.head, 8);
    L.head = L.Push(L.head, 7);
    L.head = L.Push(L.head, 5);

    L.head.right = L.Push(L.head.right, 20);
    L.head.right = L.Push(L.head.right, 10);

    L.head.right.right = L.Push(L.head.right.right, 50);
    L.head.right.right = L.Push(L.head.right.right, 22);
    L.head.right.right = L.Push(L.head.right.right, 19);

    L.head.right.right.right
        = L.Push(L.head.right.right.right, 45);
    L.head.right.right.right
        = L.Push(L.head.right.right.right, 40);
    L.head.right.right.right
        = L.Push(L.head.right.right.right, 35);
    L.head.right.right.right
        = L.Push(L.head.right.right.right, 20);

    // Function call
    L.head = L.flatten(L.head);

    L.printList();
}
}
