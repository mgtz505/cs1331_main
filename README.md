GA Tech CS1331 - Introduction to Object-Oriented Programming with Java

Class Notes

# Module 1
## Lesson 1 - Intro to Java

### Basic Elements of Java Programs:

#### Methods
- Statements can be grouped together using a method
- A program must have at least one or more methods
- In order to be executable, a program must have a method called “main”
- Methods are enclosed in classes
- A program must have one or more classes

```
// simple program that prints text on the terminal:

public class HelloWorld { 
	public static void main(String[] args){
	System.out.println(“Hello World”)
	}
}
```
Anatomy of the above code:
```
public class HelloWorld -> Class Header
```
- Gives class a name
- Use CamelCase
- No Spaces
```
public static void main(String[] args) -> Starter of our method
```
By naming this method main, it’s special
The main method is automatically executed when you run a java program

#### Naming Java Files
- The file name must match the class declared in the file
- Ends in .java

#### Compilers vs Interpreters
- Takes a program written in a high-level language and translates it into a low-level version that’s either machine code or something close
- The two units of codes are functionally equivalent, just expressed differently 
- When the compiler performs the translation in one session and creates a new file, an interpreter translates the language on-the-fly
- Each individual expression is individually translated
- Compiled programs are generally faster; translate once
- Interpreters offer greater general platform independence 
- A programmer can write a program in an interpreted language and that code will run on any computer
- If using a compiled language, the dev would need to compile every written program to every kind of instruction set that exists

Java takes a hybrid approach to offer both compilation and interpretation. Its source code is not compiled directly to machine code like in C and C++.  Instead, a compiler generates what is known as bytecode and stores that in one or more files with a “.class” extension.
Bytecode is not fixed to a specific type of processor’s instruction set.  However, it comes close to the low level of machine code without making significant assumptions about the kind of processor that will run it. Once the bytecode for a Java program is generated, you can then actually run it using an interpreter that can translate the bytecode to the machine language of the particular processor of the target computer. 
-  Recall that interpreted languages tend to be much slower than compiled languages because they typically translate from high-level code down to low-level. 
-  However, with Java, since bytecode is already at a low-level, the translation costs are not as significant.
-  You’ll often find the Java interpreter being referred to as the Java Virtual Machine (or just JVM).  The “Virtual Machine” part of the name is derived from the fact that compiled Java code is not executed by a real processor. Rather a piece of software, the interpreter, performs the execution.

## Lesson 2 - Why Use OOP? A Brief Introduction

### Identifiers, Variables and other Syntax tidbits

#### Identifiers
Identifiers are names that programmers use to label classes, methods, variables and other elements
- Can contain letters, numbers, underscore and dollar sign
- A digit cannot be a starting_character
- Cannot use reserved words as identifiers
#### Variables
- Declaring a variable: <type> <identifier>
- Int: type that accommodates ~-2Bn -> 2Bn
- Java is statically typed; must declare a variable before you use it
```
//example:
int saturdayTemp;
saturdayTemp = 78;
```
- The type of a variable must be compatible with the type of value being assigned to it
- String Literals - Must be in Double Quotes!

### Intro to Object and OOP
- The attributes of an object collectively represent its state, and the actions make up its behavior
- Classes enclose a group of related methods
- A class can be a blueprint that defines a state and behavior or a kind of object using variables and methods
- Recall that each object will be created from a class (Each object has its own copy of the classes’ state variables)

So why use OOP?
- You can use code to model entities, concepts, and processes in ways that effectively simplify the tasks of building, maintaining and extending software
What is procedural programming?
- Recall that earlier we learned that a method groups related statements together.  So really, a program without classes, but built from well-crafted methods, still provides some level of structure
- However, a problem arises when you start to modify or even just read the code of large procedural programs.  There will be very many methods, and in some cases too many to search through. Classes, however, reduce that complexity by grouping not just statements but multiple methods and related data at a time.

## Lesson 3 - Back to Basics

### Whitespace
- Blanks / Tabs / NewLine characters
- Use to visually draw emphasis to portions off your code
- The compiler will ignore whitespace beyond separating words

### Errors
There are three types of errors a program can have
#### Compiler Error
- Typically syntax errors
- Code must be “legal” to be compiled; otherwise an error will be output to help resolve the syntax violation
- As you write more complex programs, fixing compiler errors may become increasingly difficult 

