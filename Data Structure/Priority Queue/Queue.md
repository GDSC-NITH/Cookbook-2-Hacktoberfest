# Tree Data Structure

A tree is a popular data structure that is non-linear in nature. Unlike other data structures like array, stack, queue, and linked list which are linear in nature, a tree represents a hierarchical structure. The ordering information of a tree is not important. A tree contains nodes and 2 pointers. These two pointers are the left child and the right child of the parent node. Let us understand the terms of tree in detail.

#### Root:
The root of a tree is the topmost node of the tree that has no parent node. There is only one root node in every tree.
#### Edge:
Edge acts as a link between the parent node and the child node.
#### Leaf:
A node that has no child is known as the leaf node. It is the last node of the tree. There can be multiple leaf nodes in a tree.
#### Subtree:
The subtree of a node is the tree considering that particular node as the root node.
#### Depth:
The depth of the node is the distance from the root node to that particular node.
#### Height: 
The height of the node is the distance from that node to the deepest node of that subtree.
#### Height of tree:
The Height of the tree is the maximum height of any node. This is same as the height of root node

#### Why Use Trees? 

1. One reason to use trees might be because you want to store information that naturally forms a hierarchy. For example, the file system on a computer.

2. Trees (with some ordering e.g., BST) provide moderate access/search (quicker than Linked List and slower than arrays). 
3. Trees provide moderate insertion/deletion (quicker than Arrays and slower than Unordered Linked Lists). 
4. Like Linked Lists and unlike Arrays, Trees don’t have an upper limit on the number of nodes as nodes are linked using pointers.

#### Main applications of trees include: 

Manipulate hierarchical data. 
Make information easy to search (see tree traversal). 
Manipulate sorted lists of data. 
As a workflow for compositing digital images for visual effects. 
Router algorithms 
Form of multi-stage decision-making (see business chess). 
Binary Tree: A tree whose elements have at most 2 children is called a binary tree. Since each element in a binary tree can have only 2 children, we typically name them the left and right child. 

Binary Tree Representation: A tree is represented by a pointer to the topmost node of the tree. If the tree is empty, then the value of the root is NULL. 
A Tree node contains the following parts. 

Data 
Pointer to the left child 
Pointer to the right child
In C, we can represent a tree node using structures. In other languages, we can use classes as part of their OOP feature. Below is an example of a tree node with integer data.

// Structure of each node of the tree
  
struct node
{
    int data;
    struct node* left;
    struct node* right;
};
Basic Operation On Binary Tree:

Inserting an element.
Removing an element.
Searching for an element.
Traversing an element. There are three types of traversals in a binary tree which will be discussed ahead.
Auxiliary Operation On Binary Tree:

Finding the height of the tree
Find the level of the tree
Finding the size of the entire tree.
Applications of Binary Tree:

In compilers, Expression Trees are used which is an application of binary tree.
Huffman coding trees are used in data compression algorithms.
Priority Queue is another application of binary tree that is used for searching maximum or minimum in O(1) time complexity.
Binary Tree Traversals:

PreOrder Traversal: Here, the traversal is: root – left child – right child. It means that the root node is traversed first then its left child and finally the right child.
InOrder Traversal: Here, the traversal is: left child – root – right child.  It means that the left child is traversed first then its root node and finally the right child.
PostOrder Traversal: Here, the traversal is: left child – right child – root.  It means that the left child is traversed first then the right child and finally its root node.

### What is a binary tree?
Binary Tree is defined as a Tree data structure with at most 2 children. Since each element in a binary tree can have only 2 children, we typically name them the left and right child.

