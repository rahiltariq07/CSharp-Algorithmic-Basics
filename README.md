# C# Algorithmic Basics 🚀

This repository contains a **quick revision** of essential C# concepts required for solving **algorithmic problems**. It covers variables, loops, strings, arrays, recursion, sorting, searching, and bitwise operations with code examples.

## 📌 Topics Covered

## **1️⃣ Variables and Data Types**  
In C#, you must declare variables with a type.  
```csharp
int num = 10;       // Integer
double pi = 3.14;   // Double (decimal)
char letter = 'A';  // Single character
string name = "John"; // String (text)
bool isTrue = true; // Boolean (true/false)
```
- **Input and Output**
  ```csharp
  Console.WriteLine("Enter a number:");
  int x = int.Parse(Console.ReadLine()); // Reads input and converts to int
  Console.WriteLine("You entered: " + x);
  ```
- **Reading multiple values** (space-separated)
  ```csharp
  string[] input = Console.ReadLine().Split();
  int a = int.Parse(input[0]);
  int b = int.Parse(input[1]);
  ```

---

## **2️⃣ Loops & Conditions**  
**If-Else:**  
```csharp
if (x > 0) Console.WriteLine("Positive");
else if (x < 0) Console.WriteLine("Negative");
else Console.WriteLine("Zero");
```

**Loops:**  
```csharp
for (int i = 0; i < 5; i++) Console.WriteLine(i); // 0 to 4

int j = 0;
while (j < 5) { Console.WriteLine(j); j++; }

int k = 0;
do { Console.WriteLine(k); k++; } while (k < 5);
```

---

## **3️⃣ Strings in C#**  
**Accessing Characters:**  
```csharp
string s = "Hello";
char firstChar = s[0]; // 'H'
char lastChar = s[s.Length - 1]; // 'o'
```

**String Methods:**  
```csharp
string s1 = "Hello";
string s2 = "World";

// Concatenation
string result = s1 + " " + s2; // "Hello World"

// Substring
string part = s1.Substring(1, 3); // "ell"

// Convert to char array
char[] charArray = s1.ToCharArray();

// Reverse a string
char[] arr = s1.ToCharArray();
Array.Reverse(arr);
string reversed = new string(arr); // "olleH"

// Check if two strings are equal (case-sensitive)
bool isEqual = s1.Equals(s2); // false
```

---

## **4️⃣ Arrays in C#**
### **1D Array (Single Dimension)**
```csharp
int[] arr = new int[5]; // Array of size 5
int[] nums = {1, 2, 3, 4, 5}; // Pre-initialized array

// Loop through array
for (int i = 0; i < nums.Length; i++) Console.WriteLine(nums[i]);

// Using foreach
foreach (int num in nums) Console.WriteLine(num);
```

### **2D Arrays (Matrix)**
```csharp
int[,] matrix = new int[3, 3] // 3x3 matrix
{
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// Accessing elements
int val = matrix[1, 1]; // 5

// Looping through 2D array
for (int i = 0; i < 3; i++)
{
    for (int j = 0; j < 3; j++)
        Console.Write(matrix[i, j] + " ");
    Console.WriteLine();
}
```

---

## **5️⃣ Lists (Dynamic Arrays)**
Unlike arrays, **Lists** are resizable.
```csharp
List<int> numbers = new List<int> {1, 2, 3};
numbers.Add(4); // Add element
numbers.Remove(2); // Remove element
numbers.Sort(); // Sort elements

foreach (int num in numbers) Console.Write(num + " ");
```

---

## **6️⃣ Dictionary (Key-Value Pairs)**
Useful for **fast lookups** (O(1) average time).
```csharp
Dictionary<string, int> ages = new Dictionary<string, int>();
ages["Alice"] = 25;
ages["Bob"] = 30;

Console.WriteLine(ages["Alice"]); // 25
```

---

## **7️⃣ Math Functions**  
```csharp
using System;  
Console.WriteLine(Math.Max(10, 20)); // 20
Console.WriteLine(Math.Min(10, 20)); // 10
Console.WriteLine(Math.Sqrt(16)); // 4
Console.WriteLine(Math.Pow(2, 3)); // 8
Console.WriteLine(Math.Abs(-5)); // 5
Console.WriteLine(Math.Round(3.6)); // 4
Console.WriteLine(Math.Floor(3.9)); // 3
Console.WriteLine(Math.Ceiling(3.1)); // 4
```

---

## **8️⃣ Bitwise Operations**
Great for optimization & low-level programming.
```csharp
int a = 5, b = 3; // 5 = 101, 3 = 011
Console.WriteLine(a & b); // AND (101 & 011) → 001 = 1
Console.WriteLine(a | b); // OR  (101 | 011) → 111 = 7
Console.WriteLine(a ^ b); // XOR (101 ^ 011) → 110 = 6
Console.WriteLine(~a); // NOT (~101) → -6
Console.WriteLine(a << 1); // Left shift (5 << 1) → 10
Console.WriteLine(a >> 1); // Right shift (5 >> 1) → 2
```

---

## **9️⃣ Recursion in C#**
Recursion is useful for problems like factorial, Fibonacci, and DFS.

💡 **Factorial Using Recursion**
```csharp
int Factorial(int n)
{
    if (n == 0) return 1;
    return n * Factorial(n - 1);
}
Console.WriteLine(Factorial(5)); // 120
```

💡 **Fibonacci Using Recursion**
```csharp
int Fibonacci(int n)
{
    if (n <= 1) return n;
    return Fibonacci(n - 1) + Fibonacci(n - 2);
}
```

---

## **🔟 Sorting Algorithms**
### **Bubble Sort**
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

---

## **🔢 Searching Algorithms**
### **Binary Search (O(log n))**
💡 **Search for `x` in a sorted array**
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
    return -1; // Not found
}
```

---

## **🔥 Quick Summary**
✔ **Variables & Input/Output**  
✔ **Loops & Conditions**  
✔ **String Operations**  
✔ **Arrays & Lists**  
✔ **Dictionary (HashMap)**  
✔ **Math Functions**  
✔ **Recursion & Sorting**  
✔ **Binary Search**  

---

This repo serves as a **quick revision guide** for solving C# algorithmic problems. 📚 Happy Coding! 🎯

Sure! Here's a **quick revision of C# basics** that will help you solve algorithmic problems efficiently. 🚀   
