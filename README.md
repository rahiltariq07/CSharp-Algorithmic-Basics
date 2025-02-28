# C# Algorithmic Basics 🚀

This repository contains a **quick revision** of essential C# concepts required for solving **algorithmic problems**. It covers variables, loops, strings, arrays, recursion, sorting, searching, and bitwise operations with code examples.


## Topics Covered

Below is an explanation of each concept along with code examples and guidance on where to use them.

---

## 1️⃣ Variables and Data Types

In C#, **variables** are used to store data. Each variable has a **data type** that defines what kind of data it can hold. You declare a variable with its type so the computer knows how much space to allocate and what operations can be performed on it.

### Code Example:
```csharp
int num = 10;       // Integer: Stores whole numbers.
double pi = 3.14;   // Double: Stores decimal numbers.
char letter = 'A';  // Character: Stores a single character.
string name = "John"; // String: Stores text.
bool isTrue = true; // Boolean: Stores true/false.
```
### Explanation:
- **Variables & Data Types:**  
  Use these when you need to store different types of information. For example, use an `int` for counting items, a `double` for precise measurements, a `char` for single letters, a `string` for text, and a `bool` for conditions (true/false).

### Input and Output

Interacting with the user is done through console input and output. You display messages with `Console.WriteLine` and capture user input with `Console.ReadLine`.

```csharp
Console.WriteLine("Enter a number:");
int x = int.Parse(Console.ReadLine()); // Reads input and converts it to an integer.
Console.WriteLine("You entered: " + x);
```
### Explanation:
- **Console.WriteLine:** Prints messages to the screen.
- **Console.ReadLine:** Reads input as a string from the keyboard.
- **int.Parse:** Converts the string input into an integer so you can perform numerical operations.

### Reading Multiple Values

This code reads several values entered on one line (separated by spaces).

```csharp
string[] input = Console.ReadLine().Split();
int a = int.Parse(input[0]);
int b = int.Parse(input[1]);
```
### Explanation:
- **Split():** Breaks the input string into parts wherever there is a space.
- **Usage:** Helpful when you need to read multiple numbers at once, such as coordinates or multiple parameters.

---

## 2️⃣ Loops & Conditions

**Conditions** (if-else) and **loops** (for, while, do-while) are used to control the flow of your program.

### If-Else Statement:
```csharp
if (x > 0) 
    Console.WriteLine("Positive");
else if (x < 0) 
    Console.WriteLine("Negative");
else 
    Console.WriteLine("Zero");
```
### Explanation:
- **If-Else:** Checks conditions and runs different code blocks based on whether the condition is true or false.
- **Usage:** Use this when you need to make decisions, such as verifying if a number is positive, negative, or zero.

### Loops:

Loops let you repeat actions multiple times.

#### For Loop:
```csharp
for (int i = 0; i < 5; i++) 
    Console.WriteLine(i); // Prints numbers from 0 to 4.
```
#### While Loop:
```csharp
int j = 0;
while (j < 5) { 
    Console.WriteLine(j); 
    j++; 
}
```
#### Do-While Loop:
```csharp
int k = 0;
do { 
    Console.WriteLine(k); 
    k++; 
} while (k < 5);
```
### Explanation:
- **For Loop:** Ideal when you know in advance how many times the loop should run.
- **While Loop:** Continues looping as long as a condition remains true.
- **Do-While Loop:** Always runs at least once, then checks the condition.
- **Usage:** Choose the type of loop based on whether you need to execute the loop a set number of times or until a condition changes.

---

## 3️⃣ Strings in C#

**Strings** are used to handle text. This section covers common operations you might perform on strings.

### Accessing Characters:
```csharp
string s = "Hello";
char firstChar = s[0];           // 'H'
char lastChar = s[s.Length - 1];   // 'o'
```
### Explanation:
- **Accessing Characters:**  
  Use indices (positions) to retrieve specific characters from a string. Indexes start at 0.

