# IPL Interpreter (IPLI)

Interpreter implementation for the **IPL programming language**, developed as part of an academic assignment.

---

## Authors
- **Vasileios Roussos**
- **Phoebe Orfanakou**

---

## Program Description

The program consists of **five files**: three source files and two header files.  
Its operation is structured into the following stages:

### 1. Detacher
The `detacher` module reads an IPL source file and produces an intermediate file (`out.txt`)
identical to the original but with all comments removed.

If `DEBUG` is not defined, `out.txt` is deleted at the end of execution.

---

### 2. Lexer
The `lexer` module reads characters one by one from `out.txt` and generates **tokens**
according to the type of each word and operation.

- Tokens are stored in a **linked list**
- Lexical analysis is performed
- A limited part of the syntactic analysis is also performed, reducing the workload of the parser

---

### 3. Parser
The `parser` module is the **core component** of the interpreter.

Its responsibilities include:
- Computing the nesting depth of program structures
- Controlling whether each instruction should be executed (execution control logic)
- Performing syntactic analysis
- Executing instructions that pass the execution control phase

---

### 4. Main Program
Control returns to `main`, where:
- All dynamically allocated lists are freed
- If `DEBUG` is defined, additional output is printed

---

## Implemented Features

1. **Basic IPL interpreter functionality**
2. **`break` and `continue` statements**, including support for numeric arguments  
   (with corresponding IPL programs)
3. **Arrays** with support for **multiple references to elements**  
   (with corresponding IPL programs)
4. **Assignment 1 implemented in IPL** (two different implementations)

---

## Example Programs

### Program using `break` and `continue` (`brkcont.ipl`)
Computes the **Least Common Multiple (LCM)** of two numbers read from input.

Constraints:
- Numbers must be positive and non-zero
- Invalid input (negative or zero) is rejected and re-entered
- LCM computation starts only after two valid numbers are provided

---

### Program using arrays with multiple references (`array.ipl`)
Determines the grade obtained by the **largest number of students** in a class.

- The number of students is given as a command-line argument
- Each student's grade is then read from input
- The program outputs:
  - The students who achieved the most common grade
  - The grade itself

#### Example execution
```bash
./ipli array.ipl 5
16 17 20 19 19
4 5 19
