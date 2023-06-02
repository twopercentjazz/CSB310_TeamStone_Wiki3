# Team Stone Wiki 3 - Programming Languages Deep Dive C#

C# is an advanced, flexible, and influential programming language engineered by Microsoft. As an integral component of the .NET framework, it delivers a sturdy foundation for creating diverse applications across web, desktop, mobile, and gaming platforms. Within this Wiki, we will delve into several crucial topics that enrich your comprehension of C# and its vast capabilities.

### Data Types (Chapter 6)  - Chris
### Expressions (Chapter 7) - Chris
### Assignment Statements (Chapter 7) - Yen

In C#, assignment statements play a fundamental role in programming as they allow you to assign values to variables and modify their contents. An assignment statement typically consists of an expression on the right-hand side (RHS) and a variable or a memory location on the left-hand side (LHS), separated by the assignment operator (=).

The assignment operator (=) in C# is used to assign a value to a variable. The value on the right-hand side of the assignment operator is evaluated and then stored in the variable on the left-hand side [Y1]. For example:

int x = 10;

In the above example, the integer variable x is assigned the value 10. The assignment statement sets the value of x to 10, allowing you to later use the variable in computations or for other purposes.

C# supports various types of assignment statements: simple assignment, compound assignment, multiple assignment, and increment and decrement. Simple assignmentis the most basic form of assignment involves assigning a value directly to a variable, as shown in the previous example. In compound assignment, C# provides operators that combine an arithmetic operation with the assignment operation. These operators perform the arithmetic operation and then assign the result to the variable [Y1]. For example:

int x = 5;
x += 3;  // Equivalent to x = x + 3
In this case, the value of x is incremented by 3 using the compound assignment operator +=.

In multiple assignment, C# allows you to assign values to multiple variables in a single assignment statement. This can be done using comma-separated expressions on the right-hand side. For example:

int a, b, c;
a = b = c = 10;  // Assigns the value 10 to all variables
In this case, the value 10 is assigned to variables c, b, and a in a cascading manner.

Finally, C# provides increment (++) and decrement (--) operators, which are often used for modifying the value of a variable by one. These operators can be used both as prefix and postfix. For example:

int count = 0;
count++;  // Increment count by 1
In this example, the value of the variable count is incremented by 1.

Assignment statements are essential in programming, allowing you to store values in variables, update them, and manipulate data throughout the execution of a program. They form the backbone of data manipulation and play a crucial role in controlling the flow and behavior of programs written in C#.

### Statement-Level Control Structures (Chapter) - Michael
### Subprograms (Chapter 9 and 10) - Riko
### Abstract Data Types and Encapsulation Concepts (if there are any) (Chapter 11) - Riko
### Object-Oriented Programming (Chapter 12) - Yen

Object-oriented programming (OOP) is a programming paradigm that organizes code around the concept of objects, which are instances of classes. Objects encapsulate data and behavior together, allowing for the creation of reusable and modular code. C# provides a rich set of features that facilitate the implementation of OOP concepts.

Classes are fundamental building blocks in C#. They serve as blueprints for creating objects and define their properties and behaviors. By defining classes, you can create multiple instances of objects with similar characteristics and behaviors. This promotes code reusability and allows for a more efficient and organized approach to programming [Y2].

Inheritance is another important aspect of OOP supported by C#. It allows you to create new classes based on existing ones, inheriting their attributes and behaviors. This mechanism enables code reuse and promotes the concept of hierarchy, where more specialized classes inherit properties and methods from more general ones. Inheritance facilitates the creation of more flexible and scalable applications [Y2].

Polymorphism is yet another key feature of object-oriented programming that is well-supported in C#. It allows objects of different classes to be treated as objects of a common base class. Polymorphism allows for more flexibility in designing and implementing systems, as it allows different objects to respond differently to the same method call. This promotes code extensibility and enhances the modularity of applications [Y2].

Encapsulation is an important principle of OOP that focuses on hiding the internal details of an object and exposing only necessary information through well-defined interfaces. C# provides access modifiers like public, private, protected, and internal to control the visibility and accessibility of class members. Encapsulation enhances code maintainability and reduces the impact of changes made to the internal implementation of an object [Y2].

C# also supports other essential OOP concepts such as abstraction and association. Abstraction allows you to represent complex systems by simplifying and focusing on essential aspects, while association enables the relationship between classes and objects to be defined.

By providing these powerful features and supporting key principles of object-oriented programming, C# enables developers to write clean, modular, and reusable code. It allows for the creation of robust and scalable applications, promotes code organization, and facilitates collaboration among teams of developers. C# has become a popular choice for software development, especially in the Microsoft ecosystem, due to its rich OOP capabilities and extensive support from the .NET framework.

### Exception Handling and Event Handling (Chapter 14) - Michael


## Simple program


References:

[Y1] “Assignment operators - assign an expression to a variable,” Assignment operators - assign an expression to a variable | Microsoft Learn. [Online]. Available: https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/assignment-operator [Accessed Jun. 1, 2023]. 

[Y2] “Object-oriented programming (C#),” Object-Oriented Programming (C#) | Microsoft Learn. [Online]. Available: https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/tutorials/oop#:~:text=C%23%20is%20an%20object%2Doriented,abstract%20representation%20of%20a%20system. [Accessed Jun. 1, 2023]. 

