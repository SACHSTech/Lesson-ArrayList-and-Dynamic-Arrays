# Introduction to ArrayList (Dynamic Arrays)

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

