# Performing some important operations on Linked List in C

## Accessing elements of a linked list
##### Code:
using System;
  
public class LinkedList {
    Node head; // head of list
  
    /* Linked list Node. This inner
    class is made static so that
    main() can access it */
    public class Node {
        public int data;
        public Node next;
        public Node(int d)
        {
            data = d;
            next = null;
  
        } // Constructor
    }
  
    /* This function prints contents of
    linked list starting from head */
    public void printList()
    {
        Node n = head;
        while (n != null) {
            Console.Write(n.data + " ");
            n = n.next;
        }
    }
  
    // Driver's code
    public static void Main(String[] args)
    {
        /* Start with the empty list. */
        LinkedList llist = new LinkedList();
  
        llist.head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);
  
        llist.head.next = second; // Link first node with
                                  // the second node
        second.next
            = third; // Link second node with the third node
  
        // Function call
        llist.printList();
    }
}

## Adding an element in linked list
##### Code:
struct node
{
    int val;
    struct node *next;
} 
*start;


void insert(int x, int pos)
{
    struct node *new = (struct node *)malloc(sizeof(struct node));
    new->val = x;
    if(start == NULL)
    {
        new->next = NULL;
        start = new;
    }
    else
    {
        struct node *ptr = start;
        while(ptr->val != pos)
        {
            if(ptr->next == NULL)
            {
                printf("Invalid position!\n");
                return;
            }
        ptr = ptr->next;
        }
        new->next = ptr->next;
        ptr->next = new;
    }
    printf("Inserted %d\n", x);
}

## Adding an element in front of linked list
##### Code:
void insertFront(int x)
{
    struct node *new = (struct node *)malloc(sizeof(struct node));
    new->val = x;
    if(start == NULL)
    {
        new->next = NULL;
        start = new;
    }
    else
    {
        new->next = start;
        start = new;
    }
    printf("Inserted %d at front\n", x);
}

### Print the middle term of a given linked list
##### Code:
using System;
 
public class ABC {
 
    /*Creating a new Node*/
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
 
    /*Function to add a new Node*/
    public void pushNode(int data)
    {
        Node new_node = new Node(data);
        new_node.next = head;
        head = new_node;
    }
 
    /*Displaying the elements in the list*/
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
 
    /*Finding the length of the list.*/
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
 
    /*Printing the middle element of the list.*/
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


## Flatening a Linked List
##### Code:
using System;
public class List {
    Node head; // head of list
 
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
 
    // An utility function to merge two sorted linked lists
    Node merge(Node a, Node b)
    {
        // if first linked list is empty then second
        // is the answer
        if (a == null)
            return b;
 
        // if second linked list is empty then first
        // is the result
        if (b == null)
            return a;
 
        // compare the data members of the two linked lists
        // and put the larger one in the result
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
        // Base Cases
        if (root == null || root.right == null)
            return root;
 
        // recur for list on right
        root.right = flatten(root.right);
 
        // now merge
        root = merge(root, root.right);
 
        // return the root
        // it will be in turn merged with its left
        return root;
    }
 
    /*
     * Utility function to insert a node at beginning
     * of the linked list
     */
    Node Push(Node head_ref, int data)
    {
        /*
         * 1 & 2: Allocate the Node & Put in the data
         */
        Node new_node = new Node(data);
 
        /* 3. Make next of new Node as head */
        new_node.down = head_ref;
 
        /* 4. Move the head to point to new Node */
        head_ref = new_node;
 
        /* 5. return to link it back */
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
 
    // Driver's code
    public static void Main(String[] args)
    {
        List L = new List();
 
        /*
         * Let us create the following linked list 5 -> 10
         * -> 19 -> 28 | | | | V V V V 7 20 22 35 | | | V V
         * V 8 50 40 | | V V 30 45
         */
 
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
