# Introduction to ArrayList and Dynamic Arrays

In this lesson, we extend the ideas learned with regular arrays by introducing a new data structure: the ArrayList. 

This is a lightweight introduction intended only to give you a practical toolkit useful for future projects, including CPT game development where objects will frequently be created, removed, or resized dynamically.

## Learning Goals
By the end of this lesson, you should be able to:
- Explain the difference between a fixed-size array and a dynamic ArrayList.
- Create, modify, and retrieve values from an ArrayList.
- Recognize common patterns (adding, removing, iterating).
- Compare arrays and ArrayLists using a direct side-by-side reference.
- Understand why ArrayList exists and when it is the correct data structure to use.

## 1. Why Not Always Use Arrays?
A regular array has two main limitations:
1. The size must be known in advance.
2. The size cannot change afterwards.

This works well for situations like:
- Storing the test scores of exactly 30 students.
- Keeping track of the days of the week.
- A fixed set of sensor readings.

But it breaks down when:
- New items appear unpredictably.
- Items disappear or get removed.
- The number of items changes constantly.

### Dynamic Problems Require Dynamic Structures
In a CPT-style arcade game, for example:
- Enemies spawn at random intervals.
- Projectiles appear when fired and disappear on collision.
- The number of objects changes every frame.

A fixed array is a bad fit here because you would constantly be trying to track “empty slots” or resizing manually. The ArrayList solves this problem by growing and shrinking automatically.

## 2. What Is an ArrayList?
An ArrayList is a resizable array. It stores elements in order, just like a regular array, but it can add or remove elements at any time.

To use ArrayList, you must import it:

import java.util.ArrayList;

Then you can create one:

ArrayList<String> names = new ArrayList<>();

The angle brackets <String> tell Java what type the list holds.

## 3. Basic Operations

### Add an item
names.add("Ana");

### Get an item
String s = names.get(0);

### Change an item
names.set(1, "Lila");

### Remove an item
names.remove(0);

### Size
int count = names.size();

## 4. Iterating Through an ArrayList

### Regular index loop
for (int i = 0; i < names.size(); i++) {
    System.out.println(names.get(i));
}

### Enhanced for loop
for (String n : names) {
    System.out.println(n);
}

## 5. Arrays vs ArrayList — Side-by-Side Reference

### Creating
Array:
int[] nums = new int[5];

ArrayList:
ArrayList<Integer> nums = new ArrayList<>();

### Accessing length/size
Array: nums.length  
ArrayList: nums.size()

### Getting/setting values
Array:
nums[2] = 10;

ArrayList:
nums.set(2, 10);

### Adding/removing
Arrays cannot resize.  
ArrayList can add and remove freely.

## 6. Behind the Scenes (Optional)
An ArrayList is built on top of a regular array. When it runs out of space, it automatically:
- allocates a larger array
- copies everything over

## 7. Practical Examples
Tracking enemies, storing shapes, logging inputs.

## 8. Common Mistakes
- Using [] with ArrayList
- Forgetting <Type>
- Using .length instead of .size()
- Removing while looping forward




# Practice Problems
Annotated solutions to these problems can be found [here](SOLUTIONS.md).