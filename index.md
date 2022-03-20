# Welcome to C++

## Catalogue
- [Comments](#Comments)
- [Variables](#Variables)
- [Constants](#Constants)
- [Keywords](#Keywords)
- [Data_Types](#Data_Types)

### Comments
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

### Variables
Give a name to a space in memory.

```markdown
 type variable_Name = value;

 int a = 10;
```

### Constants
Unchangeable data in the program.

```markdown
 #define Constant_Name value
 
 #define DAY 7
```

```markdown

 const Variable_Name = value;

 const int month = 12;
```
### Keywords
Reserved and not available for re-definition or overloading.
[C++ Keywords table](https://en.cppreference.com/w/cpp/keyword)

### Data_Types
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


