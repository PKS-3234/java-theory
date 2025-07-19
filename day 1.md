Hint for a Better Approach
Think about the properties of the numbers. You have numbers from 0 to N.

What is the sum of all numbers from 0 to N? (There's a well-known mathematical formula for this!)
---------------------------------------------

Create Methods: Always inside a class.

Call Methods from main:

If the method is static, call it directly by its name (if in the same class) or ClassName.methodName() (if in another class).

If the method is non-static (instance method), you must first create an object of the class and then call the method using objectName.methodName()

------------------------------------------------------------------------
there is no slicing concept in java
and Strings are immutable.

The StringBuilder Concept in Java
1. The Problem with String Immutability

In Java, String objects are immutable. This means that once a String object is created, its content cannot be changed.
Any operation that appears to modify a String (like concat(), replace(), toLowerCase(), or even + operator for concatenation) actually creates a new String object in memory.
Performance overhead: More time spent creating and destroying objects.
Memory overhead: More memory used as old, no longer referenced String objects accumulate before garbage collection.

 The Solution: StringBuilder (and StringBuffer)

To overcome the performance and memory issues associated with frequent String modifications, Java provides two mutable (changeable) classes:

StringBuilder

StringBuffer

These classes represent sequences of characters that can be modified directly without creating new objects for each change.

Key Differences between StringBuilder and StringBuffer:

StringBuilder: Not thread-safe. This means if multiple threads try to modify the same StringBuilder object concurrently, it can lead to data inconsistency. 
However, it is generally faster because it doesn't have the overhead of synchronization.

StringBuffer: Thread-safe (synchronized). This means its methods are synchronized, ensuring that only one thread can modify it at a time. This makes it suitable for multi-threaded environments,
but it comes with a performance cost due to the synchronization overhead, making it slower than StringBuilder.

----------------------------------------------------------------
