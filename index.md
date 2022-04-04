# Welcome to C++

## Catalogue
- [Comments](#Comments)
- [Variables](#Variables)
- [Constants](#Constants)
- [Keywords](#Keywords)
- [Data_Types](#Data_Types)
- [Data_Input](#Data_Input)
- [Operators](#Operators)
- [Program_ontrol_Flow](#Program_Control_Flow)
- [Array](#Array)

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
Arrays are used to store elements of the same type(Data type). Arrays are made up of contiguous memory.

