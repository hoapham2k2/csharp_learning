# Reference type and Value type

## Overview

- Here is some of the **value types** in C#:

  - numeric types: `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`.
  - `bool`, `struct`, `enum`.
  - `Nullable<T>`.
    
  - Let's see an example of a value type:

    ```csharp
    public Struct Point
    {
        public int x;
        public int y;
    }

    Point p1 = new Point();
    p1.x = 10;

    Point p2 = p1;
    p2.x = 20;

    Console.WriteLine(p1.x); // Output: 10
    Console.WriteLine(p2.x); // Output: 20
    ```

    In the above example, the value of `p1` is not changed when we change the value of `p2`. This is because `Point` is a value type. When we assign `p1` to `p2`, the value of `p1` is **copied to** `p2`. The more accurate term would be that the memory location of `p1` is copied to `p2`. So, `p1` and `p2` are pointing to different memory locations. So, if we change the value of `p2`, the value of `p1` will not be changed.

- Here is some of the **reference types** in C#:

  - `class`, `interface`, `delegate`, `object`, `string`, `dynamic`, `array`.
  - Let's see an example of a reference type:

  ```csharp
    public class Point
    {
        public int x;
        public int y;
    }

    Point p1 = new Point();
    p1.x = 10;

    Point p2 = p1;
    p2.x = 20;

    Console.WriteLine(p1.x); // Output: 20
    Console.WriteLine(p2.x); // Output: 20
  ```

  In the above example, the value of `p1` is changed when we change the value of `p2`. This is because `Point` is a reference type. When we assign `p1` to `p2`, the memory location of `p1` **assigned to** `p2`. So, `p1` and `p2` are pointing to the same memory location. So, if we change the value of `p2`, the value of `p1` will be changed.

## Stack and Heap Memory

In C#, data are stored in two types of memory: **Stack** and **Heap**.

- The **Stack** is used for static memory allocation, or in other words, that data we unequivocally know the size of at compile time.
- The **Heap** is used for dynamic memory allocation, those size of data could be scaled at runtime.

## Value type and Reference type in Stack and Heap Memory

- when we declare a **value type** variable, the **Stack** memory will be allocated to store the value of the variable.

- when we declare a **reference type** variable, the **Stack** memory will be allocated to store the reference of the variable, and the **Heap** memory will be allocated to store the value of the variable. So in runtime, wheather the value size of the variable is changed, the **Heap** memory will be changed, and the **Stack** memory only hold the pointer/reference to the **Heap** memory.
