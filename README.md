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





# PANDAS (17/09/25) 


import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import glob
import re
import math
import warnings
warnings.filterwarnings("ignore")
Series
Create Series
# Create series from Nump Array
v = np.array([1,2,3,4,5,6,7])
s1 = pd.Series(v)
s1
0    1
1    2
2    3
3    4
4    5
5    6
6    7
dtype: int32
#Datatype of Series
s1.dtype
dtype('int32')

# Number of bytes consumed by Series
s1.nbytes
28
# Shape of the Series
s1.shape
(7,)
# number of dimensions
s1.ndim
1
# Length of Series
len(s1)
7
s1.count()
7
s1.size
7
# Create series from List 
s0 = pd.Series([1,2,3],index = ['a','b','c'])
s0
a    1
b    2
c    3
dtype: int64
# Modifying index in Series
s1.index = ['a' , 'b' , 'c' , 'd' , 'e' , 'f' , 'g']
s1
a    1
b    2
c    3
d    4
e    5
f    6
g    7
dtype: int32
# Create Series using Random and Range function
v2 = np.random.random(10)
ind2 = np.arange(0,10)
s = pd.Series(v2,ind2)
v2 , ind2 , s
(array([0.87790351, 0.21256923, 0.2833476 , 0.84976498, 0.17274437,
        0.36953613, 0.92661933, 0.13005525, 0.25394528, 0.43563311]),
 array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9]),
 0    0.877904
 1    0.212569
 2    0.283348
 3    0.849765
 4    0.172744
 5    0.369536
 6    0.926619
 7    0.130055
 8    0.253945
 9    0.435633
 dtype: float64)
# Creating Series from Dictionary
dict1 = {'a1' :10 , 'a2' :20 , 'a3':30 , 'a4':40}
s3 = pd.Series(dict1)
s3
a1    10
a2    20
a3    30
a4    40
dtype: int64
pd.Series(99, index=[0, 1, 2, 3, 4, 5]) 
0    99
1    99
2    99
3    99
4    99
5    99
dtype: int64

Slicing Series
s
0    0.877904
1    0.212569
2    0.283348
3    0.849765
4    0.172744
5    0.369536
6    0.926619
7    0.130055
8    0.253945
9    0.435633
dtype: float64
# Return all elements of the series
s[:]
0    0.877904
1    0.212569
2    0.283348
3    0.849765
4    0.172744
5    0.369536
6    0.926619
7    0.130055
8    0.253945
9    0.435633
dtype: float64
# First three element of the Series
s[0:3]
0    0.877904
1    0.212569
2    0.283348
dtype: float64
# Last element of the Series
s[-1:]
9    0.435633
dtype: float64
# Fetch first 4 elements in a series
s[:4]
0    0.877904
1    0.212569
2    0.283348
3    0.849765
dtype: float64
# Return all elements of the series except last two elements.
s[:-2]
0    0.877904
1    0.212569
2    0.283348
3    0.849765
4    0.172744
5    0.369536
6    0.926619
7    0.130055
dtype: float64

0    0.877904
1    0.212569
2    0.283348
3    0.849765
4    0.172744
5    0.369536
6    0.926619
7    0.130055
dtype: float64
# Return all elements of the series except last element.
s[:-1]
0    0.877904
1    0.212569
2    0.283348
3    0.849765
4    0.172744
5    0.369536
6    0.926619
7    0.130055
8    0.253945
dtype: float64
# Return last two elements of the series
s[-2:]
8    0.253945
9    0.435633
dtype: float64
# # Return last element of the series
s[-1:]
9    0.435633
dtype: float64
s[-3:-1]
7    0.130055
8    0.253945
dtype: float64
Append Series
s2 = s1.copy()
s2
0    10
1    20
2    30
dtype: int32
s3
a1    10
a2    20
a3    30
a4    40
dtype: int64
# Append S2 & S3 Series
s4 = s2.append(s3)
s4
0     10
1     20
2     30
a1    10
a2    20
a3    30
a4    40
dtype: int64
# When "inplace=False" it will return a new copy of data with the operation performed
s4.drop('a4' , inplace=False)
0     10
1     20
2     30
a1    10
a2    20
a3    30
dtype: int64
s4
0     10
1     20
2     30
a1    10
a2    20
a3    30
a4    40
dtype: int64
# When we use "inplace=True" it will affect the dataframe
s4.drop('a4', inplace=True)
s4
0     10
1     20
2     30
a1    10
a2    20
a3    30
dtype: int64
s4 = s4.append(pd.Series({'a4': 7}))
s4
0     10
1     20
2     30
a1    10
a2    20
a3    30
a4     7
dtype: int64






# NumPy (17/09/25) 
