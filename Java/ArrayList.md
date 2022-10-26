## ArrayList :

Arraylist class is an arry-based implementation of list Interface . All elements of an ArrayList are stored in a Array. 
ArrayList class is used to implement Resizable-array. 
ArrayList creates an array of obejcts where the array can grow dynamically  

## Difference between Array and ArrayList:
Arrays are static whereas ArrayList is dynamic. Arrays are of fixed length on the other hand ArrayList  can be Resizable.
Arrays can store Primitive data as well as objects , but can't store generics . ArrayList  can store generics as well as objects but it cannot store store data of primitive types. 

## ArrayList in Java:
It is a part of the Java Collection Framework and a class of java.util.package.
![ArrayList](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200624184403/ArrayList.png "ArrayList")

Java ArrayList class can contain duplicate elements.
Java ArrayList class maintains insertion order.
Java ArrayList class is non synchronized
Java ArrayList allows random access because the array works on an index basis.

In ArrayList, manipulation is a little bit slower than the LinkedList in Java because a lot of shifting needs to occur if any element is removed from the array list.
We can not create an array list of the primitive types, such as int, float, char, etc. It is required to use the required wrapper class in such cases. 
For example:
we can declare interger in this form 
ArrayList<Integer> al = new ArrayList<Integer>();// Should be declared in this manner.

## Methods in ArrayList :
add(Object o): This method is used to append a specific element to the end of list.
add(int index, Object element) :  This method is used to insert specific elements in specific index position.
clear(): This method is used to remove all the elements from any list.
contains?(Object o): Returns true if this list contains the specified element.

## For more methods refer to :
(https://www.geeksforgeeks.org/arraylist-in-java/?ref=lbp)

## Basic operations on ArrayList:
Adding element to List
Changing elements
Removing elements
Iterating elements  

## Adding Elements to List :
In this we use the add() method inorder to add an element to the ArrayList 
**Example of Adding Elements to  ArrayList** :
```
import java.util.*;  
  public class ArrayList1{  
  public static void main(String args[]){  
  ArrayList<Integer> al = new ArrayList<Integer>();//Creating arraylist  
  al.add(1);//Adding object in arraylist    
  al.add(2);    
  al.add(3);    
   System.out.println(al);    
  }  
}

**Output**:
[1,2,3]	
```
## Changing Elements
If we want to change the Added elements at specific position we can use the set() method to do that.

**Example of Changing Elements**

```
import java.util.ArrayList; 
class ArrayList1{
    public static void main(String[] args){
        ArrayList<String> al = new ArrayList<String>();
        al.add("Hello");
        al.add("World");
        al.add(1,"Hello");
    System.out.println("Before Changing " +al);
        al.set(1,"Earth");
    System.out.println("After Changing " +al);   
    }
}

**Output**
Before Changing [Hello, Helllo, World]
After Changing [Hello, Earth, World]
```
## Removing elements 
Inorder to Remove elements from an ArrayList we can use remove() method.
remove(object): Simply removing an object from the ArrayList is done using this function. If there are numerous instances of the same item, the first instance is eliminated.
remove(int index):Since an array list is indexed, this method accepts an integer value and eliminates the element that is present in the array list at that particular index. After the element has been removed, all the remaining elements are shifted to the left to cover the empty space, and the object indices are updated.

**Example of Removing Elements**

```
import java.util.ArrayList; 
class ArrayList1{
    public static void main(String[] args){
        ArrayList<String> al = new ArrayList<String>();
        al.add("Hello");
        al.add("World");
        al.add(1,"Hello");
    System.out.println("Before Removing  " +al);
        al.remove(1);
        al.remove("Hello");
    System.out.println("After Removing  "   +al);   
    }
}

**Output**
Before Removing  [Hello, Hello, World]
After Removing  [World]
```
## Iterating elements:
The ArrayList can be iterated through in a variety of ways. The most well-known techniques involve utilising both the advanced for loop and the basic for loop in conjunction with the get() method to retrieve the element at a given index.

**Example of Iterating Elements**:
```
import java.util.ArrayList; 
class ArrayList1{
    public static void main(String[] args){
        ArrayList<String> al = new ArrayList<String>();
        al.add("Hello");
        al.add("World");
        al.add(1,"Hello");
    for (int i = 0; i < al.size(); i++) {
 
            System.out.print(al.get(i) + " ");
        }
 
        System.out.println(); 
    }
}

**Output**
Hello Hello World
```


## For more refer
(https://www.geeksforgeeks.org/arraylist-in-java/?ref=lbp)
(https://www.javatpoint.com/java-arraylist)




 
