# Algorithms Homework: Greedy Algorithms and Dynamic Programming

This repository contains implementations of two algorithmic problems:
1. 3D Printer Queue Optimization (Greedy Algorithm)
2. Rod Cutting Problem (Dynamic Programming)

## Task 1: 3D Printer Queue Optimization

### Problem Description
The task is to optimize a queue of 3D printing jobs for a university laboratory, considering priorities and technical constraints of the printer. Each printing job has an ID, volume, priority, and printing time. The goal is to group models for simultaneous printing while respecting the printer's constraints and prioritizing higher-priority jobs.

### Implementation Approach
The solution uses a greedy algorithm with the following steps:
1. Convert input dictionaries to `PrintJob` objects
2. Sort jobs by priority (lower number = higher priority)
3. Group jobs for simultaneous printing while respecting constraints:
   - Maximum number of items per group
   - Maximum total volume per group
4. Calculate the print order and total time, where:
   - The time for a group is the maximum print time of any job in the group
   - The total time is the sum of all group times

### Priorities
- 1 (highest): Thesis/diploma projects
- 2: Laboratory work
- 3 (lowest): Personal projects

### How to Run
```bash
python task1.py
```

The program will run three test cases:
1. Models with the same priority
2. Models with different priorities
3. Models exceeding printer constraints

## Task 2: Rod Cutting Problem

### Problem Description
The rod cutting problem involves finding the optimal way to cut a rod to maximize profit. Given a rod of length `n` and a price list where `price[i]` is the price for a rod of length `i+1`, the task is to determine how to cut the rod to achieve maximum profit.

### Implementation Approaches
The solution implements two dynamic programming approaches:

#### 1. Memoization (Top-Down)
- Uses recursion with a memoization cache to avoid redundant calculations
- Builds the solution by solving smaller subproblems and caching their results
- Reconstructs the optimal cuts from the memoization cache

#### 2. Tabulation (Bottom-Up)
- Uses an iterative approach with tables to store intermediate results
- Builds the solution from the smallest subproblems to the largest
- Reconstructs the optimal cuts from the table

### How to Run
```bash
python task2.py
```

The program will run three test cases:
1. Basic case
2. Optimal not to cut
3. Uniform cuts

For each test case, both memoization and tabulation approaches are tested and their results are displayed.

## Requirements
- Python 3.6+
- Standard libraries: typing, dataclasses