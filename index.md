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
- [Memory_Layout](#Memory_Layout)
- [Reference](#Reference)
- [Object_Oriented_Programming](#Object_Oriented_Programming)
- [Read_and_write_files](#Read_and_write_files)
- [Templates](#Templates)
- [STL_Intro](#STL_Intro)
- [Functors](#Functors)
- [STL_built_in_algorithms](#STL_built_in_algorithms)

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

#### 6. Default value of parameters of the function:
```
int func(int a, int b = 20， int c = 30){}     // If b has default value, all parameters on the right should have default values.
```

```
void func(int a, int){                         // You must give 2 values while using the function.

}
```

#### 7. Overloading

Conditions: 1. Under the same namespace 2. Name of the function should be the same 3. parameters are different.

```
void func(){
}
```

```
void func(int a){
}
```

```
void func(double a){
}
```

```
void func(int a, double b){
}
```

```
void func(double a, int b){
}
```



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

void test_2(Student *p){         // No need to copy arguments, save memory space.
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
Prevent data modification.

```
struct Student {
   string name;
   int age;
   int score;
};

void test(const Student *p){     // You can not modify the contents of the structure. Safe.
   cout << p->name << endl;
}

int main(){
   Student s = {"Matt", 20. 90};
   
   test(&s);
   
   return 0;
}
```
## Memory_Layout

Memory layout model:
- Text Segment: Contains binary executable instructions. Shared and only readable.
- Global Segment(Initialized and Uninitialized Data Segments): Store global variables, static variables and constants.
- Stack: Automatically allocate and free by the compiler. Stores the values of the parameters of the function, local variables, etc.
- Heap: Manual allocate and free by the programmer. If not de freed manually, it will be reclaimed by the operating system at the end of the program.

Data stored in different segments are given different life cycles. Make programming more flexible.

![avatar](/pics/global_segments.png)

***Caution: Do not return the address of the local variable in a function because the function stores in stack and after excuting the function, the compiler will free all the data inside it.***

```
int* func(){
   int a = 10;
   return &a;     // Return the address of local variable a.
}

int main(){
   int *p = func();
   cout << *p << endl;      // The compiler will save the data once, you can get the result 10;
   cout << *p << endl;      // You can not get 10 because the compiler already free the function which stored in stack.

   return 0;
}
```

The programmer is able to use ``` new  ``` to create the data in heap and use ``` delete ``` to free the data.

```
int* func(){
   int *p = new int(10);
   return p;    
}

void test(){
   int *p = func();
   cout << *p << endl;
   cout << *p << endl;     // Store in heap, pointer p won't be deleted by the compiler.
   cout << *p << endl;
   
   delete p;
}

int main(){
   test();     

   return 0;
}
```
Create a array.
```
void test(){
   int *arr = new int[10];    // 10 elements
   
   for(int i = 0; i < 10; i++){
      arr[i] = i;
   }
   
   delete [] arr;
}

int main(){
   test();     

   return 0;
}
```

## Reference

Give an alternative name of a variable by using ```int * const ref = &a;```. It can be simplified as:

```
int a = 10;
int &b = a;
```

![avatar](/pics/reference_1.png)

Pass by address(using pointers) can be simplified by using reference as the parameters of a function:
```
void func(int &a, int &b){
   int temp = a;
   a = b;
   b = temp;
}

int main(){
   int main_a = 10;
   int main_b = 20;
   
   func(main_a, main_b);
   
   cout << "Now main_a is " << main_a << endl;     // 20, swaped
   cout << "Now main_b is " << main_b << endl;     // 10, swaped
   
   return 0;
}
```

Use reference as the return of a function(Do remember do not return the reference of a local variable!): 
```
int & func(){             // Return the alternative name of a, & is not used for getting the address of the variable.
   int a = 10;
   return a;              // Do not return the reference of the local variable in a function. This is a bad example!
}

int main(){
   int & ref = func();
   cout << ref << endl;   // 10
   cout << ref << endl;   // 26000090846, a has been deleted, ref will lost it's value.
}
```

```
int & func(){
   static int a = 10;     // Stored in global memory space.
   return a;
}

int main(){
   int & ref = func();
   cout << ref << endl;   // 10
   cout << ref << endl;   // 10
   
   func() = 1000;
   
   cout << ref << endl;   // 1000, the result of func() is the alternative name(reference) of static variable a, func() = 1000 is equal to let a = 1000, then ref is equal to 1000 also.
   cout << ref << endl;   // 1000
}
```

## Object_Oriented_Programming

#### 1. Encapsulation

###### 1. How to apply Encapsulation
```
class Circle{
public:
   int m_r;                   // attribute
   
   double perimeter(){        // method
      return 2 * PI * m_r;
   };
}

int main(){
   Circle c;
   c.m_r = 4;
   c.perimeter();

   return 0;
}
```

###### 2. Public, protected and private
public:     Members inside the class can access, members outside the class can access.
protected:  Members inside the class can access, members outside the class can not access.
private:    Members inside the class can access, members outside the class can not access.

The difference between protected and private will be explained in Inheritance.
Struct: default is public, Class: default is private.

```
class Person{
public:
   string m_Name;
  
protected:
   string m_Car;
   
private:
   int m_Password;

public:
   void func(){
      m_Name = "Matt";
      m_Car = "Toyota";
      m_Password = 123456;
   }
}

int main(){
   Person p_1;
   
   p_1.m_Name = "Jonny";
   p_1.m_Car = "Honda";       // Error!
   p_1.m_Password = 123;      // Error!

   return 0;
}
```
### 2. Initialize and delete objects

###### 1. Constructors and Destructors

Constructors: When creating a new object, assign values to the members of this object. Parameters allowed. Overloading allowed.
Destructors: Clean the object. No parameters. Overloading not allowed.
```
Class Person{
public:
   int m_age;

public:
   Person(){
      cout << "This is a constructor without parameters." << endl;
   }
   
   Person(int a){
      m_age = a;
      cout << "This is a constructor with parameters." << endl;
   }

   Person(const Person &p){
      m_age = p.m_age;
      cout << "This is a copy constructor." << endl;                 // Copy from other objects.
   }
   
   ~Person(){
      cout << "This is destructor." << endl;
   }

}

// Three ways to use it.

void method_1(){
   Person p_1;
   Person p_2(22);
   Person p_3(p_2);
}

void method_2(){
   Person p_1;
   Person p_2 = Person(22);
   Person p_3 = Person(p_2);
}

void method_3(){
   Person p_1 = 22;              // Equal to Person p_1 = Person(22);
   Person p_2 = p_1;
}

int main(){
   method_1();
   method_2();
   method_3();
   
   return 0;
}
```

###### 2. When to use copy constructor
- Create an new object by copying.

```
void test_1(){
   Person p_1(20);
   Person p_2(p1);
}
```

- Pass by value.

```
void func(Person p){

}

void test_2(){
   Person p;
   func(p);             // Pass by value, it will call copy constructor.
}
```

- Return local object

```
Person func(){
   Person p_1;
   return p_1;
}

void test_3(){
   Person p = func();    // While returing func() will call copy constructor to save it to p.
}
```

###### 3. Deep copy and shallow copy

shallow cause error here because using "new".
```
class Person{
public:
   int m_Age;
   int *m_Height;                // Going to use "new"

public:
   Person(int age, int height){
      m_Age = age;
      m_Height = new int(height);
   }
   
   ~Person(){
      cout << "Delete m_Height here." << endl;
      if(m_Height != NULL){
         delete m_Height;
         m_Height = NULL;
      }
   }
};

void test(){
   Person p_1(22, 160);
   Person p_2(p1);
}

int main(){
   test();

   return 0;
}
```
![avatar](/pics/shallow_copy.png)

Solve it by using deep copy(Implementing your own copy constructor).
```
class Person{
public:
   int m_Age;
   int *m_Height;                // Going to use "new"

public:
   Person(int age, int height){
      m_Age = age;
      m_Height = new int(height);
   }
   
   Person(const Person &p){
      m_Age = p.age
      m_Height = mew int(*p.m_Height);
   }
   
   ~Person(){
      cout << "Delete m_Height here." << endl;
      if(m_Height != NULL){
         delete m_Height;
         m_Height = NULL;
      }
   }
};

void test(){
   Person p_1(22, 160);
   Person p_2(p1);
}

int main(){
   test();

   return 0;
}
```

###### 4. Constructor initializer list
```
class Person{
public:
   int m_A;
   int m_B;
   int m_C;
  
public:
   Person():m_A(10),m_B(20),m_C(30){
   }

};
```

```
class Person{
public:
   int m_A;
   int m_B;
   int m_C;
  
public:
   Person(int a, int b, int c):m_A(a),m_B(b),m_C(c){
   }

};
```

###### 5. An object is a member of another class

```
class A{};

class B{
   A a;
};
```

Call constructor A first(create a first), then call constructor B.
Call destructor B first(delete object of class B first), then call destructor A.


###### 6. Static data members

- All objects of a class share this data. It does not belong to any single object.
- Allocating memory during compilation.
- Declare inside the class, initialize outside the class.
- Can be accessed by class name and object.

```
class Person{
public:
   static int m_Age;
};

int Person::m_Age = 100;            // Initialize outside the class.

void test(){
   Person p_1;
   
   Person p_2;
   p_2.m_Age = 200;
   cout << p_1.m_Age << endl;       // 200, p_1 and p_2 are sharing static member m_Age.
   cout << Person::m_Age << endl;   // Access by class name.
}

int main(){
   test();

   return 0;
}
```


###### 7. Static member functions

- All objects share same functions.
- static members functions can only access static data members because a static member function is global to all objects, it cannot tell which object an regular member variable belongs to.
- Can be accessed by class name and object.

###### 8. Memory allocation of a object

1 byte for an empty object.
```
class Person{

};

void test (){
   Person p;
   cout << sizeof(p) << endl;          // Compiler will allocate 1 byte for an empty object to distinguish between different empty objects.
}
```

4 bytes for this object.
```
class Person{
   int m_Age;                          // belongs to the object
   static int m_Score;                 // Does not belong to object
   void func_1(){}                     // Does not belong to object
   static void func_2(){}              // Does not belong to object
};

void test (){
   Person p;
   cout << sizeof(p) << endl;
```

###### 9. this pointer

- Resolve name conflicts.
- Return object itself(*this)

```
class Person{
public:
   int age
public:
   Person(int age){
      this->age = age;
   }
   
   Person Add(Person &p){
      this->age += p.age;
      return *this            // return object itself
   }
};

void test(){
   Person p_1(10);
   
   Person p_2(10);
   
   p_2.Add(p_1).Add(p_1).Add(p_1);     // 40
}
```

###### 10. Member functions with const

- const functions
1. Members acn not be modified.
2. Keyword 'mutable' can disable the function of const.
3. const Person * const this;

```
class Person{
public:

   void showInfo() const {
      m_A = 100;           // Error.
      m_B = 100;           // OK.
   }
   
   int m_A;
   mutable int m_B;
};
```

- const objects
1. Unable to modify the members inside the object expect mutable.
2. const object can only call const functions.
```
const Person p;
```

### 3. Friend class and function
- Global function as friend
In the program code, some private properties also want to be accessed by some functions outside the class, so friends are needed.

```
class Building{
   
   friend void person(Building & building);     // Friend

private:
   string m_Bedroom;
  
public:
   Building(){
      m_Bedroom = "My Bedroom!";
   }
};

void person(Building &building){
   cout << building.m_Bedroom << endl;    // m_Bedroom can be accessed by using 'friend'. 
}
```

- Class as friend

```
class Building;

class Person{
public:
   Person();
   
public:
   Building * building;
   
public:
   void visit();
};

class Building{
   friend class Person;          // Friend

public:
   Building();

public:
   string m_Livingroom;
private:
   string m_Bedroom;
};

Building::Building(){
   m_Livingroom = "My living room!";
   m_Bedroom = "My bedroom!";
}

Person::Person(){
   building = new Building;
}

Person::void visit(){
   cout << "Is visiting " << building->m_Livingroom << endl;
   
   cout << "Is visiting " << building->m_Bedroom << endl; 
}

void test(){
   Person p;
   p.visit();
}

int main(){
   test();
   
   return 0;
}
```
- Member functions as friend.

```
class Building;

class Person{
public:
   Person();
   
public:
   Building * building;
   
public:
   void visit_1();      // Let it can access private members of class Building.
   void visit_2();      // Let it can not access private members of class Building.
};

class Building{
   friend void Person::visit_1();         // Friend

public:
   Building();

public:
   string m_Livingroom;
private:
   string m_Bedroom;
};

Building::Building(){
   m_Livingroom = "My living room!";
   m_Bedroom = "My bedroom!";
}

Person::Person(){
   building = new Building;
}

Person::void visit_1(){
   cout << "Is visiting " << building->m_Livingroom << endl;
}

Person::void visit_2(){  
   cout << "Is visiting " << building->m_Bedroom << endl; 
}

void test(){
   Person p;
   p.visit_1();
   p.visit_2();
}

int main(){
   test();
   
   return 0;
}
```

### 4. Operator Overloading

Redefine an existing operator, for example '+' operator can be only used for adding numbers. What if we want to use '+' to add two objects as we want?
Operator overloading can also implement functional overloading.
###### 1. '+' overloading
- Overloading with class function
```
class Person{
public:
   int m_A;
   int m_B;
   
public:
   Person operator+(Person &p){           // Implement overloading. 
      Person temp;
      temp.m_A = this->m_A + p.m_A;
      temp.m_B = this->m_B + p.m_B;
      return temp;
   }

};

void test(){
   Person p_1;
   p_1.m_A= 10；
   p_1.m_B= 10；
   
   Person p_2;
   p_2.m_A= 10；
   p_2.m_B= 10；
   
   Person p_3 = p_1 + p_2;                   // Simplfied by compiler. Same as Person p_3 = p_1.operator+(p_2);
}
```

- Overloading with global function
```
class Person{
public:
   int m_A;
   int m_B;
};

Person operator+(Person &p_1, Person &p_2){              // Implement overloading
      Person temp;
      temp.m_A = p_1.m_A + p_2.m_A;
      temp.m_B = p_1.m_B + p_2.m_B;
      return temp;
}

void test(){
   Person p_1;
   p_1.m_A= 10；
   p_1.m_B= 10；
   
    Person p_2;
   p_2.m_A= 10；
   p_2.m_B= 10；
   
   Person p_3 = p_1 + p_2;                                // Simplfied by compiler. Same as Person p_3 = operator+(p_1, p_2);
}
```

###### 2. '<<' overloading
Do it by yourself.
###### 3. '++' overloading
Do it by yourself.
###### 4. '=' overloading

```
class Person{
public:

   Person(int age){
      m_Age = new int(age);
   }
   
   int *m_Age;
   
   Person& operator=(Person &p){
   if(m_Age != NULL){
      delete m_Age;
      m_Age = NULL;
      
      return *this;
   }

   m_Age = new int(*p.m_Age);
}
   
   ~Person(){
      if(m_Age != NULL){
         delete m_Age;
         m_Age = NULL;
      }
   }
};

void test_1(){
   Person p_1(18);
   
   Person p_2(20);
   
   p_2 = p_1;
   
   cout << *p_1.m_Age = << endl;
   
   cout << *p_2.m_Age = << endl;
}

int main(){
   test_1();

   return 0;
}
```
###### 5. '==' overloading
Do it by yourself.
###### 6. '()' overloading
Do it by yourself.

### 5. Inheritance
###### 1. Basic 
The Derived class inherits the properties of the base class and can also have its own properties.
```
class A{
public:
   Base(){
      m_A = 100;
   }
   
   int m_A;
};

class B : public A{
     Son(){
     m_A = 200;
   }
   
   int m_A;
};

void test(){
   Son s;
   cout << s.m_A << endl;        // 200
   cout << s.Base::m_A << endl;  // 100
}
```

###### 2. Three ways of inheritance
- public
- protected
- private

![avatar](/pics/3_ways_inheritance.png)

###### 3. Multiple inheritance
Not recommended to use.
```
class A
{
   ...
};
  
class B
{
public:
   ...
};
  
class C: public B, public A
{
   ...
};
```

###### 4. Virtual inheritance
- Problems with diamond inheritance
```
class A{
public:
   int m_Age; 
};

class B : public A{};

class C : public A{};

class D : public B, public C{
   
};

void test(){
   D d;
   d.m_Age = 10;              // Error! It doesn't know which class belongs to.
   d.B::m_Age = 20;
   d.C::m_Age = 30;
}
```
- How to solve it
By using virtual inheritance.
```
class A{                      // Virtual base class
public:
   int m_Age; 
};

class B : virtual public A{};

class C : virtual public A{};

class D : public B, public C{
   
};

void test(){
   D d;
   d.m_Age = 10;                 // Correct! They all share same m_Age.
   d.B::m_Age = 20;
   d.C::m_Age = 30;
   cout << d.B::m_Age << endl;   // 30, B::m_Age is the C::m_Age.
}
```

### 6. Polymorphism
###### 1. Basic
Polymorphism occurs when a base class pointer or reference points to a derived class object. ``` Animal & animal = cat;```

- Static polymorphism(Determine the address of the function while compiling): function overloading, operator overloading
- Dynamic polumorphism(Determine the address of the function while excuting): derived class, virtual functions


Static polymorphism, the outcome is "Animal is speaking" because the address of speak function already been determined while compiling and the object is Animal class, it will navigate to the speak function of the Animal class.
```
class Animal{
public:
   void speak(){
      cout << "Animal is speaking!" << endl; 
   }
};

class Cat : public Animal{
public:
   void speak(){
      cout << "Cat is speaking!" << endl;
   }
};

void doSpeak(Animal & animal){
   animal.speak();
}

void test(){
   Cat cat;
   doSpeak(cat);
}
```

 Dynamic polymorphism, after adding keyword 'virtual', the address will be determined later. Now the outcome will be "Cat is speaking!".
 ```
class Animal{
public:
   virtual void speak(){
      cout << "Animal is speaking!" << endl; 
   }
};

class Cat : public Animal{
public:
   void speak(){
      cout << "Cat is speaking!" << endl;
   }
};

void doSpeak(Animal & animal){
   animal.speak();
}

void test(){
   Cat cat;
   doSpeak(cat);
}
```
![avatar](/pics/polymorphism.png)

###### 2. Pure virtual functions and abstract classes(Interface)
When a class has a pure virtual function, it will become an abstract class. An abstract class cannot create an object and derived classes must overwrite pure virtual functions.
```
virtual int func() = 0;
```
###### 3. Virtual destructor and pure virtual destructor
When polymorphism occurs(``` Animal & animal = cat;```), if derived class has some attributes been created in heap, then while releasing base pointer, the deconstructor of derived class cannot be called. Virtual destructor and pure virtual destructor can solve this issue.

```
class Animal{
public:
   virtual void speak() = 0;
};

class Cat: public Animal{
public:
   Cat(string name){
      m_Name = new string(name);
   }

   virtual void speak(){
      cout << *m_Name << "cat is speaking!" << endl;
   }
   string *m_Name;
   
   ~Cat(){                                // This one won't be called because if you delete animal, it will call the destructor of base class only.
      if(m_Name != NULL){
         delete m_Name;
         m_Name = NULL;
      }
   }
};

void test(){
   Animal * animal = new Cat("Tom");
   animal -> speak();
   delete animal;
}
```

How to solve it:
```
class Animal{
public:
   virtual void speak() = 0;
   
   virtual ~Animal(){
   
   }
};

class Cat: public Animal{
public:
   Cat(string name){
      m_Name = new string(name);
   }

   virtual void speak(){
      cout << *m_Name << "cat is speaking!" << endl;
   }
   string *m_Name;
   
   ~Cat(){                                
      if(m_Name != NULL){
         delete m_Name;
         m_Name = NULL;
      }
   }
};

void test(){
   Animal * animal = new Cat("Tom");
   animal -> speak();
   delete animal;
}
```

## Read_and_write_files
Use header file ```<fstream>```.
- ofstream: write
- ifstream: read
- fstream: read and write
   
   
### 1. Write ASCII files
```
#include <fstream>

ofstream ofs;                    // Create stream object.

ofs.open("path", ios::out);       // ios::out means open the file for writing. other ways: ios::out, ios::ate, ios::app, ios::trunc, ios::binary

ofs << "content";

ofs.close();
```

### 2. Read ASCII files
```
#include <fstream>

ifstream ifs;                          // Create stream object.

ifs.open("path", ios::in);

char buf[1024] = {0};
while(ifs >> buf){                     // Fisrt method to read the file.
   cout << buf << endl;
}

while(ifs.getline(buf, sizeof(buf))){  // Second method.
   cout << buf << endl;
}

string buf;                            // Third method.
while(getline(ifs.buf)){
   cout << buf << endl;
}

char c;                                // Fourth method, not recommand.
while((c = ifs.get()) != EOF){
   cout << c;
}

ifs.close();
```

### 3. Write binary files
```
class Person{
public:
   char m_Name[64];
   int m_Age;
};

void test(){
   ofstream ofs("person.txt", ios::out | ios::binary);
   
   Person p = {"Matt", 26};
   
   of.write((const char *) &p, sizeof(p));
   
   ofs.close();
}
```

### 4. Read binary files
```
ifstream ifs;

ifs.open("person.txt", ios::in | ios::binary);

Person p;

ifs.read((char *) &p, sizeof(Perosn));

ifs.close();
```

## Templates
### 1. Function templates
###### 1. Concepts
```
template<typename T>                   // T can be any letters.
```

```
void swap(int &a, int &b){             // This function can only swap integers.
   int temp = a;
   a = b;
   b = temp;
}

template<typename T>                   // a and b must defined while using it and they must have same data types.
void tSwap(T &a, T &b){
   T temp = a;
   a = b;
   b = temp;
}

void test(){
   int a = 10;
   int b = 20;
   
   tSwap(a, b);                         // Auto.
   tSwap<int>(a, b);                    // Manual.
}
```

###### 2. Difference between regular functions and template functions
Regular functions have implicit conversions, but template functions don't have.
```
int add(int &a, int &b){
   return c = a + b;
}

void test(){
   int a = 10;
   char c = 'c'                          // c - 99
   cout << add(a, c) << endl;            // Able to excute.
}
```

###### 3. Limitation of templates
```
template<typename T>
void fun(T a, T b){
   a =  b;                                // Won't be excuted while a and b are arrays.
}
```
Operator overloading can solve this issue.

### 2. Class templates
###### 1. Concepts
```
template<typename T>                       // typename can also use class.
class Person{
   ...
   };
 ```
 
 ```
 template<class NameType, class AgeType>
 class Person{
 public:
   Person(NameType name, AgeType age){
      m_Name = name;
      m_Age = age;
   }
 
   NameType m_Name;
   AgeType m_Age;
 };
 
 void test(){
   Person<string, int> p_1("Matt", 26);
 }
 ```
 
###### 2. Difference between function templates and class templates
 - No auto derive for class templates, you have to define the data types while using it.
 - class templates can have default parameters.

###### 3. Template object as function parameter
```
template<class T1, class T2>
class Person{
public:
   Person(T1 name, T2 age){
      m_Name = name;
      m_Age = age;
   }
   
   void showInfo(){
      cout << "Person info!" << endl;
   }
   
   T1 m_Name;
   T2 m_Age
};

void printPerson(Person<string, int> &p){
   p.showInfo();
}

void test_1(){
   Person<string, int> p("Matt", 26);
   printPerson(p);
}
```
Or
```
template<class T1, class T2>
class Person{
public:
   Person(T1 name, T2 age){
      m_Name = name;
      m_Age = age;
   }
   
   void showInfo(){
      cout << "Person info!" << endl;
   }
   
   T1 m_Name;
   T2 m_Age
};

template<class T1, T2>
void printPerson(Person<T1, T2> &p){
   p.showInfo();
}

void test_1(){
   Person<string, int> p("Matt", 26);
   printPerson(p);
}
```
Or
```
template<class T1, class T2>
class Person{
public:
   Person(T1 name, T2 age){
      m_Name = name;
      m_Age = age;
   }
   
   void showInfo(){
      cout << "Person info!" << endl;
   }
   
   T1 m_Name;
   T2 m_Age
};

template<class T>
void printPerson(T &p){
   p.showInfo();
}

void test_1(){
   Person<string, int> p("Matt", 26);
   printPerson(p);
}
```

###### 4. Templates and inheritance
```
template<class T>
class Base{
   T m;
};

class Son : public Base<int>{                   // Data type must be confirmed.
   
};
```
Or
```
template<class T>
class Base{
   T m;
};

template<class T1, class T2>
class Son : public Base<T2>{                   // Data type must be confirmed.
   T1 obj;
};
```

## STL_Intro
reference: https://www.geeksforgeeks.org/

### 1. vector
Similar to array, but the length can be changed arbitrarily when in use.
- Container: ```vector```
- Algorithm: ```for_each```
- Iterator: ```vector<int>::iterator```

```
#include <vector>
#include <algorithm>

void myPrint(int val){
   cout << val << endl;
}

void test(){
   vector<int> v;
   
   v.push_back(10);                             // Insert data into the container.
   v.push_back(20);
   v.push_back(30);
   
   vector<int>::iterator itBegin = v.begin();   // Iterator points at the beginning of the vector.
   vector<int>::iterator itEnd = v.end();
   while(itBegin != itEnd){                     // Get the data one by one.
      cout << *itBegin << endl;
      itBegin++;
   }
   
   for (vector<int>::iterator it = v.begin(); it != v.end(); it++){     // Second way for getting the data from vector.
      cout << *it << endl;
   }
   
   for_each(v.begin(), v.end(), myPrint);
}
```

```
class Person{
public:
   Person(string name, int age){
      m_Nmae = name;
      m_Age = age;
   }

   string m_Name;
   int m_Age;
};

void test(){
   vector<Person> v;
   
   Person p_1("Matt", 26);
   Person p_2("Amy", 27);
   Person p_3("Bob", 28);
   
   v.push_back(p_1);
   v.push_back(p_2);
   v.push_back(p_3);
   
   for(vector<Person>::iterator)
}
```

- Iterators:


```begin()``` – Returns an iterator pointing to the first element in the vector.

```end()``` – Returns an iterator pointing to the theoretical element that follows the last element in the vector.

```rbegin()``` – Returns a reverse iterator pointing to the last element in the vector (reverse beginning). It moves from last to first element

```rend()``` – Returns a reverse iterator pointing to the theoretical element preceding the first element in the vector (considered as reverse end)

```cbegin()``` – Returns a constant iterator pointing to the first element in the vector.

```cend()``` – Returns a constant iterator pointing to the theoretical element that follows the last element in the vector.

```crbegin()``` – Returns a constant reverse iterator pointing to the last element in the vector (reverse beginning). It moves from last to first element

```crend()``` – Returns a constant reverse iterator pointing to the theoretical element preceding the first element in the vector (considered as reverse end)

- Capacity:


```size()``` – Returns the number of elements in the vector.

```max_size()``` – Returns the maximum number of elements that the vector can hold.

```capacity()``` – Returns the size of the storage space currently allocated to the vector expressed as number of elements.

```resize(n)``` – Resizes the container so that it contains ‘n’ elements.

```empty()``` – Returns whether the container is empty.

```shrink_to_fit()``` – Reduces the capacity of the container to fit its size and destroys all elements beyond the capacity.

```reserve()``` – Requests that the vector capacity be at least enough to contain n elements.

- Element access:


```reference operator [g]``` – Returns a reference to the element at position ‘g’ in the vector

```at(g)``` – Returns a reference to the element at position ‘g’ in the vector

```front()``` – Returns a reference to the first element in the vector

```back()``` – Returns a reference to the last element in the vector

```data()``` – Returns a direct pointer to the memory array used internally by the vector to store its owned elements.

- Modifiers:


```assign()``` – It assigns new value to the vector elements by replacing old ones

```push_back()``` – It push the elements into a vector from the back

```pop_back()``` – It is used to pop or remove elements from a vector from the back.

```insert()``` – It inserts new elements before the element at the specified position

```erase()``` – It is used to remove elements from a container from the specified position or range.

```swap()``` – It is used to swap the contents of one vector with another vector of same type. Sizes may differ.

```clear()``` – It is used to remove all the elements of the vector container

```emplace()``` – It extends the container by inserting new element at position

```emplace_back()``` – It is used to insert a new element into the vector container, the new element is added to the end of the vector

### 2. string
- Modifiers:


```etline()```	This function is used to store a stream of characters as entered by the user in the object memory.

```push_back()```	This function is used to input a character at the end of the string.

```pop_back()```	Introduced from C++11(for strings), this function is used to delete the last character from the string.

```copy(“char array”, len, pos)``` 	This function copies the substring in the target character array mentioned in its arguments. It takes 3 arguments, target char array, length to be copied, and starting position in the string to start copying.

```swap()```	This function swaps one string with other.

- Capacity:


```capacity()```	This function returns the capacity allocated to the string, which can be equal to or more than the size of the string. Additional space is allocated so that when the new characters are added to the string, the operations can be done efficiently.

```resize()```	This function changes the size of the string, the size can be increased or decreased.

```length()```	This function finds the length of the string.

```shrink_to_fit()```	This function decreases the capacity of the string and makes it equal to the minimum capacity of the string. This operation is useful to save additional memory if we are sure that no further addition of characters has to be made.

- Iterator:


```begin()```	This function returns an iterator to the beginning of the string.

```end()```	This function returns an iterator to the end of the string.

```rbegin()```	This function returns a reverse iterator pointing at the end of the string.

```rend()```	This function returns a reverse iterator pointing at beginning of the string.

### 3. Deque
Double-ended queues are sequence containers with the feature of expansion and contraction on both ends.

- Modifiers:


```deque::insert()```	Inserts an element. And returns an iterator that points to the first of the newly inserted elements.

```deque::rbegin()```	Returns a reverse iterator which points to the last element of the deque (i.e., its reverse beginning).

```deque::rend()```	Returns a reverse iterator which points to the position before the beginning of the deque (which is considered its reverse end).

```deque::cbegin()```	Returns a constant iterator pointing to the first element of the container, that is, the iterator cannot be used to modify, only traverse the deque.

```deque::max_size()```	Returns the maximum number of elements that a deque container can hold.

```deque::assign()```	Assign values to the same or different deque container.

```deque::resize()``` 	Function which changes the size of the deque.

```deque::push_front()```	It is used to push elements into a deque from the front.

```deque::push_back()``` 	This function is used to push elements into a deque from the back.

```deque::pop_front() and deque::pop_back()```	pop_front() function is used to pop or remove elements from a deque from the front. pop_back() function is used to pop or remove elements from a deque from the back.

```deque::front() and deque::back()```	front() function is used to reference the first element of the deque container. back() function is used to reference the last element of the deque container.

```deque::clear() and deque::erase()``` 	clear() function is used to remove all the elements of the deque container, thus making its size 0. erase() function is used to remove elements from a container from the specified position or range.

```deque::empty() and deque::size()```	empty() function is used to check if the deque container is empty or not. size() function is used to return the size of the deque container or the number of elements in the deque container.

```deque::operator= and deque::operator[]```	operator= operator is used to assign new contents to the container by replacing the existing contents. operator[] operator is used to reference the element present at position given inside the operator.

```deque::at() and deque::swap()```	at() function is used reference the element present at the position given as the parameter to the function. swap() function is used to swap the contents of one deque with another deque of same type and size.

```deque::begin() and deque::end``` 	begin() function is used to return an iterator pointing to the first element of the deque container. end() function is used to return an iterator pointing to the last element of the deque container.

```deque::emplace_front() and deque::emplace_back()``` 	emplace_front() function is used to insert a new element into the deque container. The new element is added to the beginning of the deque. emplace_back() function is used to insert a new element into the deque container. The new element is added to the end of the deque.

```deque::find()```	Finds the element in the given range of numbers. Returns an iterator to the first element in the range [first,last] that compares equal to val. If no such element is found, the function returns last.

### 4. Stack
Stacks are a type of container adaptors with LIFO(Last In First Out) type of working, where a new element is added at one end (top) and an element is removed from that end only. 

- Methods:
```empty()``` – Returns whether the stack is empty – Time Complexity : O(1) 

```size()``` – Returns the size of the stack – Time Complexity : O(1) 

```top()``` – Returns a reference to the top most element of the stack – Time Complexity : O(1) 

```push(g)``` – Adds the element ‘g’ at the top of the stack – Time Complexity : O(1) 

```pop()``` – Deletes the top most element of the stack – Time Complexity : O(1) 

### 5. Queue
Queues are a type of container adaptors that operate in a first in first out (FIFO) type of arrangement. Elements are inserted at the back (end) and are deleted from the front.

- Methods:
```queue::empty()```	Returns whether the queue is empty.

```queue::size()```	Returns the size of the queue.

```queue::swap()```	Exchange the contents of two queues but the queues must be of the same type, although sizes may differ.

```queue::emplace()```	Insert a new element into the queue container, the new element is added to the end of the queue.

```queue::front()```	Returns a reference to the first element of the queue.

```queue::back()```	Returns a reference to the last element of the queue.

```queue::push(g)``` 	Adds the element ‘g’ at the end of the queue.

```queue::pop()``` 	Deletes the first element of the queue.

### 6. List
Lists are sequence containers that allow non-contiguous memory allocation. As compared to vector, the list has slow traversal, but once a position has been found, insertion and deletion are quick.

- Methods:
```front()```	Returns the value of the first element in the list.

```back()```	Returns the value of the last element in the list.

```push_front(g)```	Adds a new element ‘g’ at the beginning of the list.

```push_back(g)``` 	Adds a new element ‘g’ at the end of the list.

```pop_front()```	Removes the first element of the list, and reduces size of the list by 1.

```pop_back()```	Removes the last element of the list, and reduces size of the list by 1.

```list::begin()```	begin() function returns an iterator pointing to the first element of the list.

```list::end()```	end() function returns an iterator pointing to the theoretical last element which follows the last element.

```list rbegin() and rend()```	rbegin() returns a reverse iterator which points to the last element of the 

```list. rend()``` returns a reverse iterator which points to the position before the beginning of the list.

```list cbegin() and cend()``` 	 cbegin() returns a constant random access iterator which points to the beginning of the list. cend() returns a constant random access iterator which points to the end of the list.

```list crbegin() and crend()``` 	crbegin() returns a constant reverse iterator which points to the last element of the list i.e reversed beginning of container. crend() returns a constant reverse iterator which points to the theoretical element preceding the first element in the list i.e. the reverse end of the list.

```empty()``` 	Returns whether the list is empty(1) or not(0).

```insert()```	Inserts new elements in the list before the element at a specified position.

```erase()```	Removes a single element or a range of elements from the list.

```assign()```	Assigns new elements to list by replacing current elements and resizes the list.

```remove()```	Removes all the elements from the list, which are equal to given element.

```list::remove_if()```	Used to remove all the values from the list that correspond true to the predicate or condition given as parameter to the function.

```reverse()```	Reverses the list.

```size()```	Returns the number of elements in the list.

```list resize()```	Used to resize a list container.

```sort()```	Sorts the list in increasing order.

```list max_size()``` 	Returns the maximum number of elements a list container can hold.

```list unique()```	Removes all duplicate consecutive elements from the list.

```list::emplace_front() and list::emplace_back()```	emplace_front() function is used to insert a new 
element into the list container, the new element is added to the beginning of the list. emplace_back() function is used to insert a new element into the list container, the new element is added to the end of the list.

```list::clear()```	clear() function is used to remove all the elements of the list container, thus making it size 0.

```list::operator=```	This operator is used to assign new contents to the container by replacing the existing contents.

```list::swap()```	This function is used to swap the contents of one list with another list of same type and size.

```list splice()```	Used to transfer elements from one list to another.

```list merge()```	Merges two sorted lists into one.

```list emplace()```	Extends list by inserting new element at a given position.

### 7. set and multiset
After inserting all the elements, they will be sorted. Set can not have same emelemts, multiset can have same elements.  

- Methods:
```begin()```	Returns an iterator to the first element in the set.

```end()```	Returns an iterator to the theoretical element that follows the last element in the set.

```rbegin()```	Returns a reverse iterator pointing to the last element in the container.

```rend()```	Returns a reverse iterator pointing to the theoretical element right before the first element 
in the set container.

```crbegin()```	Returns a constant iterator pointing to the last element in the container.

```crend()```	Returns a constant iterator pointing to the position just before the first element in the container.

```cbegin()```	Returns a constant iterator pointing to the first element in the container.

```cend()```	Returns a constant iterator pointing to the position past the last element in the container.

```size()```	Returns the number of elements in the set.

```max_size()```	Returns the maximum number of elements that the set can hold.

```empty()```	Returns whether the set is empty.

```insert(const g)``` 	Adds a new element ‘g’ to the set.

```iterator insert (iterator position, const g)```	Adds a new element ‘g’ at the position pointed by the iterator.

```erase(iterator position)``` 	Removes the element at the position pointed by the iterator.

```erase(const g)```	Removes the value ‘g’ from the set.

```clear()``` 	Removes all the elements from the set.

```key_comp() / value_comp()```	Returns the object that determines how the elements in the set are ordered 
(‘<‘ by default).

```find(const g)```	Returns an iterator to the element ‘g’ in the set if found, else returns the iterator to 
end.

```count(const g)```	Returns 1 or 0 based on the element ‘g’ is present in the set or not.

```lower_bound(const g)```	Returns an iterator to the first element that is equivalent to ‘g’ or definitely 
will not go before the element ‘g’ in the set.

```upper_bound(const g)```	Returns an iterator to the first element that will go after the element ‘g’ in the 
set.

```equal_range()```	The function returns an iterator of pairs. (key_comp). The pair refers to the range that 
includes all the elements in the container which have a key equivalent to k.

```emplace()```	This function is used to insert a new element into the set container, only if the element 
to be inserted is unique and does not already exist in the set.

```emplace_hint()```	Returns an iterator pointing to the position where the insertion is done. If the element 
passed in the parameter already exists, then it returns an iterator pointing to the position where the 
existing element is.

```swap()```	This function is used to exchange the contents of two sets but the sets must be of the same 
type, although sizes may differ.

```operator=```	The ‘=’ is an operator in C++ STL which copies (or moves) a set to another set and 
set::operator= is the corresponding operator function.

```get_allocator()```	Returns the copy of the allocator object associated with the set.

### 8. map and multimap(hash table)
```key : value``` map can not have same keys but multimap can have.
- Methods:

```map::insert()```	Insert elements with a particular key in the map container.

```map:: count()```	Returns the number of matches to element with key-value ‘g’ in the map.

```map equal_range()```	Returns an iterator of pairs. The pair refers to the bounds of a range that includes 
all the elements in the container which have a key equivalent to k.

```map erase()```	Used to erase elements from the container.

```map rend()```	Returns a reverse iterator pointing to the theoretical element right before the first key-
value pair in the map(which is considered its reverse end).

```map rbegin()``` 	Returns a reverse iterator which points to the last element of the map.

```map find()```	Returns an iterator to the element with key-value ‘g’ in the map if found, else returns the 
iterator to end.

```map crbegin() and crend()``` 	crbegin() returns a constant reverse iterator referring to the last element 
in the map container. crend() returns a constant reverse iterator pointing to the theoretical element before 
the first element in the map.

```map cbegin() and cend()```	 cbegin() returns a constant iterator referring to the first element in the map 
container. cend() returns a constant iterator pointing to the theoretical element that follows the last 
element in the multimap.

```map emplace()```	Inserts the key and its element in the map container.

```map max_size()``` 	Returns the maximum number of elements a map container can hold.

```map upper_bound()```	Returns an iterator to the first element that is equivalent to mapped value with key-
value ‘g’ or definitely will go after the element with key-value ‘g’ in the map

```map operator=```	Assigns contents of a container to a different container, replacing its current content.

```map lower_bound()```	Returns an iterator to the first element that is equivalent to the mapped value with 
key-value ‘g’ or definitely will not go before the element with key-value ‘g’ in the map.

```map emplace_hint()```	Inserts the key and its element in the map container with a given hint.

```map value_comp()``` 	Returns the object that determines how the elements in the map are ordered (‘<‘ by 
default).

```map key_comp()``` 	Returns the object that determines how the elements in the map are ordered (‘<‘ by 
default).

```map::size()```	Returns the number of elements in the map.

```map::empty()```	Returns whether the map is empty

```map::begin() and end()```	begin() returns an iterator to the first element in the map. end() returns an 
iterator to the theoretical element that follows the last element in the map

```map::operator[]```	This operator is used to reference the element present at the position given inside 
the operator.

```map::clear()``` 	Removes all the elements from the map.

```map::at() and map::swap()```	at() function is used to return the reference to the element associated with 
the key k. swap() function is used to exchange the contents of two maps but the maps must be of the same 
type, although sizes may differ.

## Functors
### 1. Functors
- Consider a function that takes only one argument. However, while calling this function we have a lot more information that we would like to pass to this function, but we cannot as it accepts only one parameter.
- It's a class, not a function
- Similar as calling a function
- While using functors, it can be called as the regular functions, can have parameters and returns.

Example 1:
```
class MyAdd{
public:
   int operator()(int v1, int v2){
      return v1 + v2;
   }
}:

void test(){
   MyAdd ma;
   
   cout << ma(10, 10) << endl;
}
```

Example 2:
```
class MyPrint{
public:
   MyPring(){
      count = 0;
   }

   void operator()(string test){
      cout << test << endl;
      count++;
   }
   
   int count;                       // For counting how many times does the operator been called.
}:

void test(){
   MyPrint mp;
   
   cout << mp("Hello world!") << endl;
   
   cout << mp.count << endl;
}
```

Example 3:
```
class MyPrint{
public:
   MyPring(){
      count = 0;
   }

   void operator()(string test){
      cout << test << endl;
      count++;
   }
   
   int count;                       // For counting how many times does the operator been called.
}:

void doPrint(MyPrint & mp, string test){
   mp(test);
}

void test(){
   MyPrint mp;
   doprint(mp, "Hello world!");
   
   cout << mp.count << endl;
}
```

### 2. Predicates
- The functors which return bools called predicates.
```
class Genarator{
public:
   bool operator()(int val){
      return val > 5;
   }
};

void test(){
   vector<int> v;
   for(int i = 0; i < 10; i++){
      v.push_back(i);
   }
   
   vector<int>::iterator it = find_if(v.begin(), v.end(), Genarator());                // Genarator is predicate.
   
   if(it == v.end()){
      cout << "Didn't find" << endl;
   }
   else{
      cout << it << endl;
   }
}
```

### 3. STL built in functors
```
#include<functinal>

void test(){
   negate<int> n;
   
   cout << n(50) << endl;           // -50
}
```

```
#include<functinal>

void test(){
   plus<int> p;
   
   cout << p(1, 1) << endl;          // 2
}
```

```
#include<functinal>

void test(){
   vector<int> v;
   
   v.push_back(1);
   v.push_back(3);
   v.push_back(2);
   v.push_back(8);
   v.push_back(5);
   
   for(vector<int>::iterator it = v.begin(); it != v.end(); it++){
      cout << *it << " ";
   }
   cout << endl;
   
   sort(v.begin(), v.end(), greater<int>());                   // greater is a built in predicate, no need to write it by yourself.
   
      for(vector<int>::iterator it = v.begin(); it != v.end(); it++){
      cout << *it << " ";
   }
   cout << endl;
}
```

## STL built in algorithms
### 1. Iterate
###### 1. for_each
```
for_each
```

Using regular functions:
```
void print_1(int val){
   cout << val << endl;
}

void test(){
   vector<int> v;
   
   for (i = 0; i < 10; i++){
      v.push_back(i);
   }
   
   for_each(v.begin(), v.end(), print_1());
}
```

Using functors:
```
class print_1{
public:
   void operator()(int val){
      cout << val << endl;
   }
};

void test(){
   vector<int> v;
   
   for (i = 0; i < 10; i++){
      v.push_back(i);
   }
   
   for_each(v.begin(), v.end(), print_1());
}
```

###### 2. transform
```
int main()
{
  int arr1[] = {1, 2, 3};
  int arr2[] = {4, 5, 6};
  int n = sizeof(arr1)/sizeof(arr1[0]);
  int res[n];
 
  // Single line code to add arr1[] and arr2[] and
  // store result in res[]
  transform(arr1, arr1+n, arr2, res, plus<int>());
 
  for (int i=0; i<n; i++)
    cout << res[i] << " ";
}
```

### 2. Find
```
vector<int>::iterator it = find(v.begin(), v.end(), 5);
```

```
find_if
```

```
adjacent_find
```

```
binary_search
```

```
count
```

```
count_if
```

### 3. Sort
```
sort(v.begin(), v.end());
```

```
random_shuffle
```

```
merge
```

```
reverse
```

### 4. Copy and replace

```
copy(v_1.begin(), v_1.end(), v_2.begin());
```

```
replace
```

```
replace_if
```

```
swap
```

### 5. Calculate
```
#include<numeric>

int total = accumulate(v.begin(), v.end(), 0);        // plus 0
```

```
fill
```

### 6. Sets
```
set_intersection(v_1.begin(), v_1.end(),v_2.begin(), v_2.end(), vTarget.begin());
```

```
set_union
```

```
set_difference
```

