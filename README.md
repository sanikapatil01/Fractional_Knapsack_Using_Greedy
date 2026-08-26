# Fractional Knapsack Problem Using Greedy Algorithm

## 1. Aim

To design and implement the Fractional Knapsack Problem using the Greedy Algorithm in C++ to maximize the total profit within a given knapsack capacity.

---

## 2. Problem Statement

The Fractional Knapsack Problem is an optimization problem in which a set of items is given. Each item has a specific weight and profit, and the knapsack has a limited capacity.

The objective is to select items in such a way that the maximum possible profit is obtained without exceeding the capacity of the knapsack.

Unlike the 0/1 Knapsack Problem, the Fractional Knapsack Problem allows us to take a fraction of an item.

The selection of items is based on the Profit/Weight ratio.

---

## 3. Objective

The objectives of this project are:

- To understand the Greedy Algorithm.
- To implement the Fractional Knapsack Problem in C++.
- To calculate the Profit/Weight ratio of each item.
- To sort items according to their Profit/Weight ratio.
- To select items with the highest ratio first.
- To allow fractional selection of an item.
- To maximize the total profit.
- To analyze the time and space complexity of the algorithm.

---

## 4. Algorithm Used

### Greedy Algorithm

The Fractional Knapsack Problem is solved using a Greedy approach.

For each item, the following ratio is calculated:

    Profit/Weight Ratio = Profit / Weight

The items are then sorted in descending order of Profit/Weight ratio.

The item with the highest ratio is selected first because it provides the maximum profit for every unit of weight.

If the complete item cannot fit into the remaining capacity, a fraction of that item is selected.

---

## 5. Working of the Algorithm

The algorithm follows these steps:

1. Read the number of items.
2. Read the weight and profit of every item.
3. Calculate the Profit/Weight ratio.
4. Sort all items in descending order of their ratio.
5. Initialize the remaining knapsack capacity.
6. Select items one by one.
7. If the complete item fits into the remaining capacity, take the complete item.
8. If the complete item does not fit, take the required fraction of the item.
9. Calculate the weight taken and profit obtained.
10. Continue until the knapsack becomes full.
11. Display the selected items and maximum profit.

---

## 6. Pseudocode

    FRACTIONAL_KNAPSACK(items, capacity)

        FOR each item
            ratio = item.profit / item.weight

        SORT items in descending order of ratio

        totalProfit = 0
        remainingCapacity = capacity

        FOR each item

            IF remainingCapacity == 0
                BREAK

            IF item.weight <= remainingCapacity

                Take complete item

                fraction = 1

                weightTaken = item.weight

                profitTaken = item.profit

                remainingCapacity =
                    remainingCapacity - item.weight

                totalProfit =
                    totalProfit + item.profit

            ELSE

                fraction =
                    remainingCapacity / item.weight

                weightTaken =
                    remainingCapacity

                profitTaken =
                    item.profit * fraction

                totalProfit =
                    totalProfit + profitTaken

                remainingCapacity = 0

        RETURN totalProfit

---

## 7. Example

Consider the following items:

| Item | Weight | Profit | Profit/Weight Ratio |
|------|-------:|-------:|--------------------:|
| 1 | 10 | 60 | 6.00 |
| 2 | 20 | 100 | 5.00 |
| 3 | 30 | 120 | 4.00 |

### Knapsack Capacity

    50

---

## 8. Calculate Profit/Weight Ratio

For each item:

    Item 1:
    60 / 10 = 6.00

    Item 2:
    100 / 20 = 5.00

    Item 3:
    120 / 30 = 4.00

Therefore, the items are arranged as:

    Item 1 → Ratio = 6.00
    Item 2 → Ratio = 5.00
    Item 3 → Ratio = 4.00

---

## 9. Item Selection Process

### Item 1

Weight = 10

Profit = 60

The complete item fits into the knapsack.

    Weight Taken = 10
    Profit Gained = 60
    Remaining Capacity = 50 - 10 = 40

### Item 2

Weight = 20

Profit = 100

The complete item fits into the remaining capacity.

    Weight Taken = 20
    Profit Gained = 100
    Remaining Capacity = 40 - 20 = 20

### Item 3

Weight = 30

Profit = 120

Only 20 units of capacity remain, so the complete item cannot be taken.

Fraction taken:

    Fraction = Remaining Capacity / Item Weight
             = 20 / 30
             = 0.667
             = 66.67%

Profit obtained:

    Profit = 120 × (20 / 30)
           = 80

Therefore:

    Weight Taken = 20
    Profit Gained = 80

---

## 10. Final Selection

| Item | Fraction Taken | Weight Taken | Profit Taken |
|------|---------------:|-------------:|-------------:|
| 1 | 1.00 | 10 | 60 |
| 2 | 1.00 | 20 | 100 |
| 3 | 0.67 | 20 | 80 |

### Total Weight

    10 + 20 + 20 = 50

### Maximum Profit

    60 + 100 + 80 = 240

Therefore:

    Maximum Profit = 240

---

## 11. Time Complexity Analysis

Suppose there are n items.

### Calculating Profit/Weight Ratio

The ratio is calculated once for each item:

    O(n)

### Sorting

The items are sorted according to the Profit/Weight ratio:

    O(n log n)

### Selecting Items

The sorted items are traversed once:

    O(n)

Therefore:

    O(n) + O(n log n) + O(n)

The sorting operation dominates the overall complexity.

### Overall Time Complexity

    O(n log n)

---

## 12. Space Complexity

The item information is stored using an array or vector.

Therefore:

    Space Complexity = O(n)

Additional variables such as capacity, fraction, total profit, and weight taken require:

    O(1)

The overall space complexity for the implementation is:

    O(n)

