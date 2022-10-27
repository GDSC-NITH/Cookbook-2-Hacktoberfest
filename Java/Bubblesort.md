## Sorting :
A Sorting Algorithm is used to rearrange a given array or list of elements according to a comparison operator on the elements. 
The comparison operator is used to decide the new order of elements in the respective data structure.


## Bubble sorting :
Bubble sort is the simplest sorting Algorithm that works by repeatedly swapping the adjacent elements if they are in the wrong order. This sorting Algorithm is bot not suitable for Large data sets.
Bubble sort works on the repeatedly swapping of adjacent elements until they are not in the intended order



## Working of Bubble sort :
let's consider array a[] = {4,2,6,1}

<br>
**First Iteration**:
it will compare the very first Two elements comparing them to check Which one is greater
{4 2 6 1} --> {2 4 6 1} here 4 > 2 so it swaps the elements
{2 4 6 1} --> {2 4 6 1} since 6 > 4 its already in order algorithm does not swap them.
{2 4 6 1} --> {2 4 1 6} since 6 > 1 


**Second Iteration** :
Now, during second iteration it should look like this:
{2 4 1 6 } --> {2 4 1 6} Here it is already in order so no need to swap
{2 4 1 6 } --> {2 1 4 6} swap since 4 > 1
{2 1 4 6} --> {2 1 4 6 } 6 > 4 already in order no need to swap.
{2 1 4 6 } --> {1 2 4 6 } 2 > 1 swap.


**Third Iteration**

Now, the array is already sorted, but our algorithm does not know if it is completed.
The algorithm needs one whole pass without any swap to know it is sorted.

{1 2 4 6 } --> { 1 2 4 6}

## Bubble sort code in java

```

import java.util.*;
  import java.util.Scanner;
     public class Bubblesort{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the  number of elements");
        int n = sc.nextInt();
        
        int[] arr = new int[n];
        System.out.println("Enter the elements");
        for(int i = 0 ; i<n;i++){
            arr[i]=sc.nextInt();
        }
            for(int i = 0 ; i<n;i++){
                for(int j=0;j<n-i-1;j++){
                    if(arr[j]> arr[j+1]){
                        int temp = arr[j];
                        arr[j]= arr[j+1];
                        arr[j+1]= temp;
                    }
                }
            }
            System.out.println("sorted array is ");
            for(int i = 0;i<n;i++){
                System.out.println(arr[i]+" ");
            }
    }}     
       


 //Output :
  Enter the  number of elements: 4
  
  Enter the elements
  5
  2
  8
  6
  
 sorted array is
  2
  5
  6
  8

```
## Time & Space Complexity for Bubble sort:
**Time Complexity**:

Best Case :	    O(n) <br>
Average Case :	O(n2) <br>
Worst Case: 	O(n2) <br>

**Space Complexity**:<br>
Auxiliary Space: O(1)

## References :
(https://www.javatpoint.com/bubble-sort)<br>
(https://www.geeksforgeeks.org/bubble-sort)

