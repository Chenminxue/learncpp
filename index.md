# Welcome to C++

## Catalogue

- [Comments](#Comments)
- [Variables](#Variables)
- [Constants](#Constants)
- [Keywords](#Keywords)
- [Data_Types](#Data_Types)
- [Data_Input](#Data_Input)
- [Operators](#Operators)
- [Program_Control_Flow](#Program_Control_Flow)
- [Array](#Array)
- [Functions](#Functions)
- [Pointers](#Pointers)

## Comments

Single-line comments

```markdown
 // ...
```

Multi-line comments

```markdown
 /* ...
    ...
    ... */
```

## Variables

Give a name to a space in memory.

```markdown
 type variable_Name = value;

 int a = 10;
```

## Constants

Unchangeable data in the program.

```markdown
 #define Constant_Name value
 
 #define DAY 7
```

```markdown

 const Variable_Name = value;

 const int month = 12;
```
## Keywords

Reserved and not available for re-definition or overloading.
[C++ Keywords table](https://en.cppreference.com/w/cpp/keyword)

## Data_Types

While Creating variables and constants, you must first specify the corresponding data type. You can use keyword 
```markdown
 sizeof(data type) or sizeof(variable) 
``` 
to get the memory size of the data type or variable.

#### 1. Integer

Represent integers like 1, 10.
```markdown
 short(2 bytes)
 
 int(4 bytes)
 
 long(4bytes)
 
 long long(8 bytes)
```

```markdown
int a = 10;
```

#### 2. Floating point

Represent decimals like 1.23, -2.332.
```markdown
 float(4 bytes)

 double(8 bytes)
```

```markdown
 float pi = 3.14;
```

#### 3. Character

Represent characters like a, z. Notice: The variable stores the ASCII code of the character. Only one character can be placed in single quotes, otherwise an error will be reported.
```markdown
 char(1 byte)
```

```markdown
 char ch = 'a';
 cout << int(ch) << endl;
 
  97
```

#### 4. String

```markdown
 C style: char str[] = "abcde";
```

```markdown
 C++ style: string str = "abcde";
```

#### 5. Boolean

Represent True and False.

```markdown
 bool(1 byte) 
```

```markdown
 bool a = true;
```

## Data_Input

```markdown
 cin >> Variable;
```

```markdown
 int a = 0;
 cin >> a;
```

## Operators

```markdown
 + - * / % ++ -- += >= || ! && ...
```

```markdown
 pre-increment/decrement: a=2; b=++a; // Do b=a first and ++a, the result is a=3; b=3;
```

```markdown
 post-increment/decrement: a=2; b=a++; // Do a++ first and b=a, the result is a=3; b=2;
```

## Program_Control_Flow

#### 1. Selection statements

If condition:
```markdown
 if(score > 600){
  ...
 }
 else if(score > 500){
  ...
 }
 else{
  ...
 }
```

Conditional Operator ?:
```markdown
 c = a > b ? a : b; // a > b is true then return a, false return b.
```

Switch condition:
```markdown
 switch(c = a > b ? a : b){
   case a: 
     cout << a << endl;
     break;   
   case b: 
     cout << b << endl;
     break;
   default:
     cout << "Nothing!" << endl;
     break;
}
```

#### 2. Iteration statements

While loop:
```markdown
 while (expression){
   statement;
 } 
```

Do while loop:
Do statement first then check the conditon.
```markdown
 do{
   statement;
 }
 while (expression)
```

For loop:
```markdown
 for(expression){
   statement;
 }
```

#### 3. Jump statements

```markdown
 break; // Leave a loop

 continue; // Skip one loop
 
 goto; // Make an absolute jump to another point in the program
```

## Array

Arrays are used to store elements of the same type(Data type). Arrays are made up of continuous memory.

#### 1. One-dimensional array

![avatar](/pics/array.png)

Three ways to define an array.
```markdown
 int arr[3];
 arr[0] = 10;
 arr[1] = 20;
 arr[2] = 30;
```

```markdown
 int arr[3] = {10, 20, 30};
```

```markdown
 int arr[] = {10, 20, 30, 40};
```

Get the length of the array.
```markdown
 int len = sizeof(arr)/ sizeof(arr[0]); // len is the length of the array.
```

Get the address of the array.
```markdown
 cout << arr << endl;
```

Get the address of the first element of the array.
```markdown
 cout << &arr[0] << endl; // The address is the same as arr.
```

#### 2. Two-dimensional array

![avatar](/pics/two_dimensional_array.png)

Four ways to define a two-dimensional array.
```markdown
 int arr[2][3];
 arr[0][0] = 1;
 arr[0][1] = 2;
 arr[0][2] = 3;
 arr[1][0] = 4;
 arr[1][1] = 5;
 arr[1][2] = 6;
```

```markdown
 int arr[2][3] = {
    {1,2,3},
    {4,5,6}
 };
```

```markdown
 int arr[2][3] = {1,2,3,4,5,6};
```

```markdown
 int arr[][3] = {1,2,3,4,5,6}; // Give the number of columns.
```

## Functions

Encapsulate a piece of frequently used code to reduce repetitive use of code.

#### 1. How to write and call a function:
```markdown
 int add(int num_1, int num_2){ // num_1 and num_2 are parameters
    int sum = num_1 + num_2;
    return sum;
 }
 
 int main(){
    int a = 10;
    int b = 20;
    int sum = add(a, b); // a and b are arguments
    
    return 0;
 }
```

#### 2. Pass by value:
The above example is called pass by value. When a function is called, a value is passed to the parameters through the arguments. If the parameters are changed, the arguments will not be affected. **The principle of passing by value：**

![avatar](/pics/pass_by_value.png)

#### 3. Four types of functions:
```markdown
 void test(){
 
 }
```

```markdown
 void test(){
    cout << "This is a test!" << endl;
 }
```

```markdown
 int test(){
    cout << "This is a test!" << endl;
    return 100;
 }
```

```markdown
 int test(int a){
    return a;
 }
```
#### 4. Function Declarations:
A function declaration tells the compiler about a function name and how to call the function. The actual body of the function can be defined separately. For example:

```markdown
 int add(int num_1, int num_2);
 
 int main(){
 
 }
 
 int add(int num_1, int num_2){ // num_1 and num_2 are parameters
   int sum = num_1 + num_2;
   return sum;
 }
```
#### 5. Writing functions in different files:


## Pointers
Memory can be accessed through pointers.

#### 1. Define and use a pointer

```markdown
 datatype * variiable;
```

```markdown
 int a = 10;
 int * p = &a;
 cout << a << endl;  // 10
 cout << &a << endl; // 0x6000
 cout << p << endl;  // 0x6000
 cout << *p << endl; // 10
```
