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
