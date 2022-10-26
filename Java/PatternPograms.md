## Patterns in Programming:

Pattern program enhances the coding skill, logic, and looping concepts. It is mostly asked in interview to check the logic and thinking of the programmer

Star patterns are a series of * or any other character used to create some pattern or any geometrical shape such as - square, triangle(Pyramid), rhombus, heart etc. 
These patterns are often prescribed by many programming books and are best for practicing flow control statement


## How to print any pattern :
Every time you create logic for a pattern programme, you should first sketch the pattern in the blocks, like we have done in the picture below. 
The pattern is well shown in the illustration.
Every pattern programme contains two or more loops. The complexity of the pattern or logic determines how many loops there are. 
Both the first and second for loops are effective for the row and column, respectively. Java uses frequently  For-loop  in pattern programmes.

![Patternimage](https://static.javatpoint.com/core/images/how-to-print-pattern-in-java.png "PatternImage")

In the above pattern, the row is denoted by i and the column is denoted by j. We see that the first row prints only a star. 
The second-row prints two stars, and so on. The colored blocks print the spaces.

**sample code for above image**
```
for(int i=0; i<row; i++)   
{   
for(int j=0; j<=i; j++)   
{   
System.out.print("* ");   
}   
System.out.println();  

```

## Examples of some commonly asked Star pattern :

**Half pyramid**
 
```
public class Main
{
	public static void main(String[] args) {
	 for(int i=1;i<=5;i++)
    {
        for(int j=1;j<=i;j++)
        {
            System.out.print("*");
        }
        
        System.out.println();
    }
}}

**Output**
*
**
***
****
*****

```

**V Star pattern**

```
public class Main
{
	public static void main(String[] args) {
	for(int i=5;i>=1;i--){
    for(int j=5;j>i;j--){
        System.out.print(" ");
    }
    for(int k =1;k<(i*2);k++)
    {
        if(k>1 && k<(i*2)-1)
        {
            System.out.print(" ");
        }
        else{
            System.out.print("*");

        }
    }System.out.println();
}
}
}

**Output**:

*       *
 *     *
  *   *
   * *
    *

## Full Pyramid**

```
public class Main
{
	public static void main(String[] args) {
for(int i = 1; i<=4;i++){
    for(int j= 4;j>=i;j--){
        System.out.print("  ");
    }
    for(int k =1;k<=i;k++){
        System.out.print(" * ");
    }System.out.println();
}
}
}

**Output**
         * 
       *  * 
     *  *  * 
   *  *  *  * 

```


## Solid Half Daimond**

```
public class Main
{
	public static void main(String[] args) {
 for(int i=1; i<=4;i++){
        for(int j=1; j<=i;j++){
            System.out.print("*");
        }System.out.println();                     
    }
    for(int i=1; i<=3;i++){
        for(int j=3;j>=i;j--){
            System.out.print("*");
        }System.out.println();
    }
}}

    
**Output**
*
**
***
****
***
**
*
```

## Half Pyramid - 2:

public class Main
{
	public static void main(String[] args) {
	for(int i=1;i<=5;i++)
    {
        for(int j=5;j>i;j--)
        {
            System.out.print(" ");
        }
        for(int k=1; k<=i;k++)
        {
            System.out.print("*");
        }
        System.out.println();
    }
}}

**Output**
    *
   **
  ***
 ****
*****
```
## Daigonal Star  pattern:
```
public class Main
{
	public static void main(String[] args) {


for(int i = 1;i<=4;i++){
    for(int j=1;j<=i;j++){
        System.out.print(" ");
    }
    System.out.println("*");
}

}
}

**Output**
 *
  *
   *
    *
```

## Reference:
<br>
(https://www.javatpoint.com/how-to-print-pattern-in-java)