---

## 13. Comparison with 0/1 Knapsack

| Feature | Fractional Knapsack | 0/1 Knapsack |
|---------|---------------------|--------------|
| Items can be divided | Yes | No |
| Fraction of item allowed | Yes | No |
| Common approach | Greedy | Dynamic Programming |
| Greedy gives optimal solution | Yes | No |
| Time Complexity | O(n log n) | O(n × W) using DP |
| Selection method | Profit/Weight ratio | Optimal combination |

The main difference is that Fractional Knapsack allows an item to be divided, while 0/1 Knapsack allows only two choices: take the complete item or do not take it.

---

## 14. Sample Input

    =============================================
           FRACTIONAL KNAPSACK PROBLEM
    =============================================

    Enter number of items: 3

    Enter knapsack capacity: 50

    Enter weight and profit of each item:

    Item 1:
    Weight: 10
    Profit: 60

    Item 2:
    Weight: 20
    Profit: 100

    Item 3:
    Weight: 30
    Profit: 120

---

## 15. Sample Output

    =============================================
           ITEMS SORTED BY PROFIT/WEIGHT RATIO
    =============================================

    Item    Weight      Profit      P/W Ratio
    ---------------------------------------------------
    1       10.00       60.00       6.00
    2       20.00       100.00      5.00
    3       30.00       120.00      4.00


    =============================================
              KNAPSACK SELECTION PROCESS
    =============================================

    Item 1 -> FULL ITEM TAKEN
    Weight Taken : 10.00
    Profit Gained: 60.00
    Remaining Capacity: 40.00

    Item 2 -> FULL ITEM TAKEN
    Weight Taken : 20.00
    Profit Gained: 100.00
    Remaining Capacity: 20.00

    Item 3 -> FRACTION TAKEN
    Fraction Taken: 66.67%
    Weight Taken: 20.00
    Profit Gained: 80.00
    Remaining Capacity: 0.00


    =============================================
                  FINAL RESULT
    =============================================

    Item    Fraction    Weight Taken    Profit Taken
    ---------------------------------------------------
    1       1.00        10.00            60.00
    2       1.00        20.00            100.00
    3       0.67        20.00            80.00

    ---------------------------------------------
    Knapsack Capacity : 50.00
    Total Weight Used : 50.00
    Remaining Capacity: 0.00
    Maximum Profit    : 240.00
    ---------------------------------------------

The complete program execution output is stored in:

    output.txt

---

## 16. Advantages

- Simple and easy to implement.
- Efficient for large numbers of items.
- Provides an optimal solution for Fractional Knapsack.
- Uses a straightforward Greedy strategy.
- Allows partial selection of items.
- Has an overall time complexity of O(n log n).
- Uses the available capacity efficiently.

---

## 17. Limitations

- The Greedy approach does not guarantee an optimal solution for the 0/1 Knapsack Problem.
- Sorting is required before the selection process.
- Additional memory is required to store item information.
- The problem assumes that items can be divided into fractions.

---

## 18. Applications

The Fractional Knapsack concept can be applied in:

- Cargo loading
- Resource allocation
- Budget allocation
- Storage optimization
- Bandwidth allocation
- Investment allocation
- Supply chain optimization
- Capacity planning

---

## 19. Technologies Used

- Programming Language: C++
- Algorithm: Greedy Algorithm
- Problem: Fractional Knapsack
- Data Structure: Array / Vector
- IDE: Visual Studio Code
- Version Control: Git and GitHub

---

## 20. Key Features

- Implements Fractional Knapsack using the Greedy approach.
- Calculates Profit/Weight ratio.
- Sorts items based on the ratio.
- Selects complete items whenever possible.
- Allows fractional selection of items.
- Calculates the fraction taken from an item.
- Calculates weight taken from each item.
- Calculates profit obtained from each item.
- Displays remaining knapsack capacity.
- Displays maximum achievable profit.
- Provides O(n log n) time complexity.

---

## 21. Project Structure

    Fractional-Knapsack/
    │
    ├── fractional_knapsack.cpp
    │   └── C++ implementation of Fractional Knapsack
    │
    ├── output.txt
    │   └── Complete program execution output
    │
    └── README.md
        └── Project documentation

---

## 22. How to Run the Program

### Step 1: Open the project in VS Code

Open the Fractional Knapsack project folder.

### Step 2: Open the Terminal

Go to:

    Terminal → New Terminal

### Step 3: Compile the Program

Using g++:

    g++ fractional_knapsack.cpp -o fractional_knapsack

### Step 4: Run the Program

On Windows:

    .\fractional_knapsack

### Step 5: Enter the Input

Enter:

- Number of items
- Knapsack capacity
- Weight of each item
- Profit of each item

### Step 6: View the Output

The program displays:

- Items sorted by Profit/Weight ratio
- Selection process
- Fraction taken
- Weight taken
- Profit gained
- Remaining capacity
- Maximum profit

---

## 23. Conclusion

The Fractional Knapsack Problem was successfully implemented in C++ using the Greedy Algorithm.

The algorithm calculates the Profit/Weight ratio of every item and sorts the items in descending order of this ratio. Items with the highest profit per unit of weight are selected first. If an item cannot completely fit into the remaining capacity, the required fraction of that item is selected.

The algorithm achieves an overall time complexity of O(n log n) due to sorting and requires O(n) space for storing the item information.

This project demonstrates the practical application of the Greedy Algorithm to an optimization problem and shows how selecting the locally best option can produce the optimal solution when fractional selection is allowed.

---

## 24. Author

Student Project - Data Structures and Algorithms

Language: C++

Algorithm: Greedy Algorithm

Problem: Fractional Knapsack