#### Runtime Error
- Example: divide by zero errors
- As with compiler errors, you’ll see an error message after the runtime error exists
- Message consists of a list of the statements and methods that were active when the error occurred. This is formerly known as a stack trace, and is helpful when you are writing programs with more than one method
- Runtime errors can occur for numerous reasons
- Example: a computer running a Java program may not have enough memory or other resources to finish execution, therefore it terminates early

#### Logical Error
- Error in a program’s semantics; the program will produce unwanted results
- Java doesn’t produce useful error messages for these errors
- I.e. in the F -> C conversion program, a C value  > F

The earlier you catch a logical error, the better!
- Recommend compiling code after each method and class written in a program
- Include comments in your code!

### Commenting in a Java Program
Java has three forms of comments to help document your code
- Line comments i.e. // 
- Block / Multi-line comments i.e. /* …text goes here... */
- Javadoc Comments

Remember all comments are ignored by the compiler and are used to to explain statements or whole blocks of code
	
What’s Javadoc?
- The final kind of Java comment is used by a tool called javadoc, which automatically comes with your Java installation. 
- javadoc scans your source code for certain comments and automatically creates nicely formatted HTML files that describe your code.  
- These comments start with /** (a forward slash and two asterisks) and end with */ (an asterisk and forward slash). 

### Variables and Constants
Recall that variables must be declared before being utilized
- Java is a statically typed language
Must also consider variable scope
- Scope represents the part of a program that the variable’s identifier can be used to refer to it (i.e. cannot find…)
- One method cannot see the variables that are declared inside another
- A simple rule to recall is that a variable scope is within the closest set of braces

Variable Identifier vs constant identifier
example:
```
final double  PI = 3.14159265359;
```
Use of final:
- It has different uses in Java.  One is to prevent a variable from being assigned a value after initialization. Such a variable isn’t a regular variable since it can only be assigned one value, so the term constant is used instead.  
- With final in front of the declaration, we now can say that PI is no longer a variable identifier.  It’s a constant identifier.

While variables and constants differ in how many times their values can change, they do share many similarities.  For example, they share the same scoping rules. So a constant’s scope is within the closest set of curly braces. Also, you can create a constant of the same types as with variables.

### Primitives
- There are eight total primitive types
- Byte, short, int, long, float, double, char, boolean

A note on floats / doubles:
- Like with the integer types, the greater the storage used by a floating point type, the wider the range. You'll also see that the additional storage allows the double type to offer about twice (or double) the precision as the float type.
- The double type is the default type for the floating point value
- Java will allow you to override some basic default types of numerical literals by appending a special letter describing the desired format to the end of the literal

Why multiple numeric types?
With long and double providing the widest range of values for integer and floating point values respectively, why have other numeric types? For example, why would anyone use a byte or short variable when a long variable provides such a wider range of allowed integers?

Similarly, why use a float instead of a double?  Well, in some cases it's important for your program to minimize its use of memory while running.  In this class, I’ll use the term memory to simply refer to mechanisms used by a processor to store a running program and its data.
- You might be writing a program that is to run on a machine or appliance that might not have the relatively large memory resources of a conventional computer or laptop. In such cases, picking the type with the smallest range, but still wide enough to fit the values you'll need is an efficient use of memory.  
- A microwave’s power level setting that ranges from 1 to 10, for example, could be stored as a byte variable.

### Char Type
- ASCII is a character set that grew to 256 due to a greater need for flexibility over time
- Includes upper/lowercase letters, digits, punctuation marks, the space character and some other special chars
- Java’s char type actually uses a superset of ASCII called the unicode character set
- Unicode contains 65,536 characters and includes symbols and letters from many languages 

To create a char literal, simply enclose a character in single quotes
- Recall double quotes are used in closed strings only

### Escape Sequences
- Consists of  two consecutive characters, which have a special meaning to the compiler
- First character is always a backslash, which alerts the compiler that the next character is to be treated differently from normal
- Second character is a descriptor of the character that you are actually trying to store / show
- \t = tab
- \n = newline
- \r carriage return
- \\ backslash
- \” for double quote

### Boolean
 - The boolean type has only two possible values: true or false. It can be useful when representing things that have two distinct states like whether a car is parked or not or if it's on or off
