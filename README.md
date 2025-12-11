# Introduction to ArrayList (Dynamic Arrays)

This lesson introduces the ArrayList class in Java in a way that directly parallels your understanding of regular arrays. The goal is to give you enough practical knowledge to use dynamic lists in projects, especially CPT games where objects appear and disappear frequently.

## 1. Importing ArrayList
Before using ArrayList, you must import it:

import java.util.*;

## 2. Creating an ArrayList

### Empty ArrayList of Strings
ArrayList<String> list = new ArrayList<String>();

### Empty ArrayList of Integers
ArrayList<Integer> nums = new ArrayList<Integer>();

Note: Integer is the object wrapper for int. ArrayList cannot store primitive types directly, but Java automatically converts between int and Integer when needed.

## 3. Basic Operations

### Add a value to the end
list.add("Ana");
nums.add(5);

### Insert at an index (shifts elements to the right)
list.add(1, "Inserted");

### Get a value
String name = list.get(0);

### Set or replace a value
list.set(0, "Updated");

### Remove by index
list.remove(2);

### Get the size
int count = list.size();

## 4. Looping Through an ArrayList

### Index loop
for (int i = 0; i < list.size(); i++) {
    System.out.println(list.get(i));
}

### Enhanced for-each loop
for (String s : list) {
    System.out.println(s);
}

## 5. Arrays vs. ArrayList Comparison Table

Feature | array | ArrayList
--- | --- | ---
Get size or length | arr.length | list.size()
Set value at index | arr[i] = x | list.set(i, x)
Get value at index | arr[i] | list.get(i)
Create | int[] arr = new int[5] | ArrayList<Integer> list = new ArrayList<Integer>()
Fixed or dynamic size | Fixed size | Changes size automatically
Extra helper methods | None | Many (add, remove, clear, isEmpty)
Types allowed | Primitives or objects | Objects only, supports autoboxing

## 6. Why Choose ArrayList?
Use a regular array when:
- The number of items is fixed.
- Performance and simplicity matter more than flexibility.

Use ArrayList when:
- The list must grow or shrink.
- Items appear or disappear unpredictably.
- You want convenience methods like add and remove.

Game example: Enemy objects spawn and get removed constantly, making ArrayList the natural structure.

## 7. Common Mistakes

1. Trying to use [] with ArrayList  
Incorrect: list[0] = "Bob";  
Correct: list.set(0, "Bob");

2. Forgetting the type parameter  
ArrayList requires a type inside angle brackets.

3. Using .length instead of .size()  
Arrays use length. ArrayLists use size().

4. Removing inside a forward loop  
Removing while looping upward can skip elements. Loop backward if removing.

## 8. Summary
You can now create, update, remove, and loop through ArrayLists. You understand how they differ from arrays, when to use each structure, and how to choose the right tool for the CPT and future programming assignments.
