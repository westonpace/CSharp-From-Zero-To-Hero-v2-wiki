# C# Keyword and User Input

## Every program in a nutshell

A program is simply a set of instructions that get compiled and converted to machine code, which then are executed and put to use to solve a specific problem. Instructions essentially are functions (actions) and variables (data).

In C#, every instruction is terminated with a semicolon (;). There can be multiple instructions in the same line, but it's not very readable and by convention, we stick to a single instruction per line.  

## Visual Studio

Visual Studio is an IDE (integrated development environment), which provides a developer with all the needed tools to do their job: code editor, debugger, code runner, compiler, etc...
[[/images/Chapter1/Lesson1/Solution.png]]
In the image above you see a view that will show up on the right side (by default) when you open your first Visual Studio project. In .NET, a solution (marked as 1 in illustration) is a container for all files needed that your program is made of. Solution doesn't contain files for your program by itself- that is done by projects. Solutions are made of projects (marked as 2 in illustration).  Project is like a module (or a layer) for a full program, which provides functionality for some part of it. Projects are made of different files, but for now, we will focus .cs file. For code to be compiled as C# code, it needs to be put in .cs files (marked as 3 in illustration).

### How to run an application?

[[/images/Chapter1/Lesson1/Run.png]]
To run an application, we first need an executable type of project. The most simple type of executable is a console application. Every executable program needs to have a starting point. In a console application, that starting point is the Main function. To run it, you first need to select a project you want to run (marked as 1 in illustration) and hit the run button (marked as 2 in illustration). As an alternative to run button, you can press F5.  

## Variables

Variables are essentially data. It's hard to imagine a program which could exist without any. For a variable to be meaningful, it needs to have 3 things:  
* Type- what kind of data can a variable hold? There are 3 primitive variable categories: numbers, text and logical.
* Name- how will we refer to a variable? Can only be made of [aA-zZ], _, @, [0-9]. 
* Value- what data does the variable hold?   
You can declare a variable without a value, but C# compiler won't let you use it, because it has no value (is not initialized). Example of such error can be seen in the image below.  
[[/images/Chapter1/Lesson1/undefined.PNG]]

### Numbers

Number types are divided into two groups. Whole numbers and numbers with a fraction.

#### Whole numbers
| Type     |   Bits  |  Min value             |      Max value     :|
|----------|:-------:|-----------------------:|--------------------:|
| byte     |    8    |         0              |      255:           |
| short    |    16   |      -32 768           |    32,767           |
| int      |    32   |    -2 147 483 648      |  2 147 483 648      |
| long     |    64   |    -9x10<sup>18</sup>  |  9x10<sup>18</sup>  |


Default is int.  

Note: Most whole number types have unsigned versions of them, which double their size. For example, short is 32 767 max value, but ushort is 65 535, however, min value of ushort is 0 (no negative).

#### Floating point numbers (numbers with fraction)

| Type     |   Bits  |  Value                                              |   symbol  :|
|----------|:-------:|----------------------------------------------------:|-----------:|
| float    |    32   |  ±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38<sup>   |     f      |
| double   |    64   |  ±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup>  |     d      |
| deciaml  |    128  |  ±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup>  |     m      |

Default is double.  

Note: if you want to declare a variable as float or decimal, you will need to explicitly say so by either:  
A: using type symbol ``float f = 2.0f;``  
B: casting ``float f = (float) 2.0;``  
*Important*: for money or scientific calculations use decimal.  

### Text

char- is a single symbol.
To store a char use single quotes ('').

`char myChar = 'a';`

string- is many symbols. To store a string use double quotes ("").

`string myStr = "Joe#2020";`

Note: you cannot store an empty character (''- won't compile), but you can store an empty string.

### Logical

bool is a logical type. It can be either true or false. Logical variables drive logical statements, but about that in later lessons.

## Arithmetics

### Addition results

| Type1    |   Type2 |  Result type   |
|:--------:|:-------:|:--------------:|
| byte     |   int   |      int       |
| char     |   char  |      int       |
| char     |   int   |      int       |
| string   |  string |    string      | 
| string   |   char  |    string      |
| string   |   long  |    string      |

Note: subtraction is identical, except that we cannot one string from another.  
Note: adding two values of different types will store the result in type with bigger space. This is done to avoid buffer overflow.

### Division & Multiplication

Both are trivial and applicable only to number types.  
Dividing number you should pay attention because you if divide from the higher number, the result will be 0.  
For example: ``1/2=0``.  
If we want the result to be 0.5, all we need to do is to add a fraction to either of the numbers when dividing.  
Like so: ``1/2.0=0.5``.
  
Like in normal maths, division from 0 is impossible. Also, division and multiplication has priority over addition and subtraction.

## Console

Console is the minimum kind of display for printing data. All the functions that console are exposed under ``System.Console`` class.

### Write

To write text to console, all you have to do is ``Console.Write("My text");``  
To write a line of text to console, all you have to do is ``Console.WriteLine("My text");``  
The printed text will appear without "" because the quotation marks are used to have a distinction between code and text, but such distinction is no longer needed when printing text.  
Note: if you type ``cw`` in code editor and press tab, it will autocomplete the snippet with ``Console.WriteLine();``

### Read
We can read user input in many different ways, but for now, we will focus on the most simple one- ``Console.ReadLine();``. This will try to read a line of text that a user typed and pressed enter. For example ``string name = Console.ReadLine();``.

### var keyword
You don't have to always explicitly declare a variable with a type. It might get tedious sometimes, especially when types get more complex and long. Sometimes we either don't care about a type or it's extremely obvious what the type is. By convention, in most cases, we use ``var`` to define a type. For example: ``var name = "Kaisinel;". Type of name, in this case, will be string. Compiler is smart enough to know the type in most cases and when it doesn't, you will have to hint it with explicit types, casting or other...

Note: ``var`` doesn't make C# loose strong-typed language features. If you hover over ``var`` in IDE, you will still see the actual type.
___

## Homework

Read name, surname, age, weight (in kg) and height (in cm) from console.
1) Print all the info based on the example message below:
```
Tom Jefferson is 19 years old, his weight is 50 kg and his height is 156.5 cm. 
```
2) Calculate and print body-mass index (BMI)
3) Do 1 and 2 for another person.

## How to do your initial setup for Visual Studio

https://youtu.be/Zm0bNCrfUvw