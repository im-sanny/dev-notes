# CPU and Processing

## CPU (Central Processing Unit)

- **Definition**: The brain of the computer, performs all calculations & control.
- **Two Main Parts**:
  1. **Processing Unit (PU)**
  2. **Register Set**

---

## Processing Unit (PU)

- **ALU (Arithmetic Logic Unit)**: Performs arithmetic and logical operations.
  - Operations: `+`, `-`, `×`, `÷`, `AND`, `OR`, `NOT`, `XOR`.
- **CU (Control Unit)**: Manages the flow of data and instructions.
  - Functions: Fetches, decodes, and executes instructions.

---

## Register Set

- **Definition**: Very small & fast memory inside the CPU for temporary data storage.
- **Common Registers**:
  - **SP (Stack Pointer)**: Points to the top of the stack.
  - **BP (Base Pointer)**: Points to the base of the current stack frame.
  - **IR (Instruction Register)**: Holds the current instruction being executed.
  - **PC (Program Counter)**: Holds the address of the next instruction.
  - **AX, BX, CX, DX**: General purpose registers (used for data transfer, calculations, etc.).

### General Purpose Registers by CPU Bit Architecture

| CPU Bit    | Register Names             | Notes                                        |
| :--------- | :------------------------- | :------------------------------------------- |
| **8-bit**  | `AL`, `BL`, `CL`, `DL`     | Each RAM cell = 8 bits (1 byte).             |
| **16-bit** | `AX`, `BX`, `CX`, `DX`     | `AX` is split into `AH` (high) + `AL` (low). |
| **32-bit** | `EAX`, `EBX`, `ECX`, `EDX` | Extended registers.                          |
| **64-bit** | `RAX`, `RBX`, `RCX`, `RDX` | 64-bit registers.                            |

---

## Process

- **Definition**: A program in execution (from start to end).
- **Resource Usage**: Uses part of RAM and CPU time.
- **Memory Space**: Each process has its own isolated memory space containing:
  - Code
  - Data
  - Heap
  - Stack

---

## Stack Management

- **Purpose**: The stack is used for function calls, local variables, and return addresses.
- **Management**: Controlled by **SP** and **BP** to manage the stack frame:
  - **SP** → Points to the **top** of the stack.
  - **BP** → Points to the **base** of the current function's frame.

---

## Summary

- **CPU** = PU + Register Set
- **PU** = ALU + CU
- **Registers** = SP, BP, IR, PC, AX–DX
- **Process** = Running program
- **SP & BP** = Manage stack frames
