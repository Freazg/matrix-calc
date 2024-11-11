# MatrixTool

**MatrixTool** is a powerful and lightweight console application for performing matrix operations.  
It was designed as a study project in C++ to demonstrate practical linear algebra algorithms, while keeping the interface simple and interactive.

---

## 🌟 Overview

MatrixTool allows users to create, manipulate, and analyze matrices directly from the command line.  
It supports a wide range of operations including arithmetic, decomposition-based determinant and inverse calculations, solving linear systems, and even matrix exponentiation.  
The tool is highly modular and demonstrates efficient implementations such as **PLU decomposition**, **Gauss-Jordan elimination**, and **binary exponentiation** for matrix powers.

This makes it suitable for:  
- Students learning **linear algebra**  
- Developers needing a lightweight **matrix computation utility**  
- Anyone experimenting with **numerical methods** in C++  

---

## 🚀 Features

- **Matrix Management**
  - Create new matrices of any size
  - Store multiple matrices in memory with unique names
  - Save matrices to files and load them later
  - Delete matrices when no longer needed

- **Matrix Operations**
  - Addition, subtraction, multiplication
  - Scalar multiplication
  - Transpose
  - Determinant and trace
  - Rank (via RREF)
  - Inverse matrix (Gauss-Jordan)
  - Power (positive/negative integer exponent)
  - Solve systems of linear equations (Ax = b)

- **User-Friendly REPL**
  - Interactive shell with commands
  - Clear error messages
  - Pretty-printed matrices with adjustable formatting

---

## 📦 Installation & Build

### Requirements
- C++17 or later
- g++ / clang++ / MSVC compiler

### Build Instructions

Clone the repository (or download files) and compile:

```bash
g++ -std=c++17 -O2 -o MatrixTool main.cpp
```

This produces the executable `MatrixTool`.

---

## ▶️ Usage

Run the program:

```bash
./MatrixTool
```

You will be greeted with:

```
MatrixTool started. Type 'help' for commands.
>
```

### Example Session

```
> new A 2 2
Enter 4 numbers (row-wise):
1 2 3 4
OK

> show A
     1.000000     2.000000
     3.000000     4.000000

> det A
det(A) = -2.0000000000

> inv A
Done: INV_A

> show INV_A
    -2.000000     1.000000
     1.500000    -0.500000
```

---

## 💾 File Operations

Save a matrix to a file:

```
save A matrix.txt
```

Load a matrix from a file:

```
load B matrix.txt
```

File format:
```
r c
a11 a12 ... a1c
...
ar1 ar2 ... arc
```

Example file for 2x2 identity matrix:
```
2 2
1 0
0 1
```

---

## 📖 Commands Reference

### General
- `help` — display help text  
- `list` — list all stored matrices  
- `exit` — quit the program  

### Matrix Management
- `new <Name> <r> <c>` — create a new matrix (input row-wise)  
- `show <Name>` — print the matrix  
- `del <Name>` — delete matrix from memory  
- `save <Name> <file>` — save matrix to file  
- `load <Name> <file>` — load matrix from file  

### Matrix Operations
- `add <A> <B>` — A + B  
- `sub <A> <B>` — A - B  
- `mul <A> <B>` — A × B  
- `scal <A> <k>` — k × A  
- `trans <A>` — Aᵀ  
- `det <A>` — det(A)  
- `tr <A>` — trace(A)  
- `rank <A>` — rank(A)  
- `inv <A>` — A⁻¹  
- `pow <A> <k>` — Aᵏ (supports k < 0)  
- `solve <A> <b>` — solve Ax = b  

---

## 🛠 Implementation Details

- **Matrix Representation**: stored in a row-major `std::vector<double>`  
- **Determinant**: computed via **PLU decomposition with partial pivoting**  
- **Inverse**: computed via **Gauss-Jordan elimination** with pivoting  
- **Rank**: computed using **row-reduced echelon form (RREF)**  
- **Matrix Power**: optimized using **binary exponentiation**  
- **Solve Ax = b**: solved by forward/backward substitution after PLU decomposition  

The program includes safeguards against:  
- Non-square matrices for operations requiring squareness (det, inv, pow, etc.)  
- Singular or nearly singular matrices (pivot close to zero)  
- Dimension mismatches for addition/multiplication  

---

## 🔍 Example Workflows

### Determinant and Inverse
```
> new M 3 3
Enter 9 numbers (row-wise):
2 0 1
3 0 0
5 1 1

> det M
det(M) = 3.0000000000

> inv M
Done: INV_M
> show INV_M
     0.000000     0.333333     0.000000
     1.000000    -1.666667     1.000000
    -1.000000     1.333333    -0.000000
```

### Solve Linear System
```
> new A 2 2
1 2
3 4
> new b 2 1
5
6
> solve A b
Done: SOL_A_b
    -4.000000
     4.500000
```

---

## 📚 Educational Value

This project demonstrates:
- Practical use of **linear algebra algorithms** in C++  
- Application of **pivoting** in numerical stability  
- Structured use of **OOP and procedural design**  
- Example of a **command-driven REPL application**  

It can serve as:  
- A learning tool for students  
- A foundation for larger numerical libraries  
- A reference for implementing matrix operations from scratch  

---

## 📜 License

This project is licensed under the **MIT License**.  
You are free to use, modify, and distribute it.

---
