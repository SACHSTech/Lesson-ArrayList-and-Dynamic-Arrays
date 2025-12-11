# ArrayList Practice Problems — Annotated Solutions

## Problem 1 — Create and Print a Simple ArrayList
Store three names in an ArrayList and use an enhanced for-loop to print each one:
```java
@Override
public void run() {
    ArrayList<String> list = new ArrayList<String>();
    list.add("Ava");
    list.add("Liam");
    list.add("Zoe");

    for (String name : list) {
        System.out.println(name);
    }
}
```

Alternatively, you can solve this with an index loop approach as well:

```java
@Override
public void run() {
    ArrayList<String> list = new ArrayList<String>();
    list.add("Ava");
    list.add("Liam");
    list.add("Zoe");

    for (int i = 0; i < list.size(); i++) {
        System.out.println(list.get(i));
    }
}
```

You can see that the for-each loop reads a little cleaner than the index loop. 

## Problem 2 — Add and Remove Elements
Modify the given list, then print all items.
```java
@Override
public void run() {
    ArrayList<String> items = new ArrayList<String>();
    items.add("Pen");
    items.add("Pencil");
    items.add("Eraser");

    items.add("Marker");
    items.remove("Pencil");

    for (String item : items) {
        System.out.println(item);
    }
}
```

## Problem 3 — Insert at a Specific Index
Insert “Green” at index 1.
```java
@Override
public void run() {
    ArrayList<String> colours = new ArrayList<String>();
    colours.add("Red");
    colours.add("Blue");
    colours.add("Yellow");

    colours.add(1, "Green");

    for (String c : colours) {
        System.out.println(c);
    }
}
```

## Problem 4 — Replace a Value
Use `set()` to replace the middle element.
```java
@Override
public void run() {
    ArrayList<Integer> nums = new ArrayList<Integer>();
    nums.add(3);
    nums.add(8);
    nums.add(10);

    nums.set(1, 20);

    for (int n : nums) {
        System.out.println(n);
    }
}
```

## Problem 5 — Count How Many Times a Value Appears
Loop and compare strings.
```java
@Override
public void run() {
    ArrayList<String> pets = new ArrayList<String>();
    pets.add("Cat");
    pets.add("Dog");
    pets.add("Fish");
    pets.add("Dog");
    pets.add("Cat");
    pets.add("Dog");

    int count = 0;
    for (String p : pets) {
        if (p.equals("Dog")) {
            count++;
        }
    }

    System.out.println("Dog appears " + count + " times.");
}
```

## Problem 6 — Print All Values Above a Threshold
Print only values > 10.
```java
@Override
public void run() {
    ArrayList<Integer> temps = new ArrayList<Integer>();
    temps.add(12);
    temps.add(5);
    temps.add(19);
    temps.add(3);
    temps.add(17);

    for (int t : temps) {
        if (t > 10) {
            System.out.println(t);
        }
    }
}
```

## Problem 7 — Remove All Negative Numbers
Loop backward to avoid skipping after removals.
```java
@Override
public void run() {
    ArrayList<Integer> data = new ArrayList<Integer>();
    data.add(4);
    data.add(-3);
    data.add(9);
    data.add(-1);
    data.add(7);

    for (int i = data.size() - 1; i >= 0; i--) {
        if (data.get(i) < 0) {
            data.remove(i);
        }
    }

    System.out.println(data);
}
```

## Problem 8 — Build a List From User Input
Read 5 words using `readLine()`, then print in reverse.
```java
@Override
public void run() {
    ArrayList<String> words = new ArrayList<String>();

    for (int i = 0; i < 5; i++) {
        String w = readLine("Enter a word: ");
        words.add(w);
    }

    for (int i = words.size() - 1; i >= 0; i--) {
        System.out.println(words.get(i));
    }
}
```

