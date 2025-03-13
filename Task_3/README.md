# Task 3: Understanding and Decoding RISC-V Instructions

## Overview
This task involves analyzing the RISC-V ISA (Instruction Set Architecture), identifying different instruction types, and decoding instructions from an object dump.

## RISC-V ISA
The RISC-V ISA consists of a base integer ISA, which is mandatory in all implementations, along with optional extensions. Unlike early RISC processors, RISC-V does not have branch delay slots and supports variable-length instruction encodings.

## Types of Instruction Formats in RISC-V
RISC-V instructions are classified into six main types based on operand usage and encoding:

### 1. R-Type (Register-Register) Instruction
**Purpose:** Used for arithmetic and logical operations with two source registers and a destination register.

**Fields:**
- `opcode` (7 bits): Specifies the operation type
- `funct3` (3 bits): Differentiates similar instructions
- `funct7` (7 bits): Additional control bits
- `rs1` (5 bits): First source register
- `rs2` (5 bits): Second source register
- `rd` (5 bits): Destination register

### 2. I-Type (Immediate) Instruction
**Purpose:** Used for load instructions, arithmetic operations with immediate values, and register setup.

**Fields:**
- `opcode` (7 bits)
- `funct3` (3 bits)
- `rs1` (5 bits)
- `rd` (5 bits)
- `Immediate` (12 bits)

### 3. S-Type (Store) Instruction
**Purpose:** Used to store data from a register into memory.

**Fields:**
- `opcode` (7 bits)
- `funct3` (3 bits)
- `rs1` (5 bits)
- `rs2` (5 bits)
- `Immediate` (12 bits, split into two parts)

### 4. B-Type (Branch) Instruction
**Purpose:** Enables conditional branching based on register comparison.

**Fields:**
- `opcode` (7 bits)
- `funct3` (3 bits)
- `rs1` (5 bits)
- `rs2` (5 bits)
- `Immediate` (12 bits, offset-based for branching)

### 5. U-Type (Upper Immediate) Instruction
**Purpose:** Used for loading large immediate values.

**Fields:**
- `opcode` (7 bits)
- `rd` (5 bits)
- `Immediate` (20 bits)

### 6. J-Type (Jump) Instruction
**Purpose:** Supports function calls and unconditional jumps.

**Fields:**
- `opcode` (7 bits)
- `rd` (5 bits)
- `Immediate` (20 bits, split across encoding)

---
## Decoding 15 RISC-V Instructions
The following instructions were identified from the `riscv-objdump` of our application code. Each instruction is classified based on its type and its 32-bit encoding.

| Assembly Instruction | Instruction Type | Encoding (Hex) |
|----------------------|-----------------|---------------|
| `lui a0, 0x21` | U-Type | `0x02100537` |
| `addi sp, sp, -16` | I-Type | `0xff110113` |
| `li a2, 15` | I-Type | `0x00f00113` |
| `sd ra, 8(sp)` | S-Type | `0x00a13023` |
| `ld ra, 8(sp)` | I-Type | `0x00a13003` |
| `auipc a5, 0xffff0` | U-Type | `0xffff0537` |
| `add a3, a4, a2` | R-Type | `0x00c202b3` |
| `sub a1, a0, a2` | R-Type | `0x40a20333` |
| `jal x1, 12` | J-Type | `0x0000006f` |
| `jalr x0, x1, 0` | I-Type | `0x000080e7` |
| `slli a5, a5, 2` | I-Type | `0x0022b193` |
| `bne a2, a3, -4` | B-Type | `0xfff2dfe3` |
| `and a4, a3, a2` | R-Type | `0x00c2e2b3` |
| `or a5, a4, a3` | R-Type | `0x00e2f2b3` |
| `xor a6, a4, a3` | R-Type | `0x00e2f333` |

## Conclusion
This task provided hands-on experience in:
- Understanding different RISC-V instruction formats.
- Extracting and decoding instructions from the `riscv-objdump` output.
- Identifying instruction encodings and their corresponding assembly representations.

The knowledge gained here is crucial for working with RISC-V at a low level, including compiler optimizations and performance analysis.