### String Methods:
```csharp
string s1 = "Hello";
string s2 = "World";

// Concatenation: Joining two strings.
string result = s1 + " " + s2; // "Hello World"

// Substring: Extracting part of a string.
string part = s1.Substring(1, 3); // "ell"

// Convert to char array: Useful for manipulating individual characters.
char[] charArray = s1.ToCharArray();

// Reverse a string:
char[] arr = s1.ToCharArray();
Array.Reverse(arr);
string reversed = new string(arr); // "olleH"

// Check if two strings are equal (case-sensitive)
bool isEqual = s1.Equals(s2); // false
```
### Explanation:
- **Concatenation:** Combines strings to form a new one.
- **Substring:** Extracts a segment from the string.
- **ToCharArray:** Converts the string into an array of characters.
- **Equals:** Compares two strings for equality.
- **Usage:** These methods are essential for text manipulation tasks, such as formatting output or processing user input.

---

## 4️⃣ Arrays in C#

**Arrays** are collections that hold multiple items of the same type. They have a fixed size, which means you must know the number of elements in advance.

### 1D Array (Single Dimension)
```csharp
int[] arr = new int[5]; // Creates an array with 5 elements.
int[] nums = {1, 2, 3, 4, 5}; // An array with pre-initialized values.

// Loop through array using a for loop.
for (int i = 0; i < nums.Length; i++) 
    Console.WriteLine(nums[i]);

// Loop through array using foreach.
foreach (int num in nums) 
    Console.WriteLine(num);
```
### Explanation:
- **1D Array:** Use when you need a simple list of items.
- **For vs. Foreach:**  
  Use `for` when you need the index; use `foreach` for simpler iteration when you only need the value.

### 2D Arrays (Matrix)
```csharp
int[,] matrix = new int[3, 3] // Creates a 3x3 matrix.
{
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// Accessing an element in the matrix.
int val = matrix[1, 1]; // Retrieves the element 5

// Looping through the 2D array.
for (int i = 0; i < 3; i++)
{
    for (int j = 0; j < 3; j++)
        Console.Write(matrix[i, j] + " ");
    Console.WriteLine();
}
```
### Explanation:
- **2D Array:** Think of it as a grid or table.  
  Use it for data naturally organized in rows and columns.
- **Usage:** Nested loops allow you to work through each element in the grid.

---

## 5️⃣ Lists (Dynamic Arrays)

**Lists** are like arrays, but they can change in size during program execution. They’re useful when you don’t know the number of elements ahead of time.

### Code Example:
```csharp
List<int> numbers = new List<int> {1, 2, 3};
numbers.Add(4);       // Adds an element to the list.
numbers.Remove(2);    // Removes the element with the value 2.
numbers.Sort();       // Sorts the list in ascending order.

foreach (int num in numbers) 
    Console.Write(num + " ");
```
### Explanation:
- **Dynamic Size:** Lists automatically resize as you add or remove items.
- **Usage:** Ideal for collections where the number of elements might change.

---

## 6️⃣ Dictionary (Key-Value Pairs)

A **Dictionary** stores data as key-value pairs. It allows you to quickly look up a value based on its unique key.

### Code Example:
```csharp
Dictionary<string, int> ages = new Dictionary<string, int>();
ages["Alice"] = 25;
ages["Bob"] = 30;

Console.WriteLine(ages["Alice"]); // Outputs: 25
```
### Explanation:
- **Key-Value Pair:**  
  Use a dictionary when you need to associate and retrieve data by a unique identifier.
- **Fast Lookups:** They offer quick access to values using keys.

---

## 7️⃣ Math Functions

The `Math` class in C# provides a range of mathematical functions that simplify common operations.

### Code Example:
```csharp
using System;  
Console.WriteLine(Math.Max(10, 20)); // Returns 20: The larger of two numbers.
Console.WriteLine(Math.Min(10, 20)); // Returns 10: The smaller of two numbers.
Console.WriteLine(Math.Sqrt(16));    // Returns 4: The square root of 16.
Console.WriteLine(Math.Pow(2, 3));    // Returns 8: 2 raised to the power of 3.
Console.WriteLine(Math.Abs(-5));      // Returns 5: The absolute value of -5.
Console.WriteLine(Math.Round(3.6));   // Rounds 3.6 to 4.
Console.WriteLine(Math.Floor(3.9));   // Rounds 3.9 down to 3.
Console.WriteLine(Math.Ceiling(3.1)); // Rounds 3.1 up to 4.
```
### Explanation:
- **Math Functions:**  
  They help perform common mathematical operations quickly.
- **Usage:** Utilize these functions for calculations like finding maximum/minimum values, square roots, powers, and rounding numbers.

---

## 8️⃣ Bitwise Operations

**Bitwise operations** allow you to work directly with the binary representation of numbers. They are useful in low-level programming and optimizations.

