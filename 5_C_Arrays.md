# Topic 5: C Arrays
## 1. Array Basics
Array requires introducing new types and new operators.  
We can initialize an array with {}:
```c
int a[] = {1, 2 ,3};
```
We can't assign to an array:
```c
int a[] = {1, 2, 3, 4};
int b[4];
b = a;// Illegal!!!
```
C is designed to be a low-level language that provides minimal abstraction over machine instructions.  
When you declare an array in C, it is allocated a fixed block of contiguous memory addresses.   
We can't directly assign an array to an array since "b" is a pointer to the memory position of the first array elemrnt. This pointer cannot be redirected to point to another block of memory.  

Relationship between arrays and pointers:
- we can use pointer arithemetic to access elements in an array.

Example:
```c
int a[] = {1, 2, 3, 4};
int* a_ptr0 = a;
int* a_ptr1 = a+1;
int b = *a_ptr0 + *a_ptr1;
*a = 1;
*(a+1) = 2;
```

The subscript operator (a[i]) is syntactic sugar for *(a+i)
## 2. Iterating Over Arrays
```c
// Iterating using subscript operator a[i]
int a[] = {1, 2, 3, 4};
int sum = 0;
for (int i = 0; i < 4; i++){
    sum += a[i];
}
int avg = sum/4;
```
```c
int a[] = {1, 2, 3, 4};
int sum = 0;
int* curr = a;
int* end = a+4;
while(curr != end){
    sum += *curr;
    curr++;
}
int avg = sum/4;
```

Use int for general-purpose variables and when negative values are possible; use size_t for representing sizes, such as array lengths and memory allocation, where negative values don't make sense and large values might be needed.
## 3. Arrays as Function Parameters
Arrays are always passed by pointers to the first element of the array, so we must pass array size along with the pointers.  
```c
#include <stdio.h>

int avg(int* a, int size){
    int* curr = a;
    int* end = a+size;
    int sum = 0;
    while(curr != end){
        sum += *curr;
        curr++;
    }
    return sum/size;
}

int main(){
    int a[] = {1, 4, 8, 10, 1};
    int size = sizeof(a)/sizeof(a[0]);
    int b = avg(a,size);
    printf("%d\n",b);
    return 0;
}
```
## Strings
Strings are arrays of char.  
The null terminator character (\0) indicates the end of string  
Two common initialization:  
```c
char a[] = {'a', 'b', '\0'};
char a[] = "ab";
```
In the second one, the compiler will add '\0' automatically.
If in first one, there is no '\0', it's ok to reach one element like "a[0], a[1]", but when we try to use some standard libraries like '<string.h>', we may face issues since many functions there need the null terminator character.  
```c
//Example of strlen()
int strlen(char* a){
    int length = 0;
    while(a[length] != '\0'){
        length += 1;
    }
    return length;
}
```