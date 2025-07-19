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
You're on the right track for Problem 4: Check Palindrome String by thinking about using StringBuilder.reverse(), which you just learned!

However, there's a crucial detail in Java when comparing strings that often trips up beginners:

The Issue: == vs. .equals() for String Comparison

In Java, == operator for objects (including String objects) compares their memory addresses (i.e., if they are the exact same object in memory). It does not compare their content.

When you do String reversed_string = sb.toString();, you are creating a new String object in memory. Even if its content is identical to name, it will be a different object. So, name == reversed_string will almost always evaluate to false, even if the string is a palindrome.

To compare the actual content of two strings in Java, you must use the .equals() method

-------------------------------------------------------------------------------

Okay, no problem! Let's go with the most efficient and common solution for Problem 8: Contains Duplicate using a HashSet. This method is generally preferred in interviews for its time complexity.

Problem 8: Contains Duplicate (Solution using HashSet)
Concept:

A HashSet in Java stores only unique elements. If you try to add an element that is already present in the HashSet, the add() method returns false. We can leverage this property to detect duplicates.

Algorithm:

Create an empty HashSet.

Iterate through each number in the given nums array.

For each number:

Try to add it to the HashSet.

If add() returns false, it means the number was already in the HashSet, indicating a duplicate. In this case, we immediately know there's a duplicate, so we can print "true" and stop.

If the loop finishes without finding any duplicates (i.e., add() always returned true), it means all elements were distinct. In this case, we print "false".

----------------------------------------------------------------------------------------------------------


That's an excellent follow-up question! It naturally extends the "Contains Duplicate" problem and leads us to use another very powerful and common data structure in Java: a HashMap (or Dictionary in Python, Map in general).

Instead of just checking if a duplicate exists, you want to count how many times each number appears.
Solution Concept: Using HashMap
A HashMap stores data in key-value pairs.

Key: In this problem, the unique number itself will be the key.

Value: The count of how many times that number has appeared will be the value.

Algorithm:

Create an empty HashMap<Integer, Integer> (where the key is the number and the value is its count).

Iterate through each number in the input nums array.

For each currentNum:

Check if currentNum is already a key in the HashMap.

If it is present, get its current count, increment it by 1, and update the count in the HashMap.

If it is not present, it means this is the first time we've seen this number, so add it to the HashMap with a count of 1.

After iterating through the entire array, iterate through the entrySet() of the HashMap (which gives you each key-value pair) and print the number (key) and its count (value).


-------------------------------------------------------------------------------



Enhanced For-Loop (for (int currentNum : nums)):
This type of loop is designed to iterate directly over the elements of an array or collection, not their indices.

In the first iteration, currentNum will be nums[0].

In the second iteration, currentNum will be nums[1].

...and so on, until currentNum holds the value of nums[n-1].

So, currentNum is the value you want to use as the key in your HashMap.

Traditional For-Loop (for (int i = 0; i < n; i++) { int currentNum = nums[i]; ... }):
Here, you explicitly get the value at index i by saying int currentNum = nums[i];. Again, currentNum holds the value.


