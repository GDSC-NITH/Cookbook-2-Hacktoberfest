## ArrayList :

ArrayList class is an array-based implementation of list Interface . All elements of an ArrayList are stored in a Array. 
ArrayList class is used to implement Resizable-array. 
ArrayList creates an array of obejcts where the array can grow dynamically  

## Difference between Array and ArrayList:
Arrays are static whereas ArrayList is dynamic. Arrays are of fixed length on the other hand ArrayList  can be Resizable.
Arrays can store Primitive data as well as objects , but can't store generics . ArrayList  can store generics as well as objects but it cannot store store data of primitive types. 

## ArrayList in Java:
It is a part of the Java Collection Framework and a class of java.util.package
<br>

![ ArrayList](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200624184403/ArrayList.png "ArrayList")

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

## Example of Simple ArrayList :

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

//output:
[1,2,3]	

## References:
(https://www.geeksforgeeks.org/arraylist-in-java/?ref=lbp)
(https://www.javatpoint.com/java-arraylist)
