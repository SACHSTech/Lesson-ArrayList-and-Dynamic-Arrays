# Introduction to ArrayList and Dynamic Arrays

This lesson introduces the ArrayList class in Java in a way that directly parallels your understanding of regular arrays. The goal is to give you enough practical knowledge to use dynamic lists in projects, especially CPT games where objects appear and disappear frequently.

## Why Learn ArrayList?

Up to this point, we have only worked with regular arrays, which are extremely useful but have one major limitation: *their size never changes*. This becomes a real limitation in programs where the number of items is not fixed. 

Think ahead to your CPT project, especially if you build a game: enemies spawn and disappear, projectiles get created and destroyed, inventories grow and shrink. Trying to manage this with a fixed array forces you to track empty slots, shift elements manually, or build new arrays constantly. ArrayList exists to solve exactly this problem. It behaves like a **resizable array** and gives you simple tools for adding, removing, and inserting elements without worrying about capacity. 


## 1. Importing ArrayList

Before using `ArrayList`, you must import the Java library that enables its function.

Add the following line to the top of your `.java` program file, along with any existing import statements:

```java
import java.util.ArrayList;
```

Some IDEs like Visual Studio Code will automatically add the import line as soon as you write a line of code requiring it.

## 2. Creating an ArrayList
Using `ArrayList` requires a new syntax using angle brackets. The angle brackets tell Java what data type the `ArrayList` will store.

Recall a regular array for integers:

```java
int[] nums = new int[5];
```

The type is written *before* the brackets.

In `ArrayList`, the type goes inside angle brackets, like this:

### Empty ArrayList of Strings
```java
ArrayList<String> list = new ArrayList<String>();
```

### Empty ArrayList of Integers
```java
ArrayList<Integer> nums = new ArrayList<Integer>();
```

Note: `Integer` is an object wrapper for `int`. `ArrayList` can only store objects, not primitive types, so when you want to store numbers you must use the object versions:

- `int` becomes `Integer`
- `double` becomes `Double`
- `boolean` becomes `Boolean`

You don’t need to do anything special — just use the wrapper type in the angle brackets, and Java will let you store values normally.

## 3. Basic Operations
This is a curated set of operations that will be helpful when you begin working with ArrayLists. Each example includes a simple before/after visualization.

### Add a value to the end
```java
list.add("Ana");
```
#### Before:  
`["Ming", "Ben"]  `

#### After:  
`["Ming", "Ben", "Ana"]`

### Insert at an index (shifts elements to the right)
```java
list.add(1, "Inserted");
```

#### Before:  
`["A", "B", "C"]`

#### After:  
`["A", "Inserted", "B", "C"]`

### Get a value at a specific index
```java
String name = list.get(0);
```

#### Before:  
`["Ana", "Ben", "Kai"]`

#### Result:  
`name` becomes `"Ana"`


### Set or replace a value at a specific index
```java
list.set(0, "Updated");
```

#### Before:  
`["Ana", "Ben", "Kai"]`  

#### After:  
`["Updated", "Ben", "Kai"]`


### Remove value at a specific index
```java
list.remove(2);
```

#### Before:  
`["A", "B", "C", "D"]`

#### After:  
`["A", "B", "D"]`

### Get the size of the list
```java
int count = list.size();
```

#### Before:  
["Ana", "Ben", "Kai"]

#### Result:  
`count` becomes `3`




## 4. Looping Through an ArrayList
Use similar techniques as regular arrays to traverse and loop through the array:

### Index loop
```java
for (int i = 0; i < list.size(); i++) {
    System.out.println(list.get(i));
}
```

### Enhanced for-each loop
```java
for (String s : list) {
    System.out.println(s);
}
```

## 5. Arrays vs. ArrayList Comparison Table
This is a helpful table that compares common array operations for a standard array named `arr` and a dynamic `ArrayList` named `list`:

Feature | array | ArrayList
--- | --- | ---
Get size or length | `arr.length` | `list.size()`
Set value at index | `arr[i] = x` | `list.set(i, x)`
Get value at index | `arr[i]` | `list.get(i)`
Create | `int[] arr = new int[5]` | `ArrayList<Integer> list = new ArrayList<Integer>()`
Fixed or dynamic size | Fixed size | Changes size automatically
Extra helper methods | None | Many (`add`, `remove`, `isEmpty`, etc.)
Data types allowed | Primitives (`int`, `double`, etc.) or objects (`String`) | Objects only, use wrappers (e.g. `Integer`, `Double`, `String`)

## 6. Why Choose ArrayList?

Use a regular array when:
- The number of items is fixed.
- You know the exact size ahead of time.
- Performance and simplicity matter more than flexibility.

Use ArrayList when:
- The list must grow or shrink at runtime.
- Items appear and disappear unpredictably.
- You want convenience methods like add, remove, etc.

## 7. Common Mistakes

1. Using `[]` on an `ArrayList`  
Incorrect: `list[0] = "Bob";`  
Correct: `list.set(0, "Bob");`

2. Forgetting the type parameter  
`ArrayList` requires a type in angle brackets.

3. Using `.length` instead of `.size()`  
Arrays use `length`. ArrayLists use `size()`.

4. Removing while looping forward  
This can skip elements. Loop backward if removing.


<br>

# Practice Problems - ArrayList

A set of 10 problems designed to introduce ArrayList operations gradually. Earlier problems reinforce basic syntax, while later problems mix logic, traversal, and refactoring.

Annotated solutions to these problems can be found [here](SOLUTIONS.md).