## Problem 9 — Find the Largest Value
Track max as you loop.
```java
@Override
public void run() {
    ArrayList<Integer> nums = new ArrayList<Integer>();
    nums.add(14);
    nums.add(2);
    nums.add(27);
    nums.add(19);
    nums.add(8);

    int max = nums.get(0);

    for (int n : nums) {
        if (n > max) {
            max = n;
        }
    }

    System.out.println("Largest value: " + max);
}
```

## Problem 10 — Refactor Array Code to Use ArrayList
Same logic, using `size()` and `get()`.
```java
@Override
public void run() {
    ArrayList<Integer> scores = new ArrayList<Integer>();
    scores.add(65);
    scores.add(42);
    scores.add(88);
    scores.add(51);
    scores.add(33);

    int count = 0;

    for (int i = 0; i < scores.size(); i++) {
        if (scores.get(i) > 50) {
            count++;
        }
    }

    System.out.println(count);
}
```

## Problem 11 — Remove All Occurrences of a Word (Case-Insensitive)
Convert both sides to the same case and loop backward. 
```java
@Override
public void run() {
    ArrayList<String> words = new ArrayList<String>();
    words.add("Apple");
    words.add("banana");
    words.add("APPLE");
    words.add("Cherry");
    words.add("apple");

    for (int i = words.size() - 1; i >= 0; i--) {
        if (words.get(i).toUpperCase().equals("APPLE")) {
            words.remove(i);
        }
    }

    System.out.println(words);
}
```

## Problem 12 — Create a New Filtered List
Build a second list based on the condition.
```java
@Override
public void run() {
    ArrayList<Integer> nums = new ArrayList<Integer>();
    nums.add(3);
    nums.add(15);
    nums.add(8);
    nums.add(22);
    nums.add(5);
    nums.add(19);

    ArrayList<Integer> filtered = new ArrayList<Integer>();

    for (int n : nums) {
        if (n >= 10 && n <= 20) {
            filtered.add(n);
        }
    }

    System.out.println(filtered);
}
```

## Problem 13 — Rotate All Values Right by One
Store the last element, shift right, then place it at index 0.
```java
@Override
public void run() {
    ArrayList<String> letters = new ArrayList<String>();
    letters.add("A");
    letters.add("B");
    letters.add("C");
    letters.add("D");

    String last = letters.get(letters.size() - 1);

    for (int i = letters.size() - 1; i > 0; i--) {
        letters.set(i, letters.get(i - 1));
    }

    letters.set(0, last);

    System.out.println(letters);
}
```

## Problem 14 — Mirror the List
Append reverse order of elements to the end of the same list.
```java
@Override
public void run() {
    ArrayList<Integer> nums = new ArrayList<Integer>();
    nums.add(1);
    nums.add(2);
    nums.add(3);

    for (int i = nums.size() - 1; i >= 0; i--) {
        nums.add(nums.get(i));
    }

    System.out.println(nums);
}
```

## Problem 15 — 2D ArrayList (List of Lists)
Build rows separately and print row-major order.
```java
@Override
public void run() {
    ArrayList<ArrayList<String>> chart = new ArrayList<ArrayList<String>>();

    ArrayList<String> row0 = new ArrayList<String>();
    row0.add("Ava");
    row0.add("Ben");

    ArrayList<String> row1 = new ArrayList<String>();
    row1.add("Mia");
    row1.add("Noah");
    row1.add("Zoe");

    ArrayList<String> row2 = new ArrayList<String>();
    row2.add("Kai");

    chart.add(row0);
    chart.add(row1);
    chart.add(row2);

    for (ArrayList<String> row : chart) {
        for (String name : row) {
            System.out.print(name + " ");
        }
        System.out.println();
    }

    chart.get(2).add("Liam");
    chart.get(0).set(1, "Ben (away)");

    System.out.println();

    for (ArrayList<String> row : chart) {
        for (String name : row) {
            System.out.print(name + " ");
        }
        System.out.println();
    }
}
```
