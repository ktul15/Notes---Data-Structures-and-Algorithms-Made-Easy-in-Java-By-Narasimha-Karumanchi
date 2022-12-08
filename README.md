This is my summary of the Effective Java 2nd Edition by Joshua Bloch. I use it while learning and as quick reference. It is not intended to be an standalone substitution of the book so if you really want to learn the concepts here presented, buy and read the book and use this repository as a reference and guide.

If you are the publisher and think this repository should not be public, just write me an email at ketulm8 [at] gmail [dot] com and I will make it private.

Contributions: Issues, comments and pull requests are super welcome :smiley:

# 1. Ch. 1 Introduction

- ## 1.1 Variables

  They are the placeholders for representing data. They refer to our data stored in memory.

- ## 1.2 Data Types

  A data type in a programming language is a set of data with predefined values. Examples: integer, floating points, unit number, characters, strings, etc...

  Computers only understands zeros and ones. And it's very difficult to write any large programs using only zeros and ones. To help with that, programming languages and compilers provide us with data types.

  A data type reduces the coding effort. There are 2 types of data types: System defined(primitives) and user defined.

  ### System defined data types:

  - They are defined by system. Also called primitives.
  - Ex: int, float, bool, char, double, etc..
  - Number of bits allocated depends on the language, compiler and OS.
  - Total number of available values for a data type depends on the size of the data type.
  - If int takes 2 bytes, total available values - (-32,768) to (+32767), and if it takes 4 bytes , then total available values are - (−2,147,483,648) to (−2,147,483,647).

  ### User defined data types:

  - Most programming languages allow the users to define their own data types.
  - Ex: Structures in c/c++, Classes in Java.
  - Provides flexibility and comfort in dealing with computer memory.

- ## 1.3 Data Structure

  - It's a particular way of storing and organizing data so that it can be used efficiently according to the needs of the problem.
  - Ex: arrays, linked lists, stacks, queues, graphs, tress, etc...
  - 2 types: Linear and Non-Linear;

  ### Linear data structures:

  - Elements are accessed in a sequential order.
  - Elements are not necessarily stored in sequential order.
  - Ex: stacks, queues, linked lists, etc...

  ### Non-linear data structures:

  - Elements are accessed in a non-linear order.
  - Ex: Trees, graphs.

- ## 1.4 Abstract Data Types(ADT)

  - To simplify the process of problem solving, we combine data structures with their operations to create ADTs. ADTs have 2 parts:
    - Declaration of data
    - Declaration of operations
  - Examples: linked lists, stacks, queues, priority queues, binary trees, disjoint sets(union and find), hash tables, graphs, etc.
  - For example, stack uses a LIFO (Last In First Out) mechanism to store data in data structures. The last element inserted will be the first to be deleted. Common operations are creating the stack, inserting, deleting, finding the current top element, finding the total elements, etc...
  - Different kinds of ADTs are suited to different kinds of applications, and some are highly specialized to specific tasks.

- ## 1.5 What is an algorithm?

  - An algorithm is a step by step unambiguous instructions to solve a problem.
  - 2 main criteria for judging the merits of algorithms:
    - correctness (does the algorithm give solution to the problem in a finite number of steps?)
    - efficiency (how much resources - memory and time - does it take to execute all the instructions.)

- ## 1.6 Why the analysis of algorithms?

  - To go from city A to city B, there can be many ways. We choose the way most suitable to us.
  - Similarly, in computer science, there can be many algorithms to solve a particular problem. For example, sorting problem has many algorithms like insertion sort, selection sort, quick sort and many more.
  - Algorithm analysis helps us to determine the most efficient algorithm in terms of time and space consumed.

- ## 1.7 Goal of the Analysis of Algorithms

  - To understand the algorithms better.
  - Main role is to predict the performance of different algos to guide design decisions.
  - To compare algos mainly in terms of running time.
  - We estimate their complexity in the asymptotic sense, i.e., to estimate the complexity function for arbitrarily large input.
  - Analysis of algos is the determination of the amount of time and space resources required to execute it.
  - Usually, the efficiency or running time of an algo is stated as a function relating the input length to the number of steps, known as the time complexity, or volume of memory, known as space complexity.

- ## 1.8 What is running time analysis?

  - Process of determining how processing time increases as the size of the input increases.
  - Types of inputs - size of an array, polynomial degree, number of elements in a matrix, number of bits, vertices and edges in a graph.

- ## 1.9 How to compare algos?

  - Execution time is not a good measure as execution times are specific to a particular computer.
  - Number of statements executed is also not a good measure since the number of statements varies according to the programming language and the style of individual programmer.
  - Ideal way is to express running time of an algo as the function of input size and compare these different functions corresponding to running times. This kind of comparison is independent of machine time, programming style, etc...

- ## 1.10 Rate of Growth

  - The rate at which running time increases as the function of input.

- ## 1.11 Commonly used rate of growths

  - Constant(1), Logarithmic(logn), Linear(n), Linear Logarithmic(nlogn), Quadratic(n^2), Cubic(n^3), Exponential(2^n), Factorial(n!).
  - Decreasing rates of growths - 2^2^n, n!, 4^n, 2^n, n^2, nlogn, log(n!), n, 2^logn, log^2\*n, logn^1/2, log log n, 1.

