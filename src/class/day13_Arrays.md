#Java Arrays
Normally, an array is a collection of similar type of elements which has contiguous memory location.

Java array is an object which contains elements of a similar data type. Additionally, The elements of an array are stored in a contiguous memory location. It is a data structure where we store similar elements. We can store only a fixed set of elements in a Java array.

Array in Java is index-based, the first element of the array is stored at the 0th index, 2nd element is stored on 1st index and so on.

Unlike C/C++, we can get the length of the array using the length member. In C/C++, we need to use the sizeof operator.

In Java, array is an object of a dynamically generated class. Java array inherits the Object class, and implements the Serializable as well as Cloneable interfaces. We can store primitive values or objects in an array in Java. Like C/C++, we can also create single dimentional or multidimentional arrays in Java.

##Types of Array in java
There are two types of array.

###Single Dimensional Array
###Multidimensional Array

Moreover, Java provides the feature of anonymous arrays which is not available in C/C++.

##Declaration, Instantiation and Initialization of Java Array
We can declare, instantiate and initialize the java array together by:

int a[]={33,3,4,5};//declaration, instantiation and initialization  

###For-each Loop for Java Array
We can also print the Java array using for-each loop. The Java for-each loop prints the array elements one by one. It holds an array element in a variable, then executes the body of the loop.

###Passing Array to a Method in Java
We can pass the java array to method so that we can reuse the same logic on any array.

###Anonymous Array in Java
Java supports the feature of an anonymous array, so you don't need to declare the array while passing an array to the method.

###ArrayIndexOutOfBoundsException
The Java Virtual Machine (JVM) throws an ArrayIndexOutOfBoundsException if length of the array in negative, equal to the array size or greater than the array size while traversing the array.