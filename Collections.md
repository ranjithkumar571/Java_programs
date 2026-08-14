# Java Collections:

# List
In Java, a List is an ordered collection of elements (also known as a sequence) that allows duplicate values and provides precise control over where each element is inserted.
Because java.util.List is an interface, you cannot instantiate it directly; instead, you must use one of its implementing classes like ArrayList or LinkedList.
Common Implementing ClassesArrayList: Backed by a resizable array. It provides fast random access (O(1)) but slower insertions/deletions in the middle of the list (O(n)).LinkedList:
Backed by a doubly linked list. It provides fast insertions/deletions (O(1)) but slower positional access (O(n)).Vector / Stack: Thread-safe (synchronized) legacy classes that are rarely used in modern, high-performance code.Ways to Create a List

```
import java.util.ArrayList;

import java.util.LinkedList;
import java.util.List;
import java.util.Arrays;

public class ListExample {
    public static void main(String[] args) {
        // 1. Modifiable ArrayList (Most Common)
        List<String> fruits = new ArrayList<>();
        
        // 2. Modifiable LinkedList
        List<Integer> numbers = new LinkedList<>();
        
        // 3. Immutable List (Java 9+) - Cannot add or remove elements
        List<String> fixedList = List.of("Apple", "Banana", "Orange");
        
        // 4. Fixed-size List backed by an array (Modifiable values, but fixed size)
        List<String> arrayList = Arrays.asList("Red", "Green", "Blue");
    }
}
```
.Essential List MethodsHere are the most common operations used to manipulate a mutable List

| Method | Description | Example |
| :--- | :--- | :--- |
| `add(E element)` | Appends an element to the end. | `fruits.add("Apple");` |
| `add(int index, E element)` | Inserts an element at a specific index. | `fruits.add(0, "Mango");` |
| `get(int index)` | Retrieves the element at a specific index. | `String f = fruits.get(1);` |
| `set(int index, E element)` | Replaces the element at a specific index. | `fruits.set(0, "Banana");` |
| `remove(int index)` | Removes the element at a specific index. | `fruits.remove(0);` |
| `size()` | Returns the number of elements. | `int total = fruits.size();` |
| `clear()` | Removes all elements from the list. | `fruits.clear();` |

Important Rules to Remember:
1. Wrapper Classes Only: Lists cannot store primitive data types (like int, char, or boolean) directly. You must use their object wrappers (like Integer, Character, or Boolean). Java automatically converts these via autoboxing.
2. Zero-Indexed: Just like standard Java arrays, elements in a List are indexed starting at 0.