### Expression
- Expression is a combination of operators, operands or method calls in a single java statement
- Expression must evaluate to a single value

### Non-Integer Division
- Due to Java’s integer division rules, we must take an extra step when we need the decimal part of a quotient.  One way to keep it is to use a floating point value as either the numerator or denominator of an operation
9.0 / 2 = 4.5
9 / 2.0 = 4.5
9.0 / 2.0 = 4.5
ALTERNATIVELY:
Override the default typing of the 9 and/or 2 by appending an F or D so that at least one value is treated as a float or double, respectively.
To illustrate:
9D / 2 = 4.5
9 / 2D = 4.5
9D / 2D = 4.5

### Mixed-Type Operations
Promotion =  a type of data conversion Java performs when it needs to match the types of operands in an expression
- Promotion is performed for all of the binary arithmetic operators as needed
- An empty string + a non-string type will yield a string representation of that latter type

Assignemnt Conversion
- Like promotion, assignment conversion happens automatically
- However, conversion happens during a variable assignment rather than within an expression
- Error message: “incompatible types: possible lossy conversion from double to int”
- Lossy conversion loses information when a value is converted from one type to another

It turns out, however, that determining the legality of a possible assignment conversion is not based on the number of bits that are used to represent a value and the number of bits a variable can hold.  Instead, they are based on whether the range of numbers of the variable’s type can fit the range of numbers of the value’s type.   To gain a better understanding, let’s revisit the specific ranges of Java numerics primitive types

<img src="https://courses.edx.org/assets/courseware/v1/76320839ea08d2d031e8162dd6f6a387/asset-v1:GTx+CS1331xI+2T2021+type@asset+block/legal_assignment_conversions.png"/>
	
### Casting
- Explicit form of type conversion
- The cast operator is a set of parens around a target type
- The operator is placed in front of a value or expression whose type you want to convert

Example: (double)5/9
- This tells Java to treat the 5 as a double
- No 0.0 or D/d needs to be appended to that 5
- The 9 is promoted its double value to match the now casted 5
- As implied casting is performed before the division
- The cast operator has highest precedence in any other operator except parenthesis

## Lesson 4 - Using Predefined Classes
- Unlike primitives, classes can also provide methods for performing certain actions
- Since objects are  more complex than primitives, their data is stored in a separately managed part of memory called the heap
- So an object’s variables really hold an address to where the actual object is found in the heap
- The process of creating an object is called instantiation, which makes sense as a term since an object is really an instance of a class. Recall that a program can have many instances of a single class

To create an instance of a class, use the new operator
example :new ClassName (parameters)
- The new operator creates an object of the provided class and then calls a special method of the class called the constructor
- The constructor’s job is to initialize certain properties of the newly created object using provided parameters

### Invoking Methods of the object / an object
- Java Standard Library / Java API
- PrintStream is an example of one of these in-built methods
- Saying that a method has returned means that is has finished executing without error
- If an object can no longer be reached to invoke its methods or perform a function,
- Java will free up space by a process called garbage collection that will allow for better memory management

### Some String Methods
- A method’s signature consists of the method’s name and a representation of the type and position of each parameter as shown here

#### concat(String)
- Returns a new string that’s a calling string object concatenated with whatever str refers to
- Str is known as a formal parameter, which is another way of saying it’s a parameter that’s listed on the method header
- Just before Java begins executing the statements of any method, if that method
has formal parameters, the value of each actual parameter is copied and
then assigned to its corresponding formal parameter. This process is known as pass by value.

#### replace(char, char)
- As strings are immutable, a new string is returned

#### substring(int, int)
- The ints refer to the start and end string indices 
- Similar to slicing by index with python 

#### toLowerCase()
- Returns a new string that is the same sequence of chars, but uppercase letters are now lowercase
- Remember that given string immutability, the method is performed on a copy of the calling object, not the original
	
You've now seen examples of some core String methods.  Understanding those particular ones should provide you with a basis for using many more like: indexOf(), lastIndexOf(), toUpperCase(), and charAt(

To illustrate, the indexOf() method should (hopefully) be straightforward now that you have seen how String indices work. Fundamentally, the method performs a left to right search for a sequence of one or more characters within a String. If the sequence doesn't exist, then the method returns -1. Otherwise, it returns the index of the first occurrence of the sequence.  There are four versions of the method:
	
