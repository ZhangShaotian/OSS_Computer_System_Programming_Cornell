# 1. C Pointers
## 1.1. Pointer Basics
Pointers are a way of referring to the location of a variable.  
```c
int a;
int* a_ptr;     //pointer to a variable of type int
a_ptr = &a;     //assigen address of a to a_ptr
int b = *a_ptr; //initialize b with what a_ptr points to(value of a)
```
## 1.2. Call by Value vs. Call by Pointer
Call by Value:  
- Call by value copies values into parameters
- Changes to parameters are not seen by caller.(The callee modifies the copy of the parameters)

Call by Pointer:  
- Callee can read and modify parameters by dereferencing pointers
- Changes to parameters are seen by caller  
```c
//Call by Value
void addTen(int x) {  // Callee function
    x = x + 10;
}

int main() {
    int a = 5;        // Caller function
    addTen(a);
    printf("%d\n", a); // Outputs: 5
    return 0;
}
```
```c
//Call by Pointer
void addTen(int *x) {  // Callee function
    *x = *x + 10;
}

int main() {
    int a = 5;          // Caller function
    addTen(&a);
    printf("%d\n", a); // Outputs: 15
    return 0;
}
```
## 1.3. Pointers to Other Types
- struct
- null(doesn't point to any valid memory address)
- pointer