# Java And OOPS CONCEPT in Java (15/09/25) 


# Java Basics
1. What is Java?

High-level, Object-Oriented Programming Language.

Developed by James Gosling (1995, Sun Microsystems).

Famous for “Write Once, Run Anywhere” → compiled into bytecode, runs on JVM (Java Virtual Machine).



---

2. Features of Java

1. Platform Independent → Same program runs on Windows, Linux, Mac because of JVM.


2. Object-Oriented → Focuses on objects, not functions.


3. Simple & Secure → No pointers, automatic memory management.


4. Robust → Strong error handling & garbage collection.


5. Multithreaded → Supports multiple tasks at the same time.


6. Portable → Compiled into .class files (bytecode).




---

3. Java Program Structure


class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
} 


class Hello → Every program is inside a class.

main() → Entry point of the program.

System.out.println() → Prints output.



---

4. Data Types in Java

Primitive Types (8 total):

Integer types → byte (1 byte), short (2 bytes), int (4 bytes), long (8 bytes).

Floating point → float (4 bytes), double (8 bytes).

Character → char (2 bytes, Unicode).

Boolean → boolean (true/false).


Non-primitive Types:

String, Array, Class, Object.


Example:

int age = 20;
double pi = 3.14;
char grade = 'A';
boolean isJavaFun = true;
String name = "Nishant";


5. Variables in Java

Local → declared inside methods.

Instance → declared inside class, each object has its own copy.

Static → declared with static, shared among all objects.


class Student {
    static String college = "ABC"; // static variable
    String name; // instance variable
}


6. Control Statements

if / else

switch

for loop

while loop

do-while loop

break, continue


Example:

for(int i=1; i<=5; i++) {
    System.out.println(i);
}



7. Arrays in Java :-

Collection of similar elements.

int arr[] = {10, 20, 30};
System.out.println(arr[1]); // 20



# OOPS 


1. Class & Object

Class: Blueprint with variables + methods.

Object: Instance created using new.

Example :-

class Car {
    String brand;
    void drive() { System.out.println("Driving " + brand); }
}

public class Main {
    public static void main(String[] args) {
        Car c1 = new Car();  // object
        c1.brand = "BMW";
        c1.drive();
    }
}



2. Encapsulation (Data Hiding + Binding)

Definition: Wrapping data (variables) and methods (functions) into a single unit (class).

Access modifiers control visibility:

private → only inside the class

default → within the same package

protected → within the package + subclasses

public → accessible everywhere

Example :-

class Student {
    private String name; // hidden data
    public void setName(String n) { name = n; }
    public String getName() { return name; }
}


3. Inheritance (Reusability)

Definition: One class (child/subclass) acquiring the properties & behaviors of another class (parent/superclass).

Types in Java:

1. Single → One parent, one child.


2. Multilevel → A → B → C.


3. Hierarchical → One parent, multiple children.


4. (Multiple not supported in Java with classes, but achieved using interfaces).

Example :-

class Animal { void eat() { System.out.println("Eating"); } }
class Dog extends Animal { void bark() { System.out.println("Barking"); } }



4. Polymorphism (Many Forms)

Definition: Same function behaves differently depending on the context.


Types:

1. Compile-time (Method Overloading)

Same method name, different parameter list.

Example :-

class MathOps {
    int add(int a, int b) { return a+b; }
    double add(double a, double b) { return a+b; }
}


2. Run-time (Method Overriding)

Subclass redefines a method from superclass.

Example :-

class Animal { void sound() { System.out.println("Animal sound"); } }
class Dog extends Animal { void sound() { System.out.println("Bark"); } }




5. Abstraction (Hiding Implementation)

Definition: Showing only what an object does, hiding how it does it.

Achieved using:

Abstract classes (contain abstract + concrete methods).

Interfaces (fully abstract in older Java, but can have default and static methods now).



Example (Interface) :-

interface Vehicle { void drive(); }
class Car implements Vehicle {
    public void drive() { System.out.println("Car is driving"); }
}

