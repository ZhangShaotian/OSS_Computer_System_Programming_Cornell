# Topic 2: C Recursion
Recursion is a method that calls the function itself as part of execution.
## 1. Single Recursion 
We want to write a function to calculate factorial of a number.  
We can implement it using for loops:
```c
int factorial(int n){
    int result = 1;
    for (int i = 1; i <= n; i++){
        result = result * i;
    }
    return result;
}
```
However, this kind of implementation doesn't resemble the the original mathematical formulation, we can directly implement it using recursion.  
```c
int factorial(int n){
    //Base Case
    if (n == 0) {
        return 1;
    }
    //Recursive Case
    if (n > 0){
        return n*factorial(n-1);
    }
}
```
- Base Case: This is where the recursion ends.  
- Recursiive Case: This is where the function calls itself, approaching the base case.  

What if n is negative?  
Then the function reaches the end without encountering a return value. Since this function is a non-void function, there might be several results:  
- Unpredictable Return Value: Return an arbitrary value, based on the value in the menory at that time.
- Compiler Warnings: Modern C compiler often issues warnings or errors.  
## 2. Multiple Recursion
Multiple recursion occurs when the function calls itself multiple times, one example is fibonacci number.
```c
int fib(int n){
    //base case 
    if (n == 0){
        return 0;
    }else if(n == 1){
        return 1;
    }
    //recursive case
    return fib(n-1)+fib(n-2);
}
