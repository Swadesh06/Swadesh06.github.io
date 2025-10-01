---
layout: page
title: RISC-V Factorian Number Program
description: Assembly language programming for mathematical computation
img: assets/img/11.jpg
importance: 11
category: course project
---

## Overview

A RISC-V assembly language program to determine whether a given number is a Factorian number, demonstrating low-level programming concepts and computer architecture principles.

## Project Details

**Duration:** August 2023 – September 2023  
**Course:** ECN-207 (Computer Architecture)  
**Language:** RISC-V Assembly  
**Simulator:** Ripes RISC-V Simulator

## What is a Factorian Number?

A **Factorian number** is an integer that equals the sum of factorials of its digits.

**Example:** 145 is a Factorian number because:
```
145 = 1! + 4! + 5!
    = 1 + 24 + 120
    = 145
```

Other Factorian numbers: 1, 2, 145, 40585

## Objectives

- Implement mathematical computation in assembly language
- Understand RISC-V instruction set architecture
- Practice register management and control flow
- Optimize for performance and code size

## Technical Implementation

### Algorithm Design

1. **Input:** Read integer from user/memory
2. **Digit Extraction:** Extract each digit using division and modulo
3. **Factorial Calculation:** Compute factorial for each digit
4. **Sum Accumulation:** Add all factorials
5. **Comparison:** Compare sum with original number
6. **Output:** Return result (1 if Factorian, 0 otherwise)

### RISC-V Assembly Components

#### Register Usage

- `a0`: Input number / Return value
- `t0-t6`: Temporary registers for computation
- `s0-s1`: Saved registers for intermediate values
- `ra`: Return address for function calls

#### Key Subroutines

1. **`factorial`:** Compute n! iteratively
2. **`extract_digit`:** Get next digit from number
3. **`is_factorian`:** Main checking logic
4. **`print_result`:** Display output

### Code Structure

```assembly
# Main function
main:
    # Load input number
    li t0, 145        # Test with 145
    
    # Call Factorian check
    mv a0, t0
    jal ra, is_factorian
    
    # Print result
    jal ra, print_result
    j exit

# Check if number is Factorian
is_factorian:
    # Save registers
    addi sp, sp, -16
    sw ra, 12(sp)
    sw s0, 8(sp)
    sw s1, 4(sp)
    
    mv s0, a0         # Save original number
    li s1, 0          # Sum accumulator
    
digit_loop:
    # Extract digit
    li t1, 10
    rem t2, s0, t1    # t2 = digit
    div s0, s0, t1    # Update number
    
    # Calculate factorial
    mv a0, t2
    jal ra, factorial
    add s1, s1, a0    # Add to sum
    
    # Continue if digits remain
    bnez s0, digit_loop
    
    # Compare sum with original
    # ... comparison logic ...
    
    # Restore and return
    lw s1, 4(sp)
    lw s0, 8(sp)
    lw ra, 12(sp)
    addi sp, sp, 16
    ret

# Factorial subroutine
factorial:
    # Iterative factorial computation
    # Input: a0 (n)
    # Output: a0 (n!)
    li t0, 1          # Result
    li t1, 1          # Counter
    
fact_loop:
    bgt t1, a0, fact_done
    mul t0, t0, t1
    addi t1, t1, 1
    j fact_loop
    
fact_done:
    mv a0, t0
    ret
```

## Key Challenges

### Technical Challenges

1. **Limited Registers:** Efficient register allocation
2. **No Native Factorial:** Implement from scratch
3. **Digit Extraction:** Handle multi-digit numbers
4. **Overflow Handling:** Manage large factorials
5. **Stack Management:** Proper function calling convention

### Solutions Implemented

- Iterative algorithms to avoid deep recursion
- Careful register save/restore protocols
- Early termination for large digits (>7)
- Modular code design for reusability

## Testing and Validation

### Test Cases

| Input | Expected | Result | Notes |
|-------|----------|--------|-------|
| 1 | True | ✓ | 1! = 1 |
| 2 | True | ✓ | 2! = 2 |
| 145 | True | ✓ | 1! + 4! + 5! = 145 |
| 40585 | True | ✓ | Sum of digit factorials |
| 10 | False | ✓ | 1! + 0! = 2 ≠ 10 |
| 100 | False | ✓ | Not a Factorian |

### Verification Method

- Manual calculation verification
- Ripes simulator step-through debugging
- Register state inspection
- Memory dump analysis

## RISC-V Features Utilized

### Instructions Used

- **Arithmetic:** `add`, `sub`, `mul`, `div`, `rem`
- **Logical:** `and`, `or`, `xor`
- **Comparison:** `beq`, `bne`, `blt`, `bge`
- **Memory:** `lw`, `sw`, `lb`, `sb`
- **Control Flow:** `jal`, `jalr`, `ret`
- **Immediate:** `li`, `addi`, `slli`

### Calling Convention

- Followed RISC-V ABI standards
- Proper stack frame management
- Caller/callee-saved register protocol
- Argument passing in `a0-a7` registers

## Performance Optimization

### Techniques Applied

1. **Loop Unrolling:** Reduce branch overhead
2. **Register Reuse:** Minimize memory access
3. **Early Exit:** Check for digits > 7
4. **Inlining:** Small function integration

### Performance Metrics

- Instruction count minimization
- Cycle count optimization
- Memory access reduction
- Code size efficiency

## Skills Developed

- RISC-V assembly programming
- Low-level algorithm implementation
- Debugging and verification techniques
- Computer architecture understanding
- Optimization strategies

## Simulator Experience

### Ripes Features Used

- Step-by-step execution
- Register file visualization
- Memory inspector
- Instruction pipeline view
- Breakpoint debugging

---

*This project provided fundamental understanding of computer architecture through hands-on assembly programming, bridging high-level algorithms with low-level machine instructions.*

