## Algorithm Analysis
Analysis of efficiency of an algorithm can be performed at two different stages, before implementation and after implementation, as

A priori analysis − This is defined as theoretical analysis of an algorithm. Efficiency of algorithm is measured by assuming that all other factors e.g. speed of processor, are constant and have no effect on implementation.

A posterior analysis − This is defined as empirical analysis of an algorithm. The chosen algorithm is implemented using programming language. Next the chosen algorithm is executed on target computer machine. In this analysis, actual statistics like running time and space needed are collected.

Algorithm analysis is dealt with the execution or running time of various operations involved. Running time of an operation can be defined as number of computer instructions executed per operation.

## Algorithm Complexity
Suppose X is treated as an algorithm and N is treated as the size of input data, the time and space implemented by the Algorithm X are the two main factors which determine the efficiency of X.

Time Factor − The time is calculated or measured by counting the number of key operations such as comparisons in sorting algorithm.

Space Factor − The space is calculated or measured by counting the maximum memory space required by the algorithm.

The complexity of an algorithm f(N) provides the running time and / or storage space needed by the algorithm with respect of N as the size of input data.

![alt text](https://i.ytimg.com/vi/47GRtdHOKMg/maxresdefault.jpg)

## Space Complexity
Space complexity of an algorithm represents the amount of memory space needed the algorithm in its life cycle.

Space needed by an algorithm is equal to the sum of the following two components

A fixed part that is a space required to store certain data and variables (i.e. simple variables and constants, program size etc.), that are not dependent of the size of the problem.

A variable part is a space required by variables, whose size is totally dependent on the size of the problem. For example, recursion stack space, dynamic memory allocation etc.

Space complexity S(p) of any algorithm p is S(p) = A + Sp(I) Where A is treated as the fixed part and S(I) is treated as the variable part of the algorithm which depends on instance characteristic I. Following is a simple example that tries to explain the concept

#### Algorithm
SUM(P, Q)
Step 1 - START
Step 2 - R ← P + Q + 10
Step 3 - Stop

Here we have three variables P, Q and R and one constant. Hence S(p) = 1+3. Now space is dependent on data types of given constant types and variables and it will be multiplied accordingly.

![alt text](https://storage.googleapis.com/algodailyrandomassets/curriculum/fundamentals/space1.png)

## Time Complexity
Time Complexity of an algorithm is the representation of the amount of time required by the algorithm to execute to completion. Time requirements can be denoted or defined as a numerical function t(N), where t(N) can be measured as the number of steps, provided each step takes constant time.

For example, in case of addition of two n-bit integers, N steps are taken. Consequently, the total computational time is t(N) = c*n, where c is the time consumed for addition of two bits. Here, we observe that t(N) grows linearly as input size increases.

![time complexity](https://www.crio.do/blog/content/images/2022/02/BIG-O-COMPLEXITY.png)

### Different problems on time and space complexity:

#### 1. What is the time, and space complexity of the following code: 
 

int a = 0, b = 0;
for (i = 0; i < N; i++) {
    a = a + rand();
}
for (j = 0; j < M; j++) {
    b = b + rand();
}

Options: 
O(N * M) time, O(1) space
O(N + M) time, O(N + M) space
O(N + M) time, O(1) space
O(N * M) time, O(N + M) space

Output: 
 O(N + M) time, O(1) space
Explanation: The first loop is O(N) and the second loop is O(M). Since N and M are independent variables, so we can’t say which one is the leading term. Therefore Time complexity of the given problem will be O(N+M).
Since variables size does not depend on the size of the input, therefore  Space Complexity will be constant or O(1)

#### 2. What is the time complexity of the following code: 
int a = 0;
for (i = 0; i < N; i++) {
    for (j = N; j > i; j--) {
        a = a + i + j;
    }
}

Options: 
O(N)
O(N*log(N))
O(N * Sqrt(N))
O(N*N)

Output: 
O(N*N)

Explanation: 
The above code runs total no of times 
= N + (N – 1) + (N – 2) + … 1 + 0 
= N * (N + 1) / 2 
= 1/2 * N^2 + 1/2 * N 
O(N^2) times.

#### 3. What is the time complexity of the following code: 
int i, j, k = 0;
for (i = n / 2; i <= n; i++) {
    for (j = 2; j <= n; j = j * 2) {
        k = k + n / 2;
    }
}

Options: 
O(n)
O(N log N)
O(n^2)
O(n^2Logn)

Output:
O(nLogn)

Explanation: If you notice, j keeps doubling till it is less than or equal to n. Several times, we can double a number till it is less than n would be log(n). 
Let’s take the examples here. 
for n = 16, j = 2, 4, 8, 16 
for n = 32, j = 2, 4, 8, 16, 32 
So, j would run for O(log n) steps. 
i runs for n/2 steps. 
So, total steps = O(n/ 2 * log (n)) = O(n*logn)

#### 4. What does it mean when we say that an algorithm X is asymptotically more efficient than Y? 

Options:
X will always be a better choice for small inputs
X will always be a better choice for large inputs
Y will always be a better choice for small inputs
X will always be a better choice for all inputs

Output: 
 X will always be a better choice for large inputs
 
Explanation: In asymptotic analysis, we consider the growth of the algorithm in terms of input size. An algorithm X is said to be asymptotically better than Y if X takes smaller time than y for all input sizes n larger than a value n0 where n0 > 0.
 

#### 5. What is the time complexity of the following code:
int a = 0, i = N;
while (i > 0) 
{
    a += i;
    i /= 2;
}

Options: 
O(N)
O(Sqrt(N))
O(N / 2)
O(log N)

Output: 
O(log N)

Explanation: We have to find the smallest x such that ‘(N / 2^x )< 1 OR  2^x > N’ 
x = log(N)

#### 6. Which of the following best describes the useful criterion for comparing the efficiency of algorithms?
Time
Memory
Both of the above
None of the above

Outout:
Both of the above

Explanation: Comparing the efficiency of an algorithm depends on the time and memory taken by  an algorithm. The algorithm which runs in lesser time and takes less memory even for a large input size is considered a more efficient algorithm.

#### 7. How is time complexity measured?
By counting the number of algorithms in an algorithm.
By counting the number of primitive operations performed by the algorithm on a given input size.
By counting the size of data input to the algorithm.
None of the above

Output:
By counting the number of primitive operations performed by the algorithm on a given input size.

#### 8. What will be the time complexity of the following code?
for(var i=0;i<n;i++)
    i*=k
    
O(n)
O(k)
O(logkn)
O(lognk)

Output:
O(logkn)

Explanation: Because loops for the kn-1 times, so after taking log it becomes logkn.

#### 9. What will be the time complexity of the following code
var value = 0;
for(var i=0;i<n;i++)
    for(var j=0;j<i;j++)
    value += 1;
    
n
(n+1)
n(n-1)
n(n+1)

Output:
n(n-1)

Explanation: First for loop will run for (n) times and another for loop will be run for (n-1) times so overall time will be n(n-1).

#### 10.  Algorithm A and B have a worst-case running time of O(n) and O(logn), respectively. Therefore, algorithm B always runs faster than algorithm A.

True
False

Output:
False

Explanation: The Big-O notation provides an asymptotic comparison in the running time of algorithms. For n < n0​​, algorithm A might run faster than algorithm B, for instance.
