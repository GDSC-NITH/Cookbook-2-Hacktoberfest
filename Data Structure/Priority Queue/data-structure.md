# Learning About Usage of data Structures
 Let's start with learning about how we decide what data we want to choose!!
#### 1. What type of data needs to be stored?:
It might be a possibility that a certain data structure can be the best fit for some kind of data.
#### 2.  Cost of operations: 
If we want to minimize the cost for the operations for the most frequently performed operations. For example, we have a simple list on which we have to perform the search operation; then, we can create an array in which elements are stored in sorted order to perform the binary search. The binary search works very fast for the simple list as it divides the search space into half.
#### 3. Memory usage: 
Sometimes, we want a data structure that utilizes less memory.

### Defining various types of data types:
#### 1. Linera Data Type:
A linear data structure has data elements connected to each other so that elements are arranged in a sequential manner and each element is connected to the element in front of it and behind it. This way, the structure can be traversed in a single run.

Linear data structures can be implemented easily as computer memory is also arranged in a linear manner. There are four types of linear data structures:

a. Array
b. Linked list
c. Stack
d. Queue

#### 2. Non-linear Data Type:
It is a form of data structure where the data elements don’t stay arranged linearly or sequentially. Since the data structure is non-linear, it does not involve a single level. Therefore, a user can’t traverse all of its elements in a single run.

The non-linear data structure is not very easy to implement as compared to the linear data structure. The utilization of computer memory is more efficient in this case.

Different types of non-linear data structures are:


a. Graphs
b. Trees.
c. Maps

## Discussing Each Data Type In Detail 

### 1. Array:
Arrays are defined as the collection of similar types of data items stored at contiguous memory locations. It is one of the simplest data structures where each data element can be randomly accessed by using its index number.

In C programming, they are the derived data types that can store the primitive type of data such as int, char, double, float, etc. For example, if we want to store the marks of a student in 6 subjects, then we don't need to define a different variable for the marks in different subjects. Instead, we can define an array that can store the marks in each subject at the contiguous memory locations.

Properties of array
There are some of the properties of an array that are listed as follows -

Each element in an array is of the same data type and carries the same size that is 4 bytes.
Elements in the array are stored at contiguous memory locations from which the first element is stored at the smallest memory location.
Elements of the array can be randomly accessed since we can calculate the address of each element of the array with the given base address and the size of the data element.
Representation of an array
We can represent an array in various ways in different programming languages. As an illustration, let's see the declaration of array in C language -

Array in DS
As per the above illustration, there are some of the following important points -

Index starts with 0.
The array's length is 10, which means we can store 10 elements.
Each element in the array can be accessed via its index.
Why are arrays required?
Arrays are useful because -

Sorting and searching a value in an array is easier.
Arrays are best to process multiple values quickly and easily.
Arrays are good for storing multiple values in a single variable - In computer programming, most cases require storing a large number of data of a similar type. To store such an amount of data, we need to define a large number of variables. It would be very difficult to remember the names of all the variables while writing the programs. Instead of naming all the variables with a different name, it is better to define an array and store all the elements into it.
Memory allocation of an array
As stated above, all the data elements of an array are stored at contiguous locations in the main memory. The name of the array represents the base address or the address of the first element in the main memory. Each element of the array is represented by proper indexing.

We can define the indexing of an array in the below ways -

0 (zero-based indexing): The first element of the array will be arr[0].
1 (one-based indexing): The first element of the array will be arr[1].
n (n - based indexing): The first element of the array can reside at any random index number.


## 2. Linked List:
Linked List can be defined as collection of objects called nodes that are randomly stored in the memory.
A node contains two fields i.e. data stored at that particular address and the pointer which contains the address of the next node in the memory.
The last node of the list contains pointer to the null.
DS Linked List
Uses of Linked List
The list is not required to be contiguously present in the memory. The node can reside any where in the memory and linked together to make a list. This achieves optimized utilization of space.
list size is limited to the memory size and doesn't need to be declared in advance.
Empty node can not be present in the linked list.
We can store values of primitive types or objects in the singly linked list.
Why use linked list over array?
Till now, we were using array data structure to organize the group of elements that are to be stored individually in the memory. However, Array has several advantages and disadvantages which must be known in order to decide the data structure which will be used throughout the program.

Array contains following limitations:

The size of array must be known in advance before using it in the program.
Increasing size of the array is a time taking process. It is almost impossible to expand the size of the array at run time.
All the elements in the array need to be contiguously stored in the memory. Inserting any element in the array needs shifting of all its predecessors.
Linked list is the data structure which can overcome all the limitations of an array. Using linked list is useful because,

It allocates the memory dynamically. All the nodes of linked list are non-contiguously stored in the memory and linked together with the help of pointers.
Sizing is no longer a problem since we do not need to define its size at the time of declaration. List grows as per the program's demand and limited to the available memory space

