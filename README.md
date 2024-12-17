# C++ Notes
## Table of Contents
- [Input and Output](#input-and-output)
- [Comments](#comments)
- [The Standard Library](#the-standard-library)
- [Data Types](#data-types)
   - [Modifiers](#modifiers)
   - [Variables](#variables)
   - [Strings](#strings)
   - [Chars](chars)
- [Pointers](#pointers)
- [Operations](#operations)
   - Basic Math Operations
   - Boolean Operations
   - Bitwise Operations
   - Ternary Operators
   - Rounding

9. [Control Statements](#control-statements)
   - Conditional Statements (if, else)
   - Loops (while, for, range-based)
   - Break and Continue

10. [Functions](#functions)
    - Function Declaration and Definition
    - Function Overloading
    - Passing by Reference and Value

11. [Data Structures](#data-structures)
    - Vectors
    - Sets and Multisets
    - Maps
    - Queues
    - Priority Queues
    - Arrays
    - Structures
    - Classes

12. [Macros and Typedefs](#macros-and-typedefs)
    - Defining Macros
    - Type Aliasing with typedef

13. [Random Numbers](#random-numbers)
    - Seed Initialization
    - Generating Random Integers and Doubles

14. [Best Practices](#best-practices)
    - Use of smart pointers
    - Error handling strategies
    - General coding practices

15. [Conclusion](#conclusion)
    - Summary of Key Points
    - Further Reading
## Input and Output <a name="input-output"></a>
Print to standard output:
```
std::cout<<_____<<std::endl;
```
The "std::endl" creates a new line after the printed output. 

Print statements can also be chained, e.g.:
```
std::cout<<_____<<_____<<endl;
```
To read a fundamental type from standard input:
```
int x;
std::cin>>x;
```
To read a string from standard input (need string header):
```
string x;
getline(std::cin,x);
```
## Comments
Single-line:
```
// _____
```
Multi-line:
```
/*
_____
*/
```
## The Standard Library
Use headers to add modules, e.g.:
```
#include <iostream>
#include <string>
#include <vector>
#include <sstream>
```
Alternatively, include the whole std library:
```
#include <bits/stdc++.h>
```
Modules can be used by, e.g.:
```
std::cout<<_____;
```
Alternatively, declare the std namespace (this will be assumed for the rest of these notes):
```
using namespace std;
```
Then to use std, e.g.:
```
cout<<_____;
```
## Data Types
Identifiers in c++, including variable names, must:
- Comprise only letters, digits, and underscores
- Begin with a letter
Common types:
- int (typically 4 bytes)
- float (typically 4 bytes)
- double (typically 8 bytes)
- char (1 byte)
- bool
- string
#### Modifiers
All number types can also be preceded by these modifiers:
- "unsigned" creates the same type with no negatives
- "long"
- "short"
#### Variables
Multiple variables of the same type can be declared together:
```
int x,y;
```
There are two ways to initialize a variable:
- c-like initialization:
```
int x=1;
```
- constructor initialization:
```
int x(1);
```
Multiple variables can be initialized to the same value by stringing together equals signs:
```
x=y=z=1;
```
A null type can be created by:
```
decltype(nullptr)
```
#### Strings
Strings are created using double quotes:
```
string s="Hello world";
```
Strings can be separated into multiple lines by including a backslash at the end of each line. 

To get a string's length:
```
int n=s.length();
```

To concatenate string literals, simply place them side by side or with only whitespace between:
```
string s="Hello " "world";
```
To concatenate strings using pointers, use "+":
```
string c=a+b;
```
To convert from string to int:
```
x=stoi(s);
```
#### Chars
Chars are created using single quotes:
```
char x='z';
```
To convert a char representing a digit or lowercase or uppercase letter to a number:
```
x-'0'
x-'a'
x-'A'
```
## Pointers
To declare a pointer:
```
[type]* [pointer-name];
```
Constant pointers: cannot be used to change the value that they point to:
```
const [type]* [pointer-name];
```
Null pointers can be created by "nullptr."
- Address-of operator:
```
a=&b;
```
- Dereference operator:
```
a=*b;
```
To declare a pointer to a variable whose size is unknown before execution, use:
```
[type]* [pointer-name]=new (nothrow) [type];
```
"(nothrow)" is optional and means that a null pointer will be returned if the declaration fails. 

This is followed by:
```
delete [pointer-name];
```
## Operations
#### Basic Math
- +
- -
- *
- ** exponent
- pow(x,y) (exponent can be floating-point)
- abs(x)
- ++ increment
- \-- decrement
When the increment\decrement operators are placed after a variable, the expression is evaluated before the increment/decrement operation. 
#### Boolean Operations
- && and
- || or
#### Bitwise Operations
- & and
- | or
- ^ XOR
- ~ invert
- << bit-shift left
- >> bit-shift right
Bitwise operations can also be placed before an equals sign to operate on the variable before the operator, e.g.:
```
x^=y; // equivalent to x=x^y;
```
#### Ternary Operators
```
[condition] ? [code if true] : [code if false];
```
#### Rounding
For printing (dec is the number of decimals to round to):
```
cout<<fixed<<setprecision(dec)<<x;
```
For saving value:
```
double x=round(y*pow(10,dec))/pow(10,dec);
```
## Control Statements
```
if (_____){
}
else if(_____){
}
else{
}
```

```
if (_____) _____ else _____;
```

```
while (_____){
}
```
For loops contain three expressions: the initializer, the break condition, and the increment. Each of these can contain multiple statements. The most basic for loop is:
```
for (int i=1; i<n; i++){
}
```
Range-based loops contain two expressions: a declaration and an object that is iterated over. A common use is:
```
for (int x : my_vector){
}
```
To escape from a loop:
```
break;
```
## Functions
Functions are defined by:
```
[return-type] [function-name]([arguments]){
	// function body here
}
```
Functions must include a return type, even if it is "void." The only exception is constructors, which have no return type. 

To allow a function to edit a variable, pass a reference by appending "&" to the variable type in the function declaration. 

Functions are called by:
```
[function-name]([arguments]);
```
The main function is defined by:
```
int main(){
}
```
## Data Structures
#### Vectors
To declare a vector:
```
vector<[type]> my_vector;
```
To initialize:
```
my_vector={1,2,3};
```
To initialize to all elements to the same value:
```
vector<[type]> my_vector(n,[value]);
```
To access a vector element:
```
x=my_vector[i];
```
To append to a vector:
```
my_vector.push_back([value]);
```
To access the last element:
```
my_vector.back();
```
To remove the last element (does not return anything):
```
my_vector.pop();
```
To get a vector's size:
```
my_vector.size();
```
To sort a vector:
```
sort(my_vector.begin(), my_vector.end());
```
To reverse a vector:
```
reverse(my_vector.begin(), my_vector.end());
```
#### Sets
There are two types:
- unordered_set (hashing)
- set (balanced BST)
To add to a set:
```
my_set.insert([value]);
```
To remove from a set:
```
my_set.erase([value]);
```
To find out whether an element exists in a set:
```
my_set.count([value]); // returns 0 or 1
```
To get a set's size:
```
my_set.size();
```
To access all the elements in a set:
```
for (auto it=s.begin(), it!=s.end(); it++){
}
```
If the set is not an unordered_set, this will return the elements in increasing order. 
#### Multisets
These work in the same way as sets, except they count how many times elements have been added to them. There are again two types:
- unordered_multiset
- multiset
To remove all instances of an element:
```
my_multiset.erase([value]);
```
To remove just one instance:
```
my_multiset.erase(my_multiset.find([value]));
```
#### Maps
There are two map types:
- unordered_map
- map
To create a map:
```
map<[key-type],[value-type]> my_map;
```
To create or edit a key-value pair:
```
my_map[[key]]=[value];
```
To access the value corresponding to a key:
```
my_map[[key]];
```
If a key that doesn't exist in the map is queried, it is created with a default value. 

To check if a key exists in a map:
```
my_map.count([key]);
```
To access all keys and values:
```
for (auto x : my_map){
	// use x.first and x.second
}
```
#### Queues
```
queue<[type]> my_queue;
```
To add to a queue:
```
my_queue.push([value]);
```
To access the front element:
```
my_queue.front();
```
To remove the front element:
```
my_queue.pop();
```
#### Priority Queues
```
priority_queue<[type]> my_pq;
```
To add to a priority_queue:
```
my_pq.push([value]);
```
To access the largest element:
```
my_pq.top();
```
To remove the largest element:
```
my_pq.pop();
```
#### Arrays
- built-in
- fixed length
Declare with type and size:
```
int my_array[10];
```
Initialize:
```
int my_array[3]={1,2,3};
```
Initialize to default:
```
int my_array[10]{};
```
Initialize to a chosen value:
```
int my_array[10]{1};
```
Access an array element:
```
x=my_array[i];
```
#### Structures
```
struct my_struct{
	[type] [variable-name];
	...
} my_struct1,...;
```
Structure properties are accessed by, e.g.:
```
int x=my_struct1.var1;
```
A structure's properties can be accessed with a pointer to the structure by:
```
int x=my_pointer->var1; // equivalent to (*my_pointer).var1
```
Structures are created by:
```
my_struct* my_struct1=new my_struct;
```
#### Classes
```
class my_class([arguments]){
	[type] [variable-name];
	...
	[functions];
	my_class([arguments]): var1([expression2]),...;
} my_class1,...;
```
Classes may be defined with several constructors with different arguments. If one of the constructors has no arguments, it is called the default constructor. 

Properties of classes are accessed in the same way as those of structures. Functions inside classes are called by:
```
my_class1.[function-name]([arguments]);
```
Classes are created by:
```
my_class* my_class1=new my_class([arguments]);
```
However, the default constructor must be called without parenthesis. 

Use blind replacement to define a name for block of code, so that the block of code will replace the name wherever it is later used:
```
#define [name] [replacement]
```
Use type aliasing to create a new name for a type:
```
typedef [original_name] [alias];
```
e.g.
```
typedef vector<vector<string>> str_vec;
```
An expression can include multiple statements separated by commas, and only the last statement will be used when the expression is evaluated. 
## Random Numbers
First, seed:
```
srand(time(NULL));
```
To generate a pseudo-random integer in the range \[a,b]:
```
int x=a+rand()%(b-a+1);
```
To generate a pseudo-random double in the range \[a,b]:
```
double x=a+(rand()/(double)RAND_MAX)*(b-a);
```