![ tree structure](https://www.geeksforgeeks.org/wp-content/uploads/binary-tree-to-DLL.png "Tree structure")
##### Binary Tree Representation

A Binary tree is represented by a pointer to the topmost node of the tree. If the tree is empty, then the value of the root is NULL.

##### Binary Tree node contains the following parts:

Data
Pointer to left child
Pointer to right child

### Tree Traversal:
Unlike linear data structures (Array, Linked List, Queues, Stacks, etc) which have only one logical way to traverse them, trees can be traversed in different ways. Following are the generally used methods for traversing trees:

Example:

![ tree structure](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Preorder-from-Inorder-and-Postorder-traversals.jpg "Tree structure")

### Inorder tree traversal:
Algorithm Inorder(tree)

1. Traverse the left subtree, i.e., call Inorder(left->subtree)
2. Visit the root.
3. Traverse the right subtree, i.e., call Inorder(right->subtree)

### Preorder Traversal (Practice): 
Algorithm Preorder(tree)

1. Visit the root.
2. Traverse the left subtree, i.e., call Preorder(left->subtree)
3. Traverse the right subtree, i.e., call Preorder(right->subtree) 

Uses of Preorder:
Preorder traversal is used to create a copy of the tree. Preorder traversal is also used to get prefix expressions on an expression tree.
Example: Preorder traversal for the above-given figure is 1 2 4 5 3.

### Postorder Traversal (Practice): 
Algorithm Postorder(tree)

1. Traverse the left subtree, i.e., call Postorder(left->subtree)
2. Traverse the right subtree, i.e., call Postorder(right->subtree)
3. Visit the root

Uses of Postorder:
Postorder traversal is used to delete the tree. Please see the question for the deletion of a tree for details. Postorder traversal is also useful to get the postfix expression of an expression tree
Example: Postorder traversal for the above-given figure is 4 5 2 3 1

### Insertion in a binary tree
using namespace std;
 
/* A binary tree node has data, pointer to left child
and a pointer to right child */
 
struct Node {
    int data;
    Node* left;
    Node* right;
};
 
// Function to create a new node
Node* CreateNode(int data)
{
    Node* newNode = new Node();
    if (!newNode) {
        cout << "Memory error\n";
        return NULL;
    }
    newNode->data = data;
    newNode->left = newNode->right = NULL;
    return newNode;
}
 
// Function to insert element in binary tree
Node* InsertNode(Node* root, int data)
{
    // If the tree is empty, assign new node address to root
    if (root == NULL) {
        root = CreateNode(data);
        return root;
    }
 
    // Else, do level order traversal until we find an empty
    // place, i.e. either left child or right child of some
    // node is pointing to NULL.
    queue<Node*> q;
    q.push(root);
 
    while (!q.empty()) {
        Node* temp = q.front();
        q.pop();
 
        if (temp->left != NULL)
            q.push(temp->left);
        else {
            temp->left = CreateNode(data);
            return root;
        }
 
        if (temp->right != NULL)
            q.push(temp->right);
        else {
            temp->right = CreateNode(data);
            return root;
        }
    }
}
 
/* Inorder traversal of a binary tree */
 
void inorder(Node* temp)
{
    if (temp == NULL)
        return;
 
    inorder(temp->left);
    cout << temp->data << ' ';
    inorder(temp->right);
}
 
// Driver code
int main()
{
    Node* root = CreateNode(10);
    root->left = CreateNode(11);
    root->left->left = CreateNode(7);
    root->right = CreateNode(9);
    root->right->left = CreateNode(15);
    root->right->right = CreateNode(8);
 
    cout << "Inorder traversal before insertion: ";
    inorder(root);
    cout << endl;
 
    int key = 12;
    root = InsertNode(root, key);
 
    cout << "Inorder traversal after insertion: ";
    inorder(root);
    cout << endl;
 
    return 0;
}

### Deletion in a binary tree

using namespace std;
 
/* A binary tree node has key, pointer to left
child and a pointer to right child */
struct Node {
    int key;
    struct Node *left, *right;
};
 
/* function to create a new node of tree and
return pointer */
struct Node* newNode(int key)
{
    struct Node* temp = new Node;
    temp->key = key;
    temp->left = temp->right = NULL;
    return temp;
};
 
/* Inorder traversal of a binary tree*/
void inorder(struct Node* temp)
{
    if (!temp)
        return;
    inorder(temp->left);
    cout << temp->key << " ";
    inorder(temp->right);
}
 
/* function to delete the given deepest node
(d_node) in binary tree */
void deletDeepest(struct Node* root, struct Node* d_node)
{
    queue<struct Node*> q;
    q.push(root);
 
    // Do level order traversal until last node
    struct Node* temp;
    while (!q.empty()) {
        temp = q.front();
        q.pop();
        if (temp == d_node) {
            temp = NULL;
            delete (d_node);
            return;
        }
        if (temp->right) {
            if (temp->right == d_node) {
                temp->right = NULL;
                delete (d_node);
                return;
            }
            else
                q.push(temp->right);
        }
 
        if (temp->left) {
            if (temp->left == d_node) {
                temp->left = NULL;
                delete (d_node);
                return;
            }
            else
                q.push(temp->left);
        }
    }
}
 
/* function to delete element in binary tree */
Node* deletion(struct Node* root, int key)
{
    if (root == NULL)
        return NULL;
 
    if (root->left == NULL && root->right == NULL) {
        if (root->key == key)
            return NULL;
        else
            return root;
    }
 
    queue<struct Node*> q;
    q.push(root);
 
    struct Node* temp;
    struct Node* key_node = NULL;
 
    // Do level order traversal to find deepest
    // node(temp) and node to be deleted (key_node)
    while (!q.empty()) {
        temp = q.front();
        q.pop();
 
        if (temp->key == key)
            key_node = temp;
 
        if (temp->left)
            q.push(temp->left);
 
        if (temp->right)
            q.push(temp->right);
    }
 
    if (key_node != NULL) {
        int x = temp->key;
        deletDeepest(root, temp);
        key_node->key = x;
    }
    return root;
}
 
// Driver code
int main()
{
    struct Node* root = newNode(10);
    root->left = newNode(11);
    root->left->left = newNode(7);
    root->left->right = newNode(12);
    root->right = newNode(9);
    root->right->left = newNode(15);
    root->right->right = newNode(8);
 
    cout << "Inorder traversal before deletion : ";
    inorder(root);
 
    int key = 11;
    root = deletion(root, key);
 
    cout << endl;
    cout << "Inorder traversal after deletion : ";
    inorder(root);
 
    return 0;
}