## Problem 1 — Create and Print a Simple ArrayList
Create an `ArrayList<String>` containing the names `"Ava"`, `"Liam"`, and `"Zoe"`.  
Print each element on its own line using a loop.

Expected Output:
```
Ava
Liam
Zoe
```
<br>

## Problem 2 — Add and Remove Elements
Start with the list:
```java
ArrayList<String> items = new ArrayList<String>();
items.add("Pen");
items.add("Pencil");
items.add("Eraser");
```

Add `"Marker"` to the end, then remove `"Pencil"`.  
Print the final list using a loop.

Expected Output:
```
Pen
Eraser
Marker
```

<br>

## Problem 3 — Insert at a Specific Index
Start with:
```java
ArrayList<String> colours = new ArrayList<String>();
colours.add("Red");
colours.add("Blue");
colours.add("Yellow");
```

Insert `"Green"` at index 1.  
Print the updated list.

<br>

## Problem 4 — Replace a Value
Given:
```java
ArrayList<Integer> nums = new ArrayList<Integer>();
nums.add(3);
nums.add(8);
nums.add(10);
```

Replace the middle value (`8`) with `20`.  
Print the final list.

<br>

## Problem 5 — Count How Many Times a Value Appears
Create an `ArrayList<String>` of the following pet names:
`["Cat", "Dog", "Fish", "Dog", "Cat", "Dog"]`

Count and print how many times `"Dog"` appears.

Expected Output:
```
Dog appears 3 times.
```

<br>

## Problem 6 — Print All Values Above a Threshold
Given:
```java
ArrayList<Integer> temps = new ArrayList<Integer>();
temps.add(12);
temps.add(5);
temps.add(19);
temps.add(3);
temps.add(17);
```

Print only the temperatures greater than 10.

<br>

## Problem 7 — Remove All Negative Numbers
Start with:
```java
ArrayList<Integer> data = new ArrayList<Integer>();
data.add(4);
data.add(-3);
data.add(9);
data.add(-1);
data.add(7);
```

Remove all negative numbers from the list.  
(HINT: loop backward when removing.)

Final Result:
```
[4, 9, 7]
```

<br>

## Problem 8 — Build a List From User Input (Assume Input Provided)
Write code that asks the user for 5 words (one at a time), stores them in an `ArrayList<String>`, then prints them in reverse order.

If user types:
```
hello
world
java
is
fun
```

The program prints:
```
fun
is
java
world
hello
```

<br>

## Problem 9 — Find the Largest Value
Given:
```java
ArrayList<Integer> nums = new ArrayList<Integer>();
nums.add(14);
nums.add(2);
nums.add(27);
nums.add(19);
nums.add(8);
```

Write code to find and print the largest number in the list.

Expected Output:
```
Largest value: 27
```

<br>

## Problem 10 — Refactor Array Code to Use ArrayList
Below is code that uses a regular array to count how many values are above 50.

```
int[] scores = {65, 42, 88, 51, 33};
int count = 0;

for (int i = 0; i < scores.length; i++) {
    if (scores[i] > 50) {
        count++;
    }
}
System.out.println(count);
```

Task: Rewrite this exact logic using an `ArrayList<Integer>` instead of an array.  

Your `ArrayList` version should produce the same output.

<br>

## Problem 11 — Remove All Occurrences of a Word (Case-Insensitive)
You are given:
```java
ArrayList<String> words = new ArrayList<String>();
words.add("Apple");
words.add("banana");
words.add("APPLE");
words.add("Cherry");
words.add("apple");
```

Write code that removes all occurrences of "apple", ignoring case.  
Print the final list.

Expected Result:
```
[banana, Cherry]
```

#### HINT 1:  
Consider converting both the list element and the word "apple" to the same case before comparing them. Use String methods such as `.toUpperCase()` or `.toLowerCase()`

#### HINT 2:
You can apply a method directly to the result of another method.
For example, in:
```java
words.get(i).toUpperCase()
```

- `words.get(i)` gives you the String at index i
- `.toUpperCase()` is then applied to that String

This technique is called **method chaining**, and it lets you write expressions in a compact way.

<br>

## Problem 12 — Create a New Filtered List
You are given the following numbers:
```java
ArrayList<Integer> nums = new ArrayList<Integer>();
nums.add(3);
nums.add(15);
nums.add(8);
nums.add(22);
nums.add(5);
nums.add(19);
```

Create a new ArrayList containing only the values between 10 and 20 inclusive.  
Print the new list.

<br>

## Problem 13 — Rotate All Values Right by One
Given:
```java
ArrayList<String> letters = new ArrayList<String>();
letters.add("A");
letters.add("B");
letters.add("C");
letters.add("D");
```

Write code that rotates all elements to the right by one position.

Before:
```
[A, B, C, D]
```

After:
```
[D, A, B, C]
```

<br>

## Problem 14 — Mirror the List
Given:
```java
ArrayList<Integer> nums = new ArrayList<Integer>();
nums.add(1);
nums.add(2);
nums.add(3);
```

Modify the list so that it becomes a mirrored version of itself:

Before:
```
[1, 2, 3]
```

After:
```
[1, 2, 3, 3, 2, 1]
```

Use `add()` and `get()` only. Do not create a second list.

<br>

## Problem 15 — 2D ArrayList (List of Lists)
Create a 2D ArrayList representing a seating chart:

```
Row 0 → ["Ava", "Ben"]  
Row 1 → ["Mia", "Noah", "Zoe"]  
Row 2 → ["Kai"]
```

Tasks:
1. Print the entire chart in row–major order.  
2. Add "Liam" to Row 2.  
3. Replace "Ben" with "Ben (away)".  
4. Print the updated chart.
