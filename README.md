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