## 3. Queue:
A queue can be defined as an ordered list which enables insert operations to be performed at one end called REAR and delete operations to be performed at another end called FRONT.

Applications of Queue
Due to the fact that queue performs actions on first in first out basis which is quite fair for the ordering of actions. There are various applications of queues discussed as below.

Queues are widely used as waiting lists for a single shared resource like printer, disk, CPU.
Queues are used in asynchronous transfer of data (where data is not being transferred at the same rate between two processes) for eg. pipes, file IO, sockets.
Queues are used as buffers in most of the applications like MP3 media player, CD player, etc.
Queue are used to maintain the play list in media players in order to add and remove the songs from the play-list.
Queues are used in operating systems for handling interrupts.

## 4. Stack:
A Stack is a linear data structure that follows the LIFO (Last-In-First-Out) principle. Stack has one end, whereas the Queue has two ends (front and rear). It contains only one pointer top pointer pointing to the topmost element of the stack. Whenever an element is added in the stack, it is added on the top of the stack, and the element can be deleted only from the stack. In other words, a stack can be defined as a container in which insertion and deletion can be done from the one end known as the top of the stack.

Some key points related to stack
It is called as stack because it behaves like a real-world stack, piles of books, etc.
A Stack is an abstract data type with a pre-defined capacity, which means that it can store the elements of a limited size.
It is a data structure that follows some order to insert and delete the elements, and that order can be LIFO or FILO.
Working of Stack
Stack works on the LIFO pattern. As we can observe in the below figure there are five memory blocks in the stack; therefore, the size of the stack is 5.

Suppose we want to store the elements in a stack and let's assume that stack is empty. We have taken the stack of size 5 as shown below in which we are pushing the elements one by one until the stack becomes full.

DS Stack Introduction
Since our stack is full as the size of the stack is 5. In the above cases, we can observe that it goes from the top to the bottom when we were entering the new element in the stack. The stack gets filled up from the bottom to the top.

When we perform the delete operation on the stack, there is only one way for entry and exit as the other end is closed. It follows the LIFO pattern, which means that the value entered first will be removed last. In the above case, the value 5 is entered first, so it will be removed only after the deletion of all the other elements.

## 5. Tree:
We read the linear data structures like an array, linked list, stack and queue in which all the elements are arranged in a sequential manner. The different data structures are used for different kinds of data.

Some factors are considered for choosing the data structure:

What type of data needs to be stored?: It might be a possibility that a certain data structure can be the best fit for some kind of data.
Cost of operations: If we want to minimize the cost for the operations for the most frequently performed operations. For example, we have a simple list on which we have to perform the search operation; then, we can create an array in which elements are stored in sorted order to perform the binary search. The binary search works very fast for the simple list as it divides the search space into half.
Memory usage: Sometimes, we want a data structure that utilizes less memory.
A tree is also one of the data structures that represent hierarchical data. Suppose we want to show the employees and their positions in the hierarchical form then it can be represented as shown below:

Tree
The above tree shows the organization hierarchy of some company. In the above structure, john is the CEO of the company, and John has two direct reports named as Steve and Rohan. Steve has three direct reports named Lee, Bob, Ella where Steve is a manager. Bob has two direct reports named Sal and Emma. Emma has two direct reports named Tom and Raj. Tom has one direct report named Bill. This particular logical structure is known as a Tree. Its structure is similar to the real tree, so it is named a Tree. In this structure, the root is at the top, and its branches are moving in a downward direction. Therefore, we can say that the Tree data structure is an efficient way of storing the data in a hierarchical way.

##### Let's understand some key points of the Tree data structure.

A tree data structure is defined as a collection of objects or entities known as nodes that are linked together to represent or simulate hierarchy.
A tree data structure is a non-linear data structure because it does not store in a sequential manner. It is a hierarchical structure as elements in a Tree are arranged in multiple levels.
In the Tree data structure, the topmost node is known as a root node. Each node contains some data, and data can be of any type. In the above tree structure, the node contains the name of the employee, so the type of data would be a string.
Each node contains some data and the link or reference of other nodes that can be called children.
Some basic terms used in Tree data structure.

Let's consider the tree structure, which is shown below:

##### Tree
In the above structure, each node is labeled with some number. Each arrow shown in the above figure is known as a link between the two nodes.

