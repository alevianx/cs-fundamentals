# CS-Fundamentals ⚙️

Welcome! This repository is my personal notebook and experimental lab for understanding how computer systems, compilers, memory, and algorithms work behind the scenes.

Instead of just writing high-level code, the goal here is to inspect **what actually happens under the hood** when code executes across different paradigms (**C++**, **Java**, and **Python**).

---

## 📂 Repository Structure

```text
cs-fundamentals/
│
├── 01-compilation-and-execution/    # Source code → machine code / bytecode
├── 02-memory-and-pointers/          # Stack, heap, memory layout, pointers
├── 03-data-structures/              # Low-level memory representation
├── 04-algorithms/                   # Implementations & complexity analysis
└── 05-concurrency-and-systems/      # Threads, processes, and execution

Each topic follows the same layout:

NN-topic/
├── README.md     # Theory, questions, roadmap and notes
├── cpp/          # C++ experiments
├── java/         # Java experiments
└── python/       # Python experiments
```

---

## 🎯 What I'm Exploring Here

* **Compilers & Runtimes**
  Compare native compilation (C++) vs. bytecode + JIT compilation (Java) vs. bytecode interpretation and runtime execution (Python/CPython).

* **Memory Mechanics**
  Understand stack vs. heap allocation, manual memory management, garbage collection, reference counting, and object lifetimes.

* **Data Structures**
  Explore how arrays, linked lists, hash tables, trees, and other structures are represented and accessed in memory.

* **Algorithms**
  Implement algorithms from scratch and analyze their time and space complexity.

* **Side-by-Side Comparisons**
  Solve the same problem in C++, Java, and Python to understand how each language and runtime handles it internally.

* **Low-Level Execution**
  Inspect assembly, machine instructions, bytecode, memory addresses, processes, threads, and system calls.

---

## 🛠️ Quick Inspection Tools

The following tools are used throughout the repository to inspect what happens below the source-code level.

### C++ — Compilation, Assembly & Memory

```bash
# Preprocess the source code
g++ -E program.cpp -o program.i

# Generate assembly code
g++ -S program.cpp -o program.s

# Generate an object file
g++ -c program.cpp -o program.o

# Generate an executable
g++ program.cpp -o program

# Inspect assembly from an executable
objdump -d program

# Check for memory leaks
valgrind --leak-check=full ./program
```

### Java — JVM Bytecode

```bash
# Compile source code into JVM bytecode
javac BytecodeDemo.java

# Inspect the generated JVM bytecode
javap -c BytecodeDemo

# Inspect additional class information
javap -verbose BytecodeDemo
```

### Python — CPython Bytecode

```bash
# Inspect Python bytecode instructions
python3 -m dis script.py
```

---

## 🔬 Example Exploration

A simple program:

### C++

```cpp
#include <iostream>

int main() {
    int x = 10;
    std::cout << x << std::endl;
    return 0;
}
```

The goal is not only to understand what the code does, but to follow the transformation:

```text
   C++ Source Code
          │
          ▼
     Preprocessor
          │
          ▼
       Compiler
          │
          ▼
       Assembly
          │
          ▼
      Assembler
          │
          ▼
     Object File
          │
          ▼
        Linker
          │
          ▼
      Executable
          │
          ▼
   Operating System
          │
          ▼
         CPU
          │
          ▼
 Machine Instructions
```

The same idea will be explored in Java and Python, where the execution pipeline is different.

---

## 🧠 Questions This Repository Tries to Answer

Instead of only asking:

> "How do I write this code?"

I want to understand questions such as:

* What happens when the compiler sees my source code?
* How does C++ become machine instructions?
* What exactly is an executable file?
* What does the linker actually do?
* What is assembly code?
* How does the CPU execute an instruction?
* Where does a variable actually live in memory?
* What is the difference between stack and heap?
* What is a pointer at the machine level?
* How are objects represented in memory?
* How does a process receive memory from the operating system?
* How does Java bytecode work?
* What does the JVM actually execute?
* What does JIT compilation do?
* How does CPython execute Python bytecode?
* Why can Python be slower than C++ for certain workloads?
* How are arrays, linked lists, hash tables, and trees represented internally?
* What happens when a function is called?
* How are parameters passed?
* What happens to local variables when a function returns?
* How do threads actually execute?
* What is the difference between a process and a thread?

---

## 🚀 How to Use This Repo

1. Pick a topic directory, for example:

   ```text
   01-compilation-and-execution/
   ```

2. Read the topic `README.md` to understand the theoretical concepts.

3. Run the provided examples.

4. Inspect the generated output:

   * Assembly
   * Object files
   * Executables
   * JVM bytecode
   * Python bytecode
   * Memory addresses
   * Runtime behavior

5. Modify the examples and observe how the generated output changes.

6. Compare the same concept across **C++, Java, and Python**.

---

## 📚 Philosophy

The purpose of this repository is not to memorize implementation details.

It is to build an increasingly accurate mental model of what happens between:

```text
Human-readable code
        ↓
Compiler / Interpreter / Runtime
        ↓
Intermediate representation
        ↓
Machine instructions
        ↓
Operating system
        ↓
Memory
        ↓
CPU
        ↓
Actual execution
```

The goal is to move from:

> "I know how to use it."

to:

> "I understand what is happening underneath it."

---

## 🧪 Experimental Approach

Whenever possible, concepts will be explored using small experiments rather than only theoretical explanations.

For example:

```text
Concept
   ↓
Minimal program
   ↓
Compile / execute
   ↓
Inspect generated output
   ↓
Change one thing
   ↓
Observe the difference
   ↓
Build a mental model
```

This repository is therefore both a **study notebook** and an **experimental laboratory**.

---

## 🗺️ Roadmap

### 01 — Compilation & Execution

* Source code
* Preprocessing
* Compilation
* Assembly
* Assembling
* Object files
* Linking
* Executables
* Machine instructions
* JVM bytecode
* CPython bytecode
* JIT compilation

### 02 — Memory & Pointers

* Virtual memory
* Stack
* Heap
* Memory addresses
* Pointers
* References
* Allocation
* Deallocation
* Object lifetime
* Garbage collection
* Reference counting

### 03 — Data Structures

* Arrays
* Dynamic arrays
* Linked lists
* Stacks
* Queues
* Hash tables
* Trees
* Graphs
* Memory layout
* Cache locality

### 04 — Algorithms

* Big O
* Searching
* Sorting
* Recursion
* Dynamic programming
* Graph algorithms
* Memory complexity
* CPU complexity

### 05 — Concurrency & Systems

* Processes
* Threads
* Context switching
* Synchronization
* Mutexes
* Race conditions
* Deadlocks
* Parallelism
* System calls
* Operating-system interaction

---

## ⚙️ Languages

The main languages used for experimentation are:

```text
C++       → Native compilation & low-level memory
Java      → JVM, bytecode & JIT
Python    → CPython, bytecode & runtime behavior
```

Each language provides a different perspective on how high-level abstractions eventually interact with the underlying computer.

---

## 📖 Final Goal

Build a solid understanding of computer systems from the top down and bottom up:

```text
        Applications
             │
             ▼
      Programming Languages
             │
             ▼
      Compilers / Runtimes
             │
             ▼
     Operating System
             │
             ▼
          Memory
             │
             ▼
            CPU
             │
             ▼
        Machine Code
             │
             ▼
          Hardware
```

**Understand the abstraction, then open it and see what is underneath.**
