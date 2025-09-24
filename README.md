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

```
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

dtype: int32
#Datatype of Series
s1.dtype
dtype('int32')
```
# Number of bytes consumed by Series
s1.nbytes

# Shape of the Series
s1.shape

# number of dimensions
s1.ndim

# Length of Series
len(s1)

s1.count()

s1.size

# Create series from List 
s0 = pd.Series([1,2,3],index = ['a','b','c'])
s0

dtype: int64
# Modifying index in Series
s1.index = ['a' , 'b' , 'c' , 'd' , 'e' , 'f' , 'g']
s1

dtype: int32
# Create Series using Random and Range function
v2 = np.random.random(10)
ind2 = np.arange(0,10)
s = pd.Series(v2,ind2)
v2 , ind2 , s
(array([0.87790351, 0.21256923, 0.2833476 , 0.84976498, 0.17274437,
        0.36953613, 0.92661933, 0.13005525, 0.25394528, 0.43563311]),
 array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9]),
 
 dtype: float64)
# Creating Series from Dictionary
dict1 = {'a1' :10 , 'a2' :20 , 'a3':30 , 'a4':40}
s3 = pd.Series(dict1)
s3

dtype: int64
pd.Series(99, index=[0, 1, 2, 3, 4, 5]) 

dtype: int64

Slicing Series

# Return all elements of the series
s[:]

dtype: float64
# First three element of the Series
s[0:3]

dtype: float64
# Last element of the Series
s[-1:]

dtype: float64
# Fetch first 4 elements in a series
s[:4]

dtype: float64
# Return all elements of the series except last two elements.
s[:-2]

dtype: float64

# Return all elements of the series except last element.
s[:-1]

dtype: float64
# Return last two elements of the series
s[-2:]

dtype: float64
# # Return last element of the series
s[-1:]

dtype: float64
s[-3:-1]

dtype: float64
Append Series
s2 = s1.copy()
s2

dtype: int32
s3

dtype: int64
# Append S2 & S3 Series
s4 = s2.append(s3)
s4

dtype: int64
# When "inplace=False" it will return a new copy of data with the operation performed
s4.drop('a4' , inplace=False)

dtype: int64
s4

dtype: int64
# When we use "inplace=True" it will affect the dataframe
s4.drop('a4', inplace=True)
s4

dtype: int64
s4 = s4.append(pd.Series({'a4': 7}))
s4

dtype: int64






# NumPy (17/09/25) 




# Import Numpy Library
import numpy as np
import warnings
warnings.filterwarnings("ignore")
from IPython.display import Image


Numpy Array Creation
list1 = [10,20,30,40,50,60]
list1

# Display the type of an object
type(list1)
list
#Convert list to Numpy Array
arr1 = np.array(list1)
arr1
array([10, 20, 30, 40, 50, 60])
#Memory address of an array object
arr1.data

# Display type of an object
type(arr1)
numpy.ndarray
#Datatype of array
arr1.dtype
dtype('int32')
# Convert Integer Array to FLOAT
arr1.astype(float)

# Generate evenly spaced numbers (space =1) between 0 to 10
np.arange(0,10)

# Generate numbers between 0 to 100 with a space of 10
np.arange(0,100,10)

# Generate numbers between 10 to 100 with a space of 10 in descending order
np.arange(100, 10, -10)

#Shape of Array
arr3 = np.arange(0,10)
arr3.shape

arr3

# Size of array
arr3.size

# Dimension 
arr3.ndim

# Datatype of object
arr3.dtype

# Bytes consumed by one element of an array object
arr3.itemsize

# Length of array
len(arr3)

# Generate an array of zeros
np.zeros(10)

# Generate an array of ones with given shape
np.ones(10)

# Repeat 10 five times in an array
np.repeat(10,5)

# Repeat each element in array 'a' thrice
a= np.array([10,20,30])
np.repeat(a,3)

# Array of 10's
np.full(5,10)

# Generate array of Odd numbers
ar1 = np.arange(1,20)
ar1[ar1%2 ==1]

# Generate array of even numbers
ar1 = np.arange(1,20)
ar1[ar1%2 == 0]

# Generate evenly spaced 4 numbers between 10 to 20.
np.linspace(10,20,4)

# Generate evenly spaced 11 numbers between 10 to 20.
np.linspace(10,20,11)

# Create an array of random values
np.random.random(4)

# Generate an array of Random Integer numbers
np.random.randint(0,500,5)

# Generate an array of Random Integer numbers
np.random.randint(0,500,10)





# Linear Algebra (17/09/25) 




import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D


v = [3,4]
u = [1,2,3]
v ,u

type(v)

w = np.array([9,5,7])
type(w)

w.shape[0]

w.shape


# Reading elements from an array
a = np.array([7,5,3,9,0,2])
a[0]

a[1:]

a[1:4]

a[-1]

a[-3]

a[-6]

a[-3:-1]



# Plotting a Vector


v = [3,4]
u = [1,2,3]
plt.plot (v)

plt.plot([0,v[0]] , [0,v[1]])

# Plot 2D Vector

plt.plot([0,v[0]] , [0,v[1]])
plt.plot([8,-8] , [0,0] , 'k--')
plt.plot([0,0] , [8,-8] , 'k--')
plt.grid()
plt.axis((-8, 8, -8, 8))
plt.show()


# Plot 3D Vector

fig = plt.figure()
ax = Axes3D(fig)
ax.plot([0,u[0]],[0,u[1]],[0,u[2]])
plt.axis('equal')
ax.plot([0, 0],[0, 0],[-5, 5],'k--')
ax.plot([0, 0],[-5, 5],[0, 0],'k--')
ax.plot([-5, 5],[0, 0],[0, 0],'k--')
plt.show()