```
public int indexOf(String str)
public int indexOf(int char)
public int indexOf(String str, int fromIndex)
public int indexOf(int char, int fromIndex)
```
Why are strings immutable?
- As you just saw, this property of Strings requires a bit of extra work (i.e., an explicit re-assignment) when we want to change the actual String we’re invoking a method on.
- It turns out, however, that there are significant security and performance benefits that are realized by making String immutable. The specific details are beyond the scope of this class.  
- However,  let's briefly think about security from a high-level perspective by considering that data like usernames, passwords, and other sensitive values are often stored as Strings.  Also, the JVM also stores the names of classes it will load during execution as String values.
-  Imagine if it were easy to dynamically change the contents of such values at runtime.  It could allow, for example, some untrustworthy code to cause the JVM to load unintended classes at a given time.  In the former example, such code could similarly change a valid password value to an invalid one to maliciously prevent a user from accessing parts of a program

## Lesson 5 - Input and Output
	
### Scanner
- To read in terminal input, we’ll use a class in the API called Scanner. The class was introduced to the API in version 1.5 of Java. It adds an easier to use method for basic terminal input processing than what the original Java API provided.
- The first step to using Scanner is to create an object as shown in the main method below:

```
public class FahrenheitToCelsius {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in); //read keyboard input
    }
}
```
- This single Scanner object will ultimately handle all of the inputs for our program, which will incrementally grow in size throughout this lesson. 
- We're calling the object input to represent what we’re going to do with it (i.e., read input), but as you’ve learned, variable names are up to the programmer
- A Scanner object can read data from multiple kinds of sources, and the object passed into the constructor represents a particular source 
- With System.in as input, the constructor customizes the created object so that it can read the ordered stream of characters entered on the keyboard 
- This stream of data is internally managed with a combination of hardware and software so that it correctly flows from a producer to a consumer 
- The particular stream that connects computer programs to the data from the keyboard is called the standard input stream (or simply standard in) since every program is automatically assigned one as a built-in means to receiving data. 
- You can direct other devices and sources to standard in, but that’s beyond the scope of this course.

With content in the stream, we can use the Scanner object's methods to read chunks of data for processing. These chunks are formally called tokens, and there are different methods that represent the different types of tokens we can read. For example, there’s a nextInt method for reading the immediately available int value from the stream.  As shown below, that int value would be 78.

To actually break a sequence of characters into tokens, the Scanner needs a representation of boundaries between tokens.  Such boundaries are defined by a particular sequence of characters called a delimiter. 
- By default, Scanner uses whitespace characters as delimiters, but you can change that if needed.
- Recall that whitespace includes the space, tab, and newline characters. Given the data below, the tokens are 78, long, and walks, as highlighted in orange:
```
78 long\nwalks\n
```
How these tokens are represented once they are read ultimately depends on which method you use.  The nextInt method described earlier would, for example, convert a token to an int value.
- As you might guess, an error occurs if the next available token in a stream is not a sequence of characters that can be represented as an int.

Each method for reading and returning data is prefixed with the word “next”, and there are several.  Here, we’ll focus on the ones that return tokens as numeric or String values, namely: nextInt, nextDouble, next, and nextLine. By learning these four, you will be able to immediately use several others like nextBoolean and nextFloat.

The nextInt and nextDouble methods read individual tokens and return them as ints and doubles respectively. The next() method reads a token and returns it as a String value.  Finally, nextLine() also returns a String, but it keeps pulling characters from the stream until it reaches a new line character. The characters that are read before the terminating newline are stored in the String, but the newline character is pulled and discarded.  You’ll see more of this with a coding example:

```
import java.util.Scanner;

public class NewDegreeConversion {
    public static void main(String[] args){
        Scanner input = new Scanner(System.in);
        System.out.print("Enter a Fahrenheit value: ");
        int fahrenheit = input.nextInt();
        double celsius = (5.0/9) * (fahrenheit - 32);
        System.out.println("Celsius: " + celsius);
    }
}
```
nextInt method skips any leading whitespace when scanning for tokens.  This rule, in fact, applies to all Scanner next methods except nextLine, which includes them in the returned String.