### Code Example:
```csharp
int a = 5, b = 3; // In binary: 5 = 101, 3 = 011
Console.WriteLine(a & b); // Bitwise AND: 101 & 011 gives 001 (1)
Console.WriteLine(a | b); // Bitwise OR: 101 | 011 gives 111 (7)
Console.WriteLine(a ^ b); // Bitwise XOR: 101 ^ 011 gives 110 (6)
Console.WriteLine(~a);    // Bitwise NOT: Inverts the bits of 101, resulting in -6 (using two's complement)
Console.WriteLine(a << 1); // Left shift: Shifts bits left, multiplying by 2 (result 10)
Console.WriteLine(a >> 1); // Right shift: Shifts bits right, dividing by 2 (result 2)
```
### Explanation:
- **Bitwise Operators:**  
  - **AND (&):** Compares each bit of two numbers.
  - **OR (|):** Combines bits where at least one is 1.
  - **XOR (^):** Sets bits to 1 only if one of the bits is 1.
  - **NOT (~):** Inverts all the bits.
  - **Left/Right Shift (<<, >>):** Shifts bits left or right.
- **Usage:** Use these for tasks like low-level data manipulation, performance optimizations, or when working with binary data.

---

## 9️⃣ Recursion in C#

**Recursion** is a technique where a function calls itself to solve smaller instances of the same problem. It is often used in problems that can be divided into similar sub-problems, such as calculating factorials or Fibonacci numbers.

### Factorial Using Recursion:
```csharp
int Factorial(int n)
{
    if (n == 0) return 1; // Base case: factorial of 0 is 1.
    return n * Factorial(n - 1); // Recursive call: multiplies n by factorial of (n-1).
}
Console.WriteLine(Factorial(5)); // Outputs: 120
```
### Explanation:
- **Factorial:** Multiplies all positive integers up to `n`.
- **Base Case:** Stops the recursion when `n` reaches 0.
- **Usage:** Great for problems that naturally break down into similar smaller tasks.

### Fibonacci Using Recursion:
```csharp
int Fibonacci(int n)
{
    if (n <= 1) return n; // Base case: returns n when n is 0 or 1.
    return Fibonacci(n - 1) + Fibonacci(n - 2); // Recursive call: sum of the two preceding numbers.
}
```
### Explanation:
- **Fibonacci Sequence:** Each number is the sum of the two previous numbers.
- **Usage:** Demonstrates recursion by breaking the problem into smaller, similar problems.

---

## Sorting Algorithms

### Bubble Sort

Bubble sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order.

```csharp
void BubbleSort(int[] arr)
{
    int n = arr.Length;
    for (int i = 0; i < n - 1; i++)
    {
        for (int j = 0; j < n - i - 1; j++)
        {
            if (arr[j] > arr[j + 1])
            {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}
```
### Explanation:
- **Bubble Sort:**  
  A simple method to sort an array by repeatedly swapping adjacent elements if they are in the wrong order.
- **Usage:** Best for educational purposes or small data sets due to its simplicity.

---

## Searching Algorithms

### Binary Search (O(log n))

Binary search is an efficient algorithm to search for an element in a sorted array. It works by repeatedly dividing the search range in half.

```csharp
int BinarySearch(int[] arr, int x)
{
    int left = 0, right = arr.Length - 1;
    while (left <= right)
    {
        int mid = left + (right - left) / 2;
        if (arr[mid] == x) return mid;
        else if (arr[mid] < x) left = mid + 1;
        else right = mid - 1;
    }
    return -1; // Returns -1 if the element is not found.
}
```
### Explanation:
- **Binary Search:**  
  Requires a sorted array and works by comparing the target with the middle element.
- **Efficiency:** Reduces the search area by half each time, making it very fast for large arrays.
- **Usage:** Use when you need to quickly locate an element in a sorted collection.

---

## Quick Summary

✔ Variables & Input/Output  
✔ Loops & Conditions  
✔ String Operations  
✔ Arrays & Lists  
✔ Dictionary (Key-Value Pairs)  
✔ Math Functions  
✔ Recursion & Sorting  
✔ Binary Search

---

This quick revision guide covers essential C# concepts and demonstrates how and where to use them in solving algorithmic problems. Use this as a reference to refresh your understanding and practice coding in C#. 📚 Happy Coding! 🎯
