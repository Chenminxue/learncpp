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
- [Struct](#Struct)

## Comments

Single-line comments

```
// ...
```

Multi-line comments

```
/* ...
   ...
   ... */
```

## Variables

Give a name to a space in memory.

```
type variable_Name = value;

int a = 10;
```

## Constants

Unchangeable data in the program.

```
#define Constant_Name value
 
#define DAY 7
```

```
const Variable_Name = value;

const int month = 12;
```
## Keywords

Reserved and not available for re-definition or overloading.
[C++ Keywords table](https://en.cppreference.com/w/cpp/keyword)

## Data_Types

While Creating variables and constants, you must first specify the corresponding data type. You can use keyword 
```
sizeof(data type) or sizeof(variable) 
``` 
to get the memory size of the data type or variable.

#### 1. Integer

Represent integers like 1, 10.
```
short(2 bytes)

int(4 bytes)

long(4bytes)

long long(8 bytes)
```

```
int a = 10;
```

#### 2. Floating point

Represent decimals like 1.23, -2.332.
```
float(4 bytes)

double(8 bytes)
```

```
float pi = 3.14;
```

#### 3. Character

Represent characters like a, z. Notice: The variable stores the ASCII code of the character. Only one character can be placed in single quotes, otherwise an error will be reported.
```
char(1 byte)
```

```
char ch = 'a';
cout << int(ch) << endl;  // 97
```

#### 4. String

```
C style: char str[] = "abcde";
```

```
C++ style: string str = "abcde";
```

#### 5. Boolean

Represent True and False.

```
bool(1 byte) 
```

```
bool a = true;
```

## Data_Input

```
cin >> Variable;
```

```
int a = 0;
cin >> a;
```

## Operators

```
+ - * / % ++ -- += >= || ! && ...
```

```
pre-increment/decrement: a=2; b=++a; // Do b=a first and ++a, the result is a=3; b=3;
```

```
post-increment/decrement: a=2; b=a++; // Do a++ first and b=a, the result is a=3; b=2;
```

## Program_Control_Flow

#### 1. Selection statements

If condition:
```
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
```
c = a > b ? a : b; // a > b is true then return a, false return b.
```

Switch condition:
```
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
```
while (expression){
  statement;
 } 
```

Do while loop:
Do statement first then check the conditon.
```
do{
  statement;
}
while (expression)
```

For loop:
```
for(expression){
  statement;
}
```

#### 3. Jump statements

```
break; // Leave a loop

continue; // Skip one loop

goto; // Make an absolute jump to another point in the program
```

## Array

Arrays are used to store elements of the same type(Data type). Arrays are made up of continuous memory.

#### 1. One-dimensional array

![avatar](/pics/array.png)

Three ways to define an array.
```
int arr[3];
arr[0] = 10;
arr[1] = 20;
arr[2] = 30;
```

```
int arr[3] = {10, 20, 30};
```

```
int arr[] = {10, 20, 30, 40};
```

Get the length of the array.
```
int len = sizeof(arr)/ sizeof(arr[0]); // len is the length of the array.
```

Get the address of the array.
```
cout << arr << endl;
```

Get the address of the first element of the array.
```
cout << &arr[0] << endl; // The address is the same as arr.
```

#### 2. Two-dimensional array

![avatar](/pics/two_dimensional_array.png)

Four ways to define a two-dimensional array.
```
int arr[2][3];
arr[0][0] = 1;
arr[0][1] = 2;
arr[0][2] = 3;
arr[1][0] = 4;
arr[1][1] = 5;
arr[1][2] = 6;
```

```
int arr[2][3] = {
   {1,2,3},
   {4,5,6}
};
```

```
int arr[2][3] = {1,2,3,4,5,6};
```

```
int arr[][3] = {1,2,3,4,5,6}; // Give the number of columns.
```

## Functions

Encapsulate a piece of frequently used code to reduce repetitive use of code.

#### 1. How to write and call a function:
```
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
```
void test(){

}
```

```
void test(){
   cout << "This is a test!" << endl;
}
```

```
int test(){
   cout << "This is a test!" << endl;
   return 100;
}
```

```
int test(int a){
   return a;
}
```
#### 4. Function Declarations:
A function declaration tells the compiler about a function name and how to call the function. The actual body of the function can be defined separately. For example:

```
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

```
datatype * variable;
```

\& is used for getting the address of one variable and \* is used for dereferencing the address.

```
int a = 10;
int * p = &a;
cout << a << endl;  // 10
cout << &a << endl; // 0x6000
cout << p << endl;  // 0x6000
cout << *p << endl; // 10
```

![avatar](/pics/pointers.png)

#### 2. Size of the pointer

32-bits machine: 4 bytes
64-bits machine: 8 bytes

#### 3. NULL pointers

The pointer points to a space numbered 0 in memory. Used to initialize pointer variables(If you create a pointer and do not know where to point). **Notice! The memory pointed to by the null pointer cannot be accessed!**

```
int *p = NULL;

cout << *p << endl;  // Error!
*p = 100;            // Error!
```

#### 4. Wild Pointers

Try to avoid wild pointers in the program.
```
int *p = (int*) 0x6000;
cout << *p << endl;  // Syntax is correct but unable to run! Because you do not have rights to access 0x6000, maybe something else important there.
```

#### 5. Pointers with const

```
int a = 10;
int b = 10;

const int *p_1 = &a;      // Value can not be changed but the address can be changed.
p_1 = &b;                 // This is correct!
*p_1 = 99;                // This is wrong!

int * const p_2 = &a;      // Value can be changed but the address can not be changed.
p_2 = &b;                 // This is wrong!
*p_2 = 99;                // This is correct!

const int * const p_3 = &a;      // Both address and value can not be changed.
p_3 = &b;                 // This is wrong!
*p_3 = 99;                // This is wrong!
```

#### 6. Pointers with array

How to use pointers to access the elements of an array?
```
int arr[] = {1,2,3,4,5,6};

int *p = arr;                                   // arr is the address already, no need to use & to get the address anymore.

cout << "First element." << arr[0] << endl;     // By using arr.
cout << "First element." << *p << endl;         // By using pointer.
p++;                                            // Move pointer to the next element, because the pointer points to datatype int, so it will shift 4 bytes.
cout << "Second element." << *p << endl;        // By using pointer.
```

![avatar](/pics/pointer_with_array.png)

#### 7. Pointers with functions(related to Chapter Functions, pass by value)

Use pointer as the parameters of the function instead of using pass by value, this is called ***pass by address***. The advantage of pass by address is that the value of arguments can be changed.

```
void swap(int *p_1, int *p_2){
   int temp = *p_1;
   *p_1 = *p_2;
   *p_2 = temp;
}

int main(){

   int a = 10;
   int b = 20;
   
   swap(&a, &b);  // a and b are swapped. 

   return 0;
}
```

## Struct

Struct is a user defined data type.

#### 1. Define and use a struct(3 ways to use a struct)

```
struct Student {
   string name;
   int age;
   int score;
};

int main(){
   Student s_1;
   s_1.name = "Matt";
   s_1.age = 20;
   s_1.score = 90;
   
   return 0;
}
```

```
struct Student {
   string name;
   int age;
   int score;
};

int main(){
   Student s_2 = {"Matt", 20. 90};
   
   return 0;
}
```

```
struct Student {
   string name;
   int age;
   int score;
}s_3;

int main(){
   s_3.name = "Matt";
   s_3.age = 20;
   s_3.score = 90;
   
   return 0;
}
```

#### 2. Struct array

```
struct Student {
   string name;
   int age;
   int score;
};

int main(){
   Student s[3] = {
   {"Matt", 20. 90},
   {"Tom", 35. 77},
   {"Jonny", 28. 95},
   };
   
   s[2].name = "Jan";   // Modify the name.
   s[1].score = 30;     // Modify the score.
   
   return 0;
}
```

#### 3. Struct with pointers

```
struct Student {
   string name;
   int age;
   int score;
};

int main(){
   Student s = {"Matt", 20. 90};
   
   Student *p = &s;     // Use pointer to access the structure.
   cout << p->name << endl;
   cout << p->age << endl;
   cout << p->score << endl;
   
   return 0;
}
```

#### 4. Use struct as the parameters of the functions

Pass by value and pass by address.

```
struct Student {
   string name;
   int age;
   int score;
};

void test_1(Student s){
   cout << s.name << endl;
}

void test_2(Student *p){
   cout << p->name << endl;
}

int main(){
   Student s = {"Matt", 20. 90};
   
   test_1(s);
   
   test_2(&s);
   
   return 0;
}
```

#### 5. Struct with const