#### Scanner Errors
- When running a program that uses a scanner object, be careful not to enter in values
that are not supported by the particular next method that you're using
- Scanner has methods for peeking into a stream without actaully pulling tokens
- Utilizing these methods requires conditional statements

### Multiple Tokens Per Line
The examples you’ve seen so far have expected a single token response for each prompt.  It is, however, possible for each line of user input to be broken into multiple tokens.

Here’s a program that prompts the user to enter both temperature and day of the week on the same line
```
import java.util.Scanner;
public class FahrenheitToCelsius {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter a Fahrenheit value and the day of the week: ");
        int fahrenheit = input.nextInt();
        String day = input.next();
        double celsius = (5.0/9) * (fahrenheit - 32);
        System.out.println(day + " Fahrenheit: " + fahrenheit);
        System.out.println(day + " Celsius: " + celsius);
    }
}
```
Output:
```
Enter a Fahrenheit value and the day of the week: 78 Monday
Monday Fahrenheit: 78
Monday Celsius: 25.555555555555557
```
If the program had called nextLine instead of next, the leading space and “Monday” would be stored in day. Here's that version:
```
import java.util.Scanner;
public class FahrenheitToCelsius {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter a Fahrenheit value and the day of the week: ");
        int fahrenheit = input.nextInt();
        String day = input.nextLine();
        double celsius = (5.0/9) * (fahrenheit - 32);
        System.out.println(day + " Fahrenheit: " + fahrenheit);
        System.out.println(day + " Celsius: " + celsius);
    }
}
```
The last two lines of the program’s output would then be indented due to that space that is included in day as shown below:
```
Enter a Fahrenheit value and the day of the week: 78 Mo
nday
Monday Fahrenheit: 78
Monday Celsius: 25.555555555555557
```
We can remove any leading spaces (and trailing spaces if any) by directly calling the String method trim on the output of nextLine with a statement like this:
	
```
String day = input.nextLine().trim();
```

### More on Packages
Classes can be grouped together based on the functions they provide.  These groups are officially called packages and each has a name.
-  For example, System, String, and a long list of many other classes are in a package called java.lang.
- They are all grouped together because they are considered fundamental to the language, and for that reason, you do not have to insert any special lines in your code before using them.
- Other classes that are not in the java.lang package, however, require an import statement to help the compiler match a class’s name with its actual definition.  For example, Scanner, Timer, and Stack are all members of the java.util package and must therefore be imported. The java.util package offers several utility classes that will come in handy as you explore Java further.
	
Here’s the template to use for import statements:
```
import packageName.memberName;
```
So for Scanner, use:
```
import java.util.Scanner
```
The two packages “util” and “lang” branch off the same top level package of “java”. The “java” package is the most common in the Java API, so expect to frequently see it as we continue exploring more classes. Together, the package and member name (e.g., java.util.Scanner) represent what’s known as the fully-qualified name of a package member. Instead of using that name in the import statement, you could just enter an asterisk in place of the member name as shown atop here:
```
import java.util.*;
public class FahrenheitToCelsius {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter a Fahrenheit value: ");
        int fahrenheit = input.nextInt();
        System.out.println();
        double celsius = (5.0/9) * (fahrenheit - 32);
        System.out.println("Fahrenheit: " + fahrenheit);
        System.out.println("Celsius: " + celsius);
    }
}
```
- The asterisk represents a wildcard, which means that all members of the java.util package are imported.  It is helpful in cases when there are several members of a package that need importing. 
- For example, if you need Scanner, Stack, Timer, and other util package members in a program, it would be easier to just write a single wildcard-based import statement instead of multiple (for each member).
- Be careful when using wildcards, however, since it is possible to have two different packages that share the name of a class but provide their own definitions
- As a final note, it’s important to also mention that using the wildcard to import all members of a package versus using their fully-qualified names does not mean your programs are going to get bigger or anything of that nature.  
- There may be some additional overhead during compile time from not being specific, but there’s none when it comes to runtime.  The same bytecode is generated either way.
	
### Formatting with Printf
- To shorten the long trail of decimal values and to perform many other kinds of formatting on terminal output, there are a few options. One of these is the printf (or print formatted) method.
- Like print and println, it’s is another printing method that you can invoke with the System class’s out object.  
```
System.out.printf(formatString, value(s));
```
Notice that the method can accept more than one parameter unlike print and println, which only take a single parameter representing the String to print.

