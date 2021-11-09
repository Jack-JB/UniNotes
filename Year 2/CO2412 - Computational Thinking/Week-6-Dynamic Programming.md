# Dynamic Programming

## Divide and Conquer: Limitations

Where the decomposition of a problem into smaller parts leads to mutually **overlapping subproblems**, divide-and-conquer (e.g., implemented by multiple recursion) might recompute the same partial solution many times.

> Fibonacci Sequence
>
> F0 = 0
>
> F1 = 1
>
> F~k~ = F~K-1~ + K ~-2~, for k > 1

To improve the decomposition efficiency in such cases, it can help to store and recall **partial solutions**. This strategy is called **<u>Dynamic Programming</u>**

<img src="D:\UniNotes\Year 2\CO2412 - Computational Thinking\images\image-20211109162305167.png" alt="image-20211109162305167" style="zoom: 80%;" />

## Divide and conquer vs. Dynamic programming

**Divide and conquer:**

- **Subproblems do not overlap**, there is a genuine split into subproblems
- The partial solutions (to subproblems) **do not need to be remembered**
- Each partial solution **is used only once**, when it is combined with one or multiple other partial solutions in a single specific way.

**Dynamic programming:**

- Partial solutions are **stored and recalled** when required.
- There is the option (and expectation) that **subproblems overlap**.
- Therefore, the same partial solution can be **used multiple times**, and it  can be combined with other partial solutions in a variety of ways.

## Data Structures

### Static Arrays

An array contains a sequence of elements of the same type, arranged **contiguously in memory.**

In C/C++ the type of an array such as int[] is the same as the corresponding pointer type int*, i.e., **the array actually is a pointer**. Its value is an address at which an integer is stored, namely, the memory address of the first element.

> **Static data structures** can only change their content,  i.e., the values of their  elements. Once they are allocated, their size and structure cannot change.

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211109163044583.png" alt="image-20211109163044583" style="zoom: 50%;" />

Above, `*x` would evaluate to `34` and so would `x[0]`.

The expression `*(x+4)` would evaluate to `4`, and so would `x[4]`.

In Python, numpy can be used to create an array,  e.g.

```python
x = np.array([34, 1, 7, 12, 3, 4, 7, 12])
```

### Dynamic Arrays

Conventional arrays are **static data structures**. Their size in memory is constant,  and memory needs to be allocated only once, e.g., at declaration time. (Details  depend on programming language, compiler, flags/optimization level, etc.). 

<u>Dynamic data structures can change in size and/or structure at runtime.</u> For an  array, this can be implemented by **allocating reserve memory** for any elements  that may be appended in the future. When the capacity of the dynamic array is exhausted, all of its contents need to be shifted to another position in memory.

> Note: More memory is allocated than strictly needed. <br>Like before, the elements are contiguously arranged in memory.

## Efficiency analysis

- Read/write access to an array element: O(1) time
  - Address of the i-th element computable by pointer arithmetic
- Deleting an element from the array: O(1) at the end, O(n) elsewhere
  - All the elements with greater indices need to be shifted
- Extending the array by one element: O(1) at the end, if there is capacity
  - O(n) elsewhere, or if the capacity of the dynamic array is exhausted

## Python Lists

**Lists in Python are implemented as dynamic arrays.** Their elements behave in the same was as Python variables do in general: For elementary data types such as numbers, they contain the value.

```python	
x = list(range(7))
y = x[2: 4]
y[0] = 7

print("x = ", x)
print ("y = ", y
       
# x = [0, 1, 2, 3, 4, 5, 6]
#y = [7, 3]
```

```python
x = [[i] for i in range(7)]
y = x[2: 4]
y[0] = 7
y[0].pop()
y[0].append(7)
print("x = ", x)
print ("y = ", y)

# x = [[0], [1], [2], [3], [4], [5], [6]]
#y = [7, 3]
```

When a sublist `x[i:j]` is created from `x`, **all the sublist elements are copied*.

