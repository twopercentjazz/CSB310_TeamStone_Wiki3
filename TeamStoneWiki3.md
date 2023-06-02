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

### Statement-Level Control Structures (Chapter 8) - Michael
In many scenarios someone writing code will want some way to repeat the same block over and over because what they have written may need to occur multiple times. For example, suppose we want to search a Microsoft excel document that is thousands of rows tall and hundreds of columns wide for a value we know is there but are uncertain where. Writing individual expressions to search the document cell by cell would probably take longer than simply manually searching the document ourselves and the code file's size we write may also exceed the document it's programmed to search. With each cell along the way we would want to evaluate the data and determine if it's the value we are looking for or not. In computer programming languages such repetitious behavior and decision making branches are refered to as control statements. The collection and organization of control statements is called a control structure[ml1].

C# offers traditional selection, multiple selection, interative and unconditional branching control statements and oftentimes updated for readability compared to their counterparts in other languages.

### Selection:
A selection control statement allows code to branch multiple ways depending upon the evaluation of data. C# offers the if-then-else-end selection statement found in many other languages but the then and end reserved words are removed. Take this code sample for example;

if (shouldContinue == true){
	DoSomething();
}
else{
	//A different block of code...
}

in this example whenever the code reaches the if statement the boolean expression  ```shouldContinue == true``` is evaluated. If the value of ```shouldContiue == true``` is true then the DoSomething function within the curley braces following the checked condition is called. If ```shouldContinue == true``` evaluted to false then code within the curley braces following the else reserve word is executed instead.

### Multiple-Selection
In C# multiple-selection can be done with switch statements and if-elseif-else. Unlike other C based languages that feature switch selection, C# enforces a ```break``` or ```goto``` statement within each case[ml2]. 


	switch (color)
        {
            case "red":
		        Console.WriteLine("Color is red");
            case "green":
                Console.WriteLine("Color is green");
                break;
            case "blue":
                Console.WriteLine("Color is blue");
		        break;
            default:
                Console.WriteLine("not a valid color");
                break;
        }

In this example the compiler will produce an error because the ```"red"``` case does not break or goto one of the other cases. This also applies to the default case. 

C#'s switch statement supports all numerical types(including ```enum``` and ```char```), strings and boolean values. C# also includes something known as a 'Case guard'. By using the ```when``` keyword you can allow a boolean expression check before the case's value is checked. 

	string color = "red";
        bool safe = false;
        switch (color)
        {
            case "red" when (safe == true):
                Console.WriteLine("Color is red");
                break;
            case "green":
                Console.WriteLine("Color is green");
                break;
            case "blue":
                Console.WriteLine("Color is blue");
                break;
            default:
                Console.WriteLine("not a valid color");
                break;
        }

In this example the ```"red"``` case would not be accepted and the switch would evalutate to the default because the guard statement ```(safe == true)``` would not evaluate to true. A similar effect could be achieved in other languages without safe guards by simply adding an ```if``` statement before the contents the case block. This approach reduces the number of lines necessary and prevents the need for the additional nesting in the control statement. Although, C# does support nesting your selection statements as deeply as you would like.

### Iterative Statements
C# like many other languages supports iterative statements, which are usually refered to as loops. The purpose of the loop is to execute the same block of code numerous times while also determining if the looping behavior needs to continue(In many cases this also includes keeping track of how many times the loop has iterated). C#'s for loop syntax is practically identical to other C style languages. Take the most classical loop structures for example; the ```for-loop```

    int[] intArray = {1,2,3,4,5,6,7,8,9,10};
    for(int i = 0; i < 10; i++){
	    Console.WriteLine(intArray[i]);
    }

In this example the semicolon separated expressions within the parenthesis are known as loop parameters. The first one being the loop variable or "initializer" where the iterative steps/progress value is stored. The second is the terminal or "for condition", which determines if the loop continues and is evaluated once before each iteration in the loop including the first. And lastly is the iterator, which updates the value of the loop variable after each loop iteration[ml3]. It is important to note that for loops typically use numerical values but C# supports non numerical values and function calls for the loop parameters should you desire;

	    int number = 13;
        for(bool isEven = false; isEven == false; isEven = isNumEven(number))
        {
            Console.WriteLine("looping to hit even number");
            number++;
        }

In this example our initializer is a boolean variable and the iterator is an assignment an a call to a seperate function that may have any amount of code that will be executed at the end of each iteration.

### Unconditional Branching
In control structures unconditional branching statements refers to statements that direcct code execution to specific locations without the conditional checks you would find in an ```if``` or ```switch``` statement. Though this feature can be very useful it's often regarded as dangerous since it can make programs hard to read[ml1]. C# offers this feature but has scope limitations that prevent the code path from breaking out of the scope the branch was encountered. Here is a valid usage of C#

	loopRestart: // goto leads back here
    for(int i = 0; i < 10; i++)
    {
        Console.WriteLine(i);
        for (int j = 0; j < 10; j++)
        {
            goto loopRestart;
        }        
    }
    
In this example the looping structure repeats infinitely. Once the inner loop begins it encounters the goto statement, which causes the code path to leave both loops and where it resumes execution at the loopRestart: statement just before the first loop.

If we attempt to put the loopRestart: statement someplace else in the code that is out of the goto statement's scope it will result in a compiler error. This is an example that will generate the error:

	for(int i = 0; i < 10; i++)
        {
            Console.WriteLine(i);
            for (int j = 0; j < 10; j++)
            {
                goto loopRestart;
            }        
        }

    for(int i = 0;i < 10; i++)
    {
        loopRestart: //cannot reach this branch via the goto statement
        Console.WriteLine(i);
    }

ml1 : textbook
ml2 : offical docs https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/tutorials/branches-and-loops-local
ml3 : https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/statements/selection-statements

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

