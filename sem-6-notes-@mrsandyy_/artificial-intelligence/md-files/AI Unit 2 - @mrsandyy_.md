# **Unit 2: Advanced Search Methods & Knowledge Representation**

## **1. Heuristic Search Methods**

### **1.1 Definition**

A **heuristic search** is an informed search strategy that uses a **heuristic function** to estimate the best path to the goal. It improves search efficiency by guiding the search towards promising paths.

### **1.2 Characteristics**

- Uses **domain-specific knowledge** to make decisions.
- Reduces the number of states to explore.
- Often faster than uninformed search methods.

### **1.3 Examples of Heuristic Functions**

- **Manhattan Distance** in pathfinding problems.
- **Hamming Distance** in text comparison.

---

## **2. Generate and Test**

### **2.1 Definition**

A brute-force approach where **possible solutions are generated and tested** against the goal criteria.

### **2.2 Steps**

1. Generate a potential solution.
2. Test whether it satisfies the goal.
3. If successful, return the solution; otherwise, repeat.

### **2.3 Example**

Solving a **Sudoku puzzle** by trying different numbers and checking constraints.

---

## **3. Hill Climbing**

### **3.1 Definition**

A local search technique that **continuously moves in the direction of increasing value** (closer to the goal).

### **3.2 Steps**

1. Start from an initial state.
2. Evaluate the neighboring states.
3. Move to the neighbor with the highest value.
4. Repeat until a peak (local maximum) is reached.

### **3.3 Disadvantages**

- **Gets stuck in local maxima** (suboptimal solutions).
- May suffer from **plateaus and ridges** (flat regions where progress is slow).

---

## **4. Best-First Search**

### **4.1 Definition**

An informed search strategy that expands the **most promising node first**, using a heuristic function.

### **4.2 Algorithm**

1. Place the starting node in a priority queue.
2. Expand the node with the lowest heuristic cost.
3. Continue until the goal node is reached.

### **4.3 Example**

- **A* Algorithm**, which uses both the cost so far (**g(n)**) and the estimated cost to goal (**h(n)**).

---

## **5. Graph Search**

### **5.1 Definition**

A search technique that operates on a **graph-based problem representation**. It ensures efficient exploration by maintaining a record of visited nodes.

### **5.2 Types**

- **Depth-First Search (DFS)**
- **Breadth-First Search (BFS)**
- **A* Algorithm**

---

## **6. AND-OR Search Methods**

### **6.1 Definition**

A search method used in **decision-making problems** where **AND** represents multiple conditions that must be met, and **OR** represents alternative choices.

### **6.2 Example**

- **Game playing AI**, where a move may have multiple outcomes (OR) and some conditions must be satisfied together (AND).

---

## **7. Constraint Satisfaction Problems (CSP)**

### **7.1 Definition**

A problem-solving approach where solutions must satisfy a **set of constraints**.

### **7.2 Components**

1. **Variables**: Elements to be assigned values.
2. **Domain**: Possible values for each variable.
3. **Constraints**: Rules that must be satisfied.

### **7.3 Example**

- **Solving a Sudoku puzzle** with number placement constraints.

---

## **8. Backtracking**

### **8.1 Definition**

A search technique that **explores all possible solutions recursively** and **abandons paths** that violate constraints.

### **8.2 Steps**

1. Pick a possible solution.
2. If constraints are violated, backtrack to the previous step.
3. Repeat until a valid solution is found.

### **8.3 Example**

- **Solving N-Queens problem** by placing queens row by row and backtracking when a conflict arises.

---

## **9. List and String Processing**

### **9.1 Lists**

- Ordered collection of elements.
- Used in AI to store sequences of operations.

### **9.2 String Processing**

- Manipulation of character sequences (e.g., **pattern matching, text recognition**).

### **9.3 Applications**

- **Natural Language Processing (NLP)**.
- **Search algorithms** that process textual data.

---

## **10. Concept of Knowledge**

### **10.1 Definition**

Knowledge represents **facts, rules, and heuristics** used by AI systems for decision-making.

### **10.2 Types of Knowledge**

1. **Declarative Knowledge**: Facts and relationships.
2. **Procedural Knowledge**: Steps and rules to solve problems.

---

## **11. Logic in AI**

### **11.1 Definition**

Logic is the **mathematical foundation** that allows AI to **reason and make decisions**.

### **11.2 Types of Logic**

1. **Propositional Logic**: Deals with simple true/false statements.
2. **Predicate Logic**: Uses variables and quantifiers for complex reasoning.

---

## **12. Propositional and Predicate Calculus**

### **12.1 Propositional Calculus**

- Uses **propositions** (statements that are true or false).

- Example:
  
  ```
  A: "It is raining."  
  B: "I will take an umbrella."  
  (A → B) means "If it is raining, I will take an umbrella."
  ```

### **12.2 Predicate Calculus**

- Extends propositional logic by using **variables and quantifiers**.

- Example:
  
  ```
  ∀x (Student(x) → Studies(x))  
  ("For all x, if x is a student, then x studies.")
  ```

---

## **13. Resolution in AI**

### **13.1 Definition**

Resolution is a **rule-based method** for logical inference in AI. It simplifies complex logical expressions into **simpler clauses**.

### **13.2 Example**

1. Given:
   
   ```
   P ∨ Q (P OR Q)  
   ¬P (NOT P)  
   ```

2. Resolution:
   
   ```
   Q (Only Q remains)
   ```

---