- The first parameter of printf is a format string, which is a String that represents the format of the output to print.  Use it to create the representation by combining the fixed parts of the output with special sequences called format specifiers.
- These sequences serve as place holders for the non-fixed parts of the output and define any styling that needs to be applied before printing
- The remaining parameters of printf represent the values that will be inserted into placeholders that are marked by the format specifiers.
	
To better understand, consider this println statement from FahrenheitToCelsius.java:
```
System.out.println(day + " Celsius: " + celsius);
```
The fixed part of the input to println is " Celsius: "  and the non-fixed parts are day and celsius since they are variables.  Here’s a matching printf statement:
```
System.out.printf("%s Celsius: %f\n", day, celsius);
```
Here, %s and %f are format specifiers holding the place for day and celsius, respectively. Here’s a template for constructing one:
```
%[flag][width][.precision]type
```
- It must start with a % to alert the compiler that the specifier is not part of the literal string.  If you ever want to print the actual % sign as part of the literal string in printf, you must use two % signs; i.e., “%%” 
- The template fields in square brackets (flag, width, and precision) are optional but important as you’ll see in a bit. The type field (also called the conversion) is required however. It represents the type of data that will be inserted and possibly formatted.

We can now revisit this printf statement:
```
System.out.printf("%s Celsius: %f\n", day, celsius);
```
Based on the type field, we can say that day is a String and Celsius is either a float or double. Notice the newline character at the end of the format string: "%s Celsius: %f\n". It’s there because, like the print method, printf does not automatically insert a newline after printing. If you do not wish to move the cursor to the next line after printing, simply omit the newline at the end of the format string.

After the format string parameter, you must enter the actual parameters in the order that printf will use to fill the places held by the format specifiers.  So, the type order of these parameters must be compatible with the type order of the format specifiers in the format string.
	
We’ve only touched the tip of the iceberg when it comes to printf’s flexibility.  Let’s say there’s a really cold day with Celsius values in the negative thousands (pun intended):
```
Enter a Fahrenheit value: -888999000
Enter a day of the week: Monday
Enter your preferred Celsius label: Celsius
Monday Fahrenheit: -888999000
Monday Celsius    -493888351.1
```
Such output might be enhanced with thousands-separators as shown here:
```
Enter a Fahrenheit value: -888999000
Enter a day of the week: Friday
Enter your preferred Celsius label: Celsius
Friday Fahrenheit: -888999000
Friday Celsius    -493,888,351.1
```
For this option, all that’s needed is a comma flag in the celsius variable’s format specifier as highlighted below:
```
import java.util.Scanner;
public class FahrenheitToCelsiusPrintf {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter a Fahrenheit value: ");
        int fahrenheit = input.nextInt();
        System.out.print("Enter a day of the week: ");
        String day = input.next();
        System.out.print("Enter your preferred Celsius label: ");
        String cText = input.next();
        double celsius = (5.0/9) * (fahrenheit - 32);
        System.out.printf("%s Fahrenheit: %d\n", day, fahrenheit);
        System.out.printf("%s %-10s %,.1f \n", day, cText, celsius);
    }
}
```
#### String.format
By learning printf, you’ve also learned how to use the String class’s format method.  It works just like printf except it doesn’t actually print the final formatted String on the terminal. Instead, the method returns the formatted String value, which you could then store in a variable for example.
```
String celsiusOutput = String.format("%s %-11s %,.1f \n", day, cText, celsius);
```
 Given the same inputs from that same example, celsiusOutput becomes a reference to this String:
```
"Friday Celsius    -493,888,351.1"
```
### Number Formatting
Refer to the following:
```
import java.util.Scanner;
import java.text.NumberFormat; 

public class CurrencyDemo {
    public static void main(String[] args) {
        int items;
        double itemCost, total;
        Scanner input = new Scanner(System.in);
        System.out.print("Enter the number of items: ");
        items = input.nextInt();
        System.out.print("Enter the cost per item: ");
        itemCost = input.nextDouble();
        total = items * itemCost;
        System.out.println();
        System.out.println("Unformatted Total: " + total);
        NumberFormat currencyFormat = NumberFormat.getCurrencyInstance();
        System.out.println("Formatted Total: " + currencyFormat.format(total));
    }
}
```
With some thinking, currency formatting could be done with printf, but the NumberFormat did it well with very little work.  All that was needed was to create an object and call a method.

