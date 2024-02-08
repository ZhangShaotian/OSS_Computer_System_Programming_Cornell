# Topic 3: C Types
C is a statically typed language, meaning that the type of variables must be known at the compile time.  

Three critical questions:  
- What is the meaning of the variable's value? 
- How should the variables's value be stored in the computer?
- What operations are allowed on the variable?
## 1. Basic Data Types
### 1.1. int Type
- Meaning: Integer whole number in a limited range.
- Stored: 32-bit two's complement.(one bit for sign, 32 bits for values)
- Operations: Basic integer arithmetic  
4-bit Unsigned Integer (0~15)  
4-bit Signed Integer (-8~7)
### 1.2. char Type
- Meaning: "word"
- Stored: 8-bit binary
- Operations: Basic integer arithmetic(It's 8-bit integer fundamentally) 
### 1.3. const Types
- Meaning: Indicating variables won't change
- Stored: whatever is required for "base" type
- Operations: read-only operations
### 1.4. void Types
- Meaning: no values 
- Stored: no storage needed
- Operations: None
## 2. Programmer-Defined Types
### 2.1. Typedefs
A typedef does not define a new type, it provides a new name for an already defined type.  
### 2.2. struct Types
A struct enables bundling multiple variables into a single entity.  
```c
struct Point{
    int a;
    int b;
};

int main(){
    struct Point p1;
    int c = p1.a;
    int d = p1.b;
}
```

Also, by using typedef together, we can further simplify it:
```c
typedef struct{
    int a;
    int b;
}Point;

int main(){
    Point p1;
    int c = p1.a;
    int d = p1.b;
}
```
## 3. Working With Types
### 3.1. Type Checking
Compiler will check to ensure types are consistent, otherwise it will cause compile-time error.
### 3.2. Type Inference
Compiler uses type inference to determine the type of expression based on the values.
### 3.3. Type Casting
Programmers can use type casting to convert a value of one type to another type.
### 3.4. Type Conversion
Compiler can also use implicit type conversion.  
C supports weak static typing since it allows implicit type conversion.