- ## 1.12 Types of Analysis

  - Best case: Defines the input for which the algo takes the lowest time. Input is the one for which the algo runs the slowest.
  - Worst case: Defines the input for which the algo takes the most time. Input is the one for which the algo runs the fastest.
  - Average case: Provides the prediction about running time. Run the algo many times, using different inputs, compute the total running time and divide by the number of trials. Assumes that the input is random.
  - Let f(n) be the function which represent the given algo,
    f(n) = n^2 + 500, for worst case,
    f(n) = n + 100n + 500, for best case

  - ## 1.13 Asymptotic Notation

    - Having the expressions for the best, worst and average cases, we need to find the upper and lower bounds for all three cases. We need some kind of syntax for that. Let us assume that the given algo is represented in the form of function f(n),

  - ## 1.14 Big-O Notation

    - Gives the tight upper bounds of the given function.
    - Generally, it's represented as f(n) = O(g(n)). That means, at larger values of n, the upper bound of f(n) is g(n). For example, if f(n) = n^4 + 100n^2 + 50\*n + 10 is the given algo, then n^4 is g(n). g(n) gives the max rate of growth for f(n) at larger values of n.
    - Our objective is to give smallest rate of growth g(n) which is greater than or equal to given algo's rate of growth f(n).
    - Rate of growth at lowe values of n is not important.
    - ### Big-O Visualization

      - O(g(n)) is the set of functions with smaller or same order of growth as g(n).
      - O(1): 100, 1000, 200, 1, etc..
      - O(n): 3n + 100, 100n, 2n - 1, 3, etc...
      - O(nlogn): 5nlogn, 3n - 100, 2n - 1, 100, 100n, etc...
      - O(n^2): n^2, 5n - 10, 100, n^2 - 2n + 1, 5, etc...

    - ### Big-O Examples
      - Ex-1: Find upper bound for f(n) = 3n + 8
      - Sol: 3n + 8 <= 4n, for all n >= 8
        so, 3n + 8 = O(n) with c = 4 and n0 = 8
      - Ex-2: Find upper bound for f(n) = n^2 + 1
      - Sol:

  - ## 1.15 Omega Notation (Lower Bounding Function)

    - This notation gives the tighter lower bound of the given algo.

  - ## 1.16 Theta Notation

    - It deided whether the upper bound and the lower bound is same. The average running time of an algo is always between upper bound and lower bound. If the upper and lower bound is same then theta notation will also have same rate of growth.

  - ## 1.17 Why is it called asymptotic analysis?

    - In the discussion above, we are trying to find a function g(n) for a given function f(n) which approximates f(n) at higher values of n. That means g(n) is a curve which approximates f(n) at higher values. In maths, this curve is called asymptotic curve. That's why we call it asymptotic analysis.

  - ## 1.18 Guidelines for asymptotic analysis

    - There are some general rules to determine the running time of an algo.
    - ### Loops:

      - The running time of a loop is, at most, the running time of the statements inside the loop (including tests) multiplied by the number of iterations.
      - // executes ݊n times
        > for (i=1; i<=n; i++)  
        > m = m + 2; //constant time, c
      - Total time - a constant c \* n = cn = O(n)

    - ### Nested Loops:
      - Analyze from the inside out. Total running time is the product of the sizes of all the loops.
        > //outer loop executed n times  
        >  for (i=1; i<=n; i++) {  
        >  // inner loop executed n times  
        >  for (j=1; j<=n; j++)  
        >  k = k+1; //constant time  
        >  }
      - Total time = c _ n _ n = cn^2 = O(n^2)
    - ### Consecutive statements
      - Add the time complexities of ach statements.
        > x+ x + 1 // constant time
        > // executed n times  
        >  for (i=1; i<=n; i++)  
        >  m = m + 2; //constant time  
        > //outer loop executed n times  
        >  for (i=1; i<=n; i++) {  
        >  //inner loop executed n times  
        >  for (j=1; j<=n; j++)  
        >  k = k+1; //constant time  
        >  }
      - Total time = c0 + cn + cn^2 = O(n^2)
    - ### If-Else statements
      - Worst case running time: the test, plus either the then part or the else part(Whichever is larger).
        > //test: constant  
        >  if(length( ) == 0 ) {  
        >  return false; //then part: constant  
        >  }  
        >  else { // else part: (constant + constant) \* n  
        >  for (int n = 0; n < length( ); n++) {  
        >  // another if : constant + constant (no else part)  
        >  if(!list[n].equals(otherList.list[n]))  
        >  //constant  
        >  return false;  
        >  }  
        >  }
      - Total time = c0 + (c1 + c2) \* n = O(n)
    - ### Logarithmic complexity
      - An algo is O(logn) if it takes a constant time to cut the problem size by a fraction (usually 1/2).
        > for (i=1; i<=n;)  
        >  i = i\*2;
      - The value of i is doubling every time. If loops runs for k steps then at kth step, 2^k = n.
      - Taking logs on both sides,
        log(2^k) = log n
        klog 2 = log n
        so, k = log n ///asumming base 2
      - Total time = O(logn)