NumberFormat is also quite special with its support for internationalization.  Meaning that its objects’ behaviors can change based on the geographic location of the computer in which they are created. 
- Running the same program with similar inputs on a computer in France could yield this\\
```
Enter the number of items: 3
Enter the cost per item: 12.3456

Unformatted Total: 37.0368
Formatted Total: 37,04 €
```
Java allows you to manually specify a location using a class in the java.util package called Locale. There, you’ll find several constants representing different countries and regions that you can pass into the getCurrencyInstance method.  Here’s a version of the program using Locale.FRANCE:
```
import java.util.Scanner;
import java.util.Locale;
import java.text.NumberFormat;

public class CurrencyDemo {
    public static void main(String[] args) {
        int items;
        double itemCost, total;
        Scanner input = new Scanner(System.in);
        System.out.print("Enter the number of items: ");
        items = input.nextInt();
        System.out.print ("Enter the cost per item: ");
        itemCost = input.nextDouble();
        total = items * itemCost;
        System.out.println();
        System.out.println ("Unformatted Total: " + total);
        NumberFormat currencyFmt = NumberFormat.getCurrencyInstance(Locale.FRANCE);
        System.out.println ("Formatted Total: " + currencyFmt.format(total));
    }
}
```

### Decimal Format
Another useful number formatting class in the java.text package is DecimalFormat.  It’s quite flexible by giving you the power to specify your own patterns or templates for how formatted numbers should look. 

Here’s an example instantiation of a DecimalFormat object, and as shown, the instance can be initialized with a desired pattern:
```
DecimalFormat formatter = new DecimalFormat("0.0");
```
Patterns look like numbers in the format of a String literal, which makes sense since they describe how actual numbers should appear after formatting.
Here’s how to interpret the above pattern or any other pattern with only zeros and a decimal point:
- A digit 0 in some pattern’s position guarantees that there will be a digit (not necessarily 0) in that same position for any formatted result.
- If the number being formatted has an actual digit in the same position of some 0 digit in the pattern, then that number’s digit will be shown in that position in the formatted result.
- If the number being formatted does not have a digit in the same position of some 0 digit in a pattern, the formatted result will fill that position with an actual 0 digit.  
- If there are more decimal places in the number being formatted than found in the pattern, the formatted result will round that number to a value with the same number of decimal places as specified in the pattern.

To apply a pattern on a number to get a formatted (String) result, simply call the format method on a DecimalFormat object, with the number as input:
```
String formattedNum = formatter.format(.8675309);

```
Here’s a program that uses the above pattern and other zero-based ones to illustrate the above rules:
```
import java.text.DecimalFormat;

public class DecimalFormatDemo {
    public static void main(String[] args) {
        DecimalFormat formatter1 = new DecimalFormat("0.0");
        DecimalFormat formatter2 = new DecimalFormat("00.00");
        DecimalFormat formatter3 = new DecimalFormat(".00");
        DecimalFormat formatter4 = new DecimalFormat("0.00%");
 
        System.out.println("0.0: " + formatter1.format(.8675309));
        System.out.println("00.00: " + formatter2.format(.8675309));
        System.out.println(".00: " + formatter3.format(.8675309));
        System.out.println("0.00%: " + formatter4.format(.8675309));
        System.out.println(".00: " + formatter3.format(8675309));
    }
}
```
The last two lines illustrate a couple of additional rules:

- If a percent sign is found at the end of a pattern, the format method will return a percentage value that represents the input
- The number of zeros to the left of a decimal point in a pattern do not constrain the number of digits that the format method will use from its input value.

There are other pattern symbols that you can use besides 0 and %.  For example, the # (pound/hash) symbol allow you to write patterns with optional digits. Here’s an example:

```
DecimalFormat formatter = new DecimalFormat("#.00");
String numStr = formatter.format(.8675309);
System.out.println(numStr);
```
Output: 
```
.87
```
Since the format method’s input value is less than 1 and the pattern specifies the whole number digit is optional, there’s no zero to the right of the formatted result.
