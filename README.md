# 8-bit ALU Design and Implementation in Proteus

This project is a complete 8-bit Arithmetic Logic Unit (ALU) designed and simulated from scratch in Proteus, using only basic logic gates. It is capable of performing a comprehensive set of arithmetic, logical, and shift operations.

## Features & Operations

This ALU is controlled by a 5-bit operation code (`S3, S2, S1, S0, Cin`) to perform the following functions, based on the classic Morris Mano textbook architecture:

| S3 | S2 | S1 | S0 | Cin | Operation | Function |
|:--:|:--:|:--:|:--:|:---:|---|---|
| 0 | 0 | 0 | 0 | 0 | `F = A` | Transfer A |
| 0 | 0 | 0 | 0 | 1 | `F = A + 1` | Increment A |
| 0 | 0 | 0 | 1 | 0 | `F = A + B` | Addition |
| 0 | 0 | 0 | 1 | 1 | `F = A + B + 1`| Add with Carry |
| 0 | 0 | 1 | 0 | 0 | `F = A + B'` | Subtract with Borrow |
| 0 | 0 | 1 | 0 | 1 | `F = A + B' + 1`| Subtraction |
| 0 | 0 | 1 | 1 | 0 | `F = A - 1` | Decrement A |
| 0 | 0 | 1 | 1 | 1 | `F = A` | Transfer A |
| 0 | 1 | 0 | 0 | X | `F = A ∧ B` | AND |
| 0 | 1 | 0 | 1 | X | `F = A ∨ B` | OR |
| 0 | 1 | 1 | 0 | X | `F = A ⊕ B` | XOR |
| 0 | 1 | 1 | 1 | X | `F = A'` | Complement A |
| 1 | 0 | X | X | X | `F = shr A` | Shift Right A |
| 1 | 1 | X | X | X | `F = shl A` | Shift Left A |

## Design Overview

This ALU is built upon a modular and hierarchical design philosophy. Core components, such as a **1-bit Full Adder** and a **4-to-1 Multiplexer**, were first created from basic gates. These "bricks" were then used to build larger, 8-bit components. The final architecture consists of three independent functional units (Arithmetic, Logical, and Shifter), whose outputs are selected by a final multiplexer to produce the ALU's result.

## How to Use

Set the 8-bit data inputs `A` and `B`, then set the 5-bit control word (`S3` through `Cin`) according to the function table above to get the desired result on the 8-bit output `F`.
