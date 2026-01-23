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

   
