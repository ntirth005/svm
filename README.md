# Operating Systems Assignment 1 - Multi-Process Perfect Number Finder

## Introduction
This program identifies **perfect numbers** up to a given limit **N** using **K child processes**.  
It utilizes **multi-processing** with `fork()`, **Inter-Process Communication (IPC)** through **shared memory**, and **process synchronization** to efficiently distribute computation across multiple processes.


## Input File Format (`CS23B1026_input.txt`)
The input file contains two integers separated by a space:

    N K
    Where:
    - **N** - The maximum number to check for perfect numbers.  
    - **K** - The number of child processes to create.

### Example:
10000 4
(This means the program will check for perfect numbers up to **10,000** using **4 processes**.)


## Output File Format (`CS23B1026_output.txt`)
The output file lists numbers along with their status as perfect numbers.

### Example Output:
6: Perfect number found 
28: Perfect number found 
496: Perfect number found 
8128: Perfect number found

Each line represents a number identified as a **perfect number**.


## How to Compile and Run the Program

### **Compile the C program**
    - gcc Assgn1Src-CS23B1026.c -o perfect_finder
    - Run the executable
        ./perfect_finder   
    - Check the Output File
        After execution, open CS23B1026_output.txt to view the perfect numbers.

## Program Workflow
    - The main process reads the values of N and K from the input file.
    - It creates K child processes using fork().
    - The range 1 to N is divided among the K processes.
    - Each child process:
        Checks its assigned numbers for perfect numbers.
        Stores results in shared memory.
    - The parent process waits for all children to finish.
    - The results are consolidated into CS23B1026_output.txt.
    - Shared memory is deallocated at the end.

## This program is tested on:

    1. OS: Linux (Ubuntu 20.04, Fedora, etc.)
    2. Compiler: GCC (GNU Compiler Collection)
    3. Memory: Minimum 1GB RAM
    4. Disk Space: ~5MB
    5. Concepts Used
        Multi-processing (fork())
        Shared Memory Communication (shmget, shmat, shmdt, shmctl)
        Process Synchronization (wait())
        Parallel Computation for efficiency

## Author Information
    Name: Himanshu Yadav
    Roll Number: CS23B1026
    Course: Operating Systems
    Assignment Number: 1