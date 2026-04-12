# Context Switching, PCB, and Concurrency

## Context Switching

- **Definition**: Context switching is the CPU switching from one process to another.
- **Single Core Limitation**: A single-core CPU can only execute one instruction at a time.
- **The Illusion**: Because switching happens extremely fast (in microseconds), it **appears** to run multiple processes at once.
- **Mechanism**: The OS saves the current process state and loads the next one — this action is the "context switch".

---

## Program Counter & Execution Flow

The CPU follows a continuous **Fetch–Decode–Execute** cycle:

1. **Program Counter (PC)** → Holds the address of the next instruction.
2. **Control Unit (CU)** → Fetches the instruction from memory (RAM) using the address in the PC.
3. **Instruction Register (IR)** → Stores the fetched instruction.
4. **Decode** → CU decodes the instruction and places operands in registers (e.g., `AL`, `BL`, `CL`).
5. **Execute** → ALU performs the operation.
6. **Store** → Result is stored in data registers or memory.
7. **Increment** → PC increments to point to the next instruction.

> This cycle continues until the program ends.

---

## CPU Speed

- A modern CPU can perform around **1–5 billion operations per second** (1–5 GHz).

---

## Role of the Operating System (OS)

- **Scheduling**: OS controls CPU scheduling and decides which process gets CPU time.
- **Instruction Management**: OS updates which instruction address (PC value) will execute next.
- **Multitasking**: OS performs context switching between processes when needed to enable multitasking.

---

## PCB (Process Control Block)

- **Definition**: PCB stands for **Process Control Block**. It is a small data structure maintained by the OS for every process.
- **Contents**: It contains all necessary information about a process:
  - **Process ID (PID)**
  - **Process State** (running, ready, waiting, etc.)
  - **CPU Registers** (PC, SP, BP, general purpose registers, etc.)
  - **Memory Info** (pointers to code, data, stack segments)
  - **I/O Info** and **Priority**

### Context Switch Mechanism with PCB

When a context switch occurs:

1. OS **saves** the current process’s state into its PCB.
2. OS **loads** the next process’s PCB (restoring its saved state).
3. This allows processes to pause and resume smoothly without losing data.

---

## Key Terminology

### Process State

- **Definition**: The "State" is the complete snapshot of CPU registers and memory for a process at a specific moment in time.

### PID (Process ID)

- **Definition**: A unique number used by the OS to identify each process.
- **Storage**: Stored inside the PCB.

### Concurrency

- **Definition**: Multiple processes **appear** to run simultaneously.
- **Reality**: On a single core, the CPU executes one process at a time but switches rapidly.
- **Parallelism**: Multicore CPUs can execute truly parallel tasks (multiple processes at the exact same instant).
- **Summary**: Concurrency is the **illusion** of simultaneous execution created by fast switching.

### Software vs. Process

- **Software**: A binary executable file containing compiled instructions that the CPU can execute.
- **Process**: When software is executed, it becomes a **process** (loaded into memory with its own PCB).

---

## Summary

- **Context Switching** → CPU switches processes (OS saves/loads PCB).
- **PCB** → Stores process info (PID, state, registers, memory, etc.).
- **PC** → Holds the next instruction address.
- **Concurrency** → Illusion of multiple tasks running together via rapid switching.
- **OS** → Manages CPU scheduling, context switching, and process states.
