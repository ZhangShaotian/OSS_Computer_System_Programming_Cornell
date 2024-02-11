# Topic 6: C Dynamic Allocation
## 1. Using malloc to Allocate Memory
When we initialize variables, we'd better use malloc if:  
- Variable-Size Data Structure: Reading User Input
- Large Data Size: Preventing stack overflow(1 - 8 MB according to OS)  
- For local variables, when we return, the stack frame is deallocated, so we should use malloc here.  

Heap is a region of memory that is used for dynamic memory allocation, memory on the heap must be allocated and deallocated mannually.
## 2. Using 'free' to Deallocate Memory
Every call to malloc must have corresponding call to free. If you assign a variable to a new memory without free previous memory, then you will no longer have access to the initial memory. Although the OS will release the memory after programm ends, but it's a good idea to manage memory properly especially in large systems.