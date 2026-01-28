# sem-2-practical
## Write a C++ program that:Declares one global variableDeclares one local variable inside main()Dynamically allocates one integer using newPrint the addresses of all three and identify which memory region each belongs to.
```
#include <iostream>
using namespace std;

// 1. Global variable (lives for the whole program)
int globalVar = 5;

int main() {

    // 2. Local variable (lives only inside main)
    int localVar = 10;

    // 3. Dynamically allocated variable (created using new)
    int* heapVar = new int;
    *heapVar = 15;

    // Print addresses
    cout << "Global variable address: " << &globalVar << endl;
    cout << "Local variable address:  " << &localVar << endl;
    cout << "Heap variable address:   " << heapVar << endl;

    cout << endl;

    // Explain where they are stored
    cout << "Memory Regions:" << endl;
    cout << "Global variable -> Global / Static Memory" << endl;
    cout << "Local variable  -> Stack Memory" << endl;
    cout << "Heap variable   -> Heap Memory" << endl;

    // Free the memory created with new
    delete heapVar;

    return 0;
}
```
## Write a function square(int) and call it:NormallyUsing a function pointer
```
#include <iostream>
using namespace std;

// Function that returns the square of a number
int square(int x) {
    return x * x;
}

int main() {

    int num = 5;

    // 1. Normal function call
    int result1 = square(num);
    cout << "Normal function call result: " << result1 << endl;

    // 2. Function pointer call
    int (*funcPtr)(int);   // declare function pointer
    funcPtr = square;      // point to the square function

    int result2 = funcPtr(num);  // call function using pointer
    cout << "Function pointer call result: " << result2 << endl;

    return 0;
}
```
## Write a program to print:Value of a variableAddress of the variableValue stored in the pointe
```
#include <iostream>
using namespace std;

int main() {

    int x = 10;        // normal variable
    int* ptr = &x;    // pointer storing address of x

    // Printing values
    cout << "Value of the variable x: " << x << endl;
    cout << "Address of the variable x: " << &x << endl;
    cout << "Value stored in the pointer ptr: " << ptr << endl;

    return 0;
}
```
## Write a program where a pointer stores the address of another variable and copies its value into a third variable using dereferencing.
```
#include <iostream>
using namespace std;

int main() {

    int a = 10;        // original variable
    int* ptr = &a;    // pointer stores address of a
    int b;            // third variable

    // Copy value of 'a' into 'b' using dereferencing
    b = *ptr;

    // Print values
    cout << "Value of a: " << a << endl;
    cout << "Value stored in pointer (address of a): " << ptr << endl;
    cout << "Value of b (copied using pointer): " << b << endl;

    return 0;
}
```
## What will be the output
```
int x = 5;
int *p = &x 

*p = 10;cout << x;
```
```
10
```
## 
```
int a = 1
b = 2;
int *p = &a;
p = &b;
*p = 5;
cout << a << " " << b;
```
```
1 5
```
##
```
int x = 10;
int *p = &x;
int **pp = &p;
**pp = 20;
cout << x;
```
```
20
```
```
int a[5] = {2,4,6,8,10};
int *p=a
cout<<*p++<<"";
cout<<*p;
```
```
2
4
```
write a program to swap two number using pointers
```
#include <iostream>
using namespace std;

void swap(int *x, int *y)
{
    int temp;
    temp = *x;
    *x = *y;
    *y = temp;
}

int main()
{
    int a, b;

    cout << "Enter two numbers: ";
    cin >> a >> b;

    swap(&a, &b);

    cout << "After swapping:" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;

    return 0;
}
```
## Implement a simple dynamic integer variable that:Is created using newModified through a pointerProperly deleted
```
#include <iostream>
using namespace std;

int main()
{
    // Step 1: Create a dynamic integer using new
    int *num = new int;

    // Step 2: Assign a value through the pointer
    *num = 10;

    // Step 3: Modify the value through the pointer
    *num = *num + 5;

    // Display the value
    cout << "Value of dynamic integer: " << *num << endl;

    // Step 4: Properly delete the dynamic memory
    delete num;

    // Set pointer to NULL (good practice)
    num = NULL;

    return 0;
}

```
## output question 
```
int a[] = {1,2,3,4,5};
int *p = a;
cout << *p++ << " ";
cout << (*p)++ << " ";
cout << ++*p << " ";
cout << *p << "\n";
for(int i=0;i<5;i++) cout << a[i]<< " ";
```
```
1 2 4 4
1 4 3 4 5
```
```
int x=10;
int *p=&x;
cout << (*p)++ << " " << x << "\n";
cout << ++(*p) << " " << x << "\n";
cout << *p++ << " " << x << "\n";
```
```
10 11
12 12
12 12

```
```
int a[] = {10,20,30,40,50};
int *p = a + 1;
cout << *(p+2) << " " << *(p-1) << "\n";
```
```
40 10
```
Write a C++ program to read and display elements of an array.
```
#include <iostream>
#include <vector> // Using vector is often more modern/flexible, but a fixed-size array works too.

int main() {
    // 1. Declare the array size and the array
    const int SIZE = 5;
    int numbers[SIZE];

    std::cout << "Enter " << SIZE << " integers:" << std::endl;

    // 2. Read input into the array using a loop
    for (int i = 0; i < SIZE; ++i) {
        std::cout << "Element " << i << ": ";
        std::cin >> numbers[i];
    }

    std::cout << "\nYou entered the following elements:" << std::endl;

    // 3. Display the elements of the array using a range-based for loop
    for (int num : numbers) {
        std::cout << num << " ";
    }

    std::cout << std::endl;

    return 0;
}

```
Write a C++ program to find the sum of all elements in an array.
Write a C++ program to copy one array into another.

Write a C++ program to print array elements at even index positions.

Write a C++ program to read and display a 2D array (matrix).

Write a C++ program to print all elements of a matrix in row-wise order.
Write a C++ program to print all elements of a matrix in column-wise order.
