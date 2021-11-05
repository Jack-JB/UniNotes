# Week 5 - Algorithm Design

----

**Design Strategies** Concern algorithm and code development at a more abstract level that that of its implementation. They are established approaches for designing algorithms/they all have their own strengths and weaknesses.

- **Brute force:** Check all possible solutions, determine the right/best one
- **Greedy algorithms:** build the solution step by step.
- Decomposition by **divide and conquer** or by dynamic programming

## Brute Force

* **Initial Analysis:** what is the **space of all conceivable solutions** to the problem, for the given input? Check all parameters/options and devise a scheme that iterates over all the permitted values and their combinations.

* **Brute force design strategy:** Evaluate all potential solutions, one by one.

* Strengths of the strategy: The code is easy to write, and it is easy to prove that it is correct. Beyond the initial analysis, not much needs to be figured out.

* Weakness of the strategy: reusing information might reduce the relevant number of candidate solutions. This is not done; instead, all are tried out.

* While there are some problems that can be addressed in this way, most cannot; the space of solutions that need to be enumerated usually grows too fast

  

-----

## Greedy Algorithms

**Greedy algorithms** are based on the idea of making the **best local improvement** (i.e., the best immediately visible small change) to a partial solution. they consider **one candidate solution** only and build it up gradually.

**Strength:** Systematic and easy to implement.

**Weakness:** it does not solve all problems correctly; but even then, it might return an acceptable suboptimal result or an approximation to the solution.

## Limitations of greedy algorithms

Constructing a solution incrementally, step by step, is not always correct.

Greedy algorithms will produce an incorrect or suboptimal result whenever the overall ("global") solution does not consist of parts that are best 'locally.'

-----

## Divide and conquer

**Decomposition** breaks a problem down into smaller subtasks. For the two decomposition techniques discussed today, divide-and-conquer and dynamic programming, subtasks are **subproblems:** Smaller versions of the problem

The solution of a subproblem then is a **partial solution** for the whole problem.

* First **divide**
* Then **conquer**
* Finally **combine** the results

In divide-and-conquer, subproblems do not overlap (or they are assumed not to overlap). Each subproblem occurs once, and hence, **each partial solution is used only once.** It need not be stored anywhere beyond its single use.

## Limitations of divide and conquer

Where the decomposition of a problem into smaller parts leads to mutually **overlapping subproblems**, divide and conquer (e.g., implemented by multiple recursion) might recompute the same partial solution many times.

To improve the decomposition efficiency in such cases, it can help to store and recall **partial solutions**. This strategy is called **dynamic programming**.