##### Root:
The root node is the topmost node in the tree hierarchy. In other words, the root node is the one that doesn't have any parent. In the above structure, node numbered 1 is the root node of the tree. If a node is directly linked to some other node, it would be called a parent-child relationship.
##### Child node:
If the node is a descendant of any node, then the node is known as a child node.
##### Parent:
If the node contains any sub-node, then that node is said to be the parent of that sub-node.
##### Sibling:
The nodes that have the same parent are known as siblings.
##### Leaf Node:-
The node of the tree, which doesn't have any child node, is called a leaf node. A leaf node is the bottom-most node of the tree. There can be any number of leaf nodes present in a general tree. Leaf nodes can also be called external nodes.
##### Internal nodes:
A node has atleast one child node known as an internal
##### Ancestor node:-
An ancestor of a node is any predecessor node on a path from the root to that node. The root node doesn't have any ancestors. In the tree shown in the above image, nodes 1, 2, and 5 are the ancestors of node 10.
##### Descendant:
The immediate successor of the given node is known as a descendant of a node. In the above figure, 10 is the descendant of node 5.

## 6. Map:
An unordered collection of key-value pair items is represented by a map data type. Assign the map data type to ports in order to pass map data via transformations. A map element is a key and value pair that corresponds to one object and maps it to another. The Spark engine can read and write map data from complicated files, as well as pass map data through mapping.

A key-value pair is analogous to looking up a word in a dictionary. The key is the word, and the value is the term's meaning or definition. Similarly, the key-value pair in computing associates two bits of data, and one-piece, the "key," may be used to search up the other component, the "value." A map array data type is an ADT (abstract data type) that stores a key-value pair (k-v) in an array. The "key" is a data identifier, while the "value" is the material that is being identified or stored. Each locker at your school has a different key or a different combination lock. If you were to list the locker number and the key for each locker, the "key" would be the locker number and the "value" would be the combination lock or key number that corresponds to each locker. When considering all of the states in the United States and their capitals, the "key" would be the state name and the capital.

The map data type has a few distinguishing characteristics. Because the keys are one-of-a-kind, no duplicate keys are conceivable. For example, if you need to list the names and populations of all the towns in the United States, the map data type cannot be utilised since town names repeat. Washington is repeated in Washington State, New Jersey, and Wisconsin.

When data has previously been recorded into a map data type, it may be viewed in three ways:

You can view simply the list of keys,
Only the list of values, or both.
Both keys and values can be seen as matched pairs.
The map data type is implemented in Java by several Java classes, including HashMap, HashTable, and TreeMap. The keys and values in HashMap are not sorted. The values in TreeMap are arranged by the key. The HashTable is synchronised and does not allow null keys or values.

The map data type is referred to as an associative array because, like an array, it is a collection of values rather than a single value, as an Int or a String is. Furthermore, each distinct key is associated with a value, resulting in an associative array.
## 7. Graph:
A graph can be defined as group of vertices and edges that are used to connect these vertices. A graph can be seen as a cyclic tree, where the vertices (Nodes) maintain any complex relationship among them instead of having parent child relationship.

Definition
A graph G can be defined as an ordered set G(V, E) where V(G) represents the set of vertices and E(G) represents the set of edges which are used to connect these vertices.

A Graph G(V, E) with 5 vertices (A, B, C, D, E) and six edges ((A,B), (B,C), (C,E), (E,D), (D,B), (D,A)) is shown in the following figure.


Graph
Directed and Undirected Graph
A graph can be directed or undirected. However, in an undirected graph, edges are not associated with the directions with them. An undirected graph is shown in the above figure since its edges are not attached with any of the directions. If an edge exists between vertex A and B then the vertices can be traversed from B to A as well as A to B.

In a directed graph, edges form an ordered pair. Edges represent a specific path from some vertex A to another vertex B. Node A is called initial node while node B is called terminal node.

A directed graph is shown in the following figure.


Graph
#### Graph Terminology
##### Path
A path can be defined as the sequence of nodes that are followed in order to reach some terminal node V from the initial node U.

##### Closed Path
A path will be called as closed path if the initial node is same as terminal node. A path will be closed path if V0=VN.

##### Simple Path
If all the nodes of the graph are distinct with an exception V0=VN, then such path P is called as closed simple path.

##### Cycle
A cycle can be defined as the path which has no repeated edges or vertices except the first and last vertices.

##### Connected Graph
A connected graph is the one in which some path exists between every two vertices (u, v) in V. There are no isolated nodes in connected graph.

##### Complete Graph
A complete graph is the one in which every node is connected with all other nodes. A complete graph contain n(n-1)/2 edges where n is the number of nodes in the graph.

##### Weighted Graph
In a weighted graph, each edge is assigned with some data such as length or weight. The weight of an edge e can be given as w(e) which must be a positive (+) value indicating the cost of traversing the edge.

##### Digraph
A digraph is a directed graph in which each edge of the graph is associated with some direction and the traversing can be done only in the specified direction.

##### Loop
An edge that is associated with the similar end points can be called as Loop.

##### Adjacent Nodes
If two nodes u and v are connected via an edge e, then the nodes u and v are called as neighbours or adjacent nodes.

##### Degree of the Node
A degree of a node is the number of edges that are connected with that node. A node with degree 0 is called as isolated node.
