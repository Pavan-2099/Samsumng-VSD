-V Talent Development Program

## Basic Details 

**Name:**  Pavan Kumar K 
**College:** New Horizon college of Engineering  
**Email:** kpavankumarc999@gmail.com  
**GitHub Profile:** [Pavan-2009](https://github.com/Pavan-2099)  


----

## Tasks

### [Task 1: Environment setup and comparing RISC-V compiler with gcc compiler](https://github.com/Vishwachetankittali/Samsung-RISC-V-Talent-Development-Program/tree/main/task%201)
**Description:** Refer to C-based and RISC-V-based lab videos to:

- Compile C code using `gcc`.
- Compile and count the number of instructions used in `o1` and `ofast` using the RISC-V compiler.

  ## Screenshots Task 1
<details>
  <br>
  
![ Screenshot 1](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/image_1.png)
  
![ Screenshot 2](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/image_2.png)

![ Screenshot 3](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/image_3.png)

![ Screenshot 4](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/image_4.png)

![ Screenshot 5](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/imge_5.png)

![ Screenshot 6](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/image_6.png)

</details>
---

### [Task 2: Analyzing RISC-V Performance with Compiler Optimization Flags (-O1 and -Ofast)](https://github.com/Vishwachetankittali/Samsung-RISC-V-Talent-Development-Program/tree/main/TASK%202)
**Description:** In this task, you will explore the compilation process for both standard C and RISC-V architecture:

- Compile a simple C program using the `gcc` compiler.
- Use the RISC-V compiler to compile the same code with optimization flags `-O1` and `-Ofast`.
- Count and compare the number of instructions generated for each optimization level, understanding the impact of compiler optimizations on RISC-V assembly code.

- ###Process Overview:

The code snippets above and the disassembly image represent the compilation of C code to the RISC-V architecture and its low-level representation. First, the sum1ton.c 
file, which probably computes the sum of numbers from 1 to 100, is compiled into a RISC-V object file sum1ton.o with the riscv64-unknown-elf-gcc compiler and some 
flags for optimization and target architecture. This object file holds the machine code produced by the compiler. The objdump utility is then used to disassemble
the object file, converting the machine code into human-readable RISC-V assembly instructions.
Finally, the spike emulator is used to execute the generated RISC-V code, enabling dynamic analysis and debugging with commands such as
until and reg to observe the program's behavior at runtime.

Disassembly Analysis:

The disassembly reveals the low-level instructions that the compiler generated for the C code.
It shows fragments of the main function, including instructions for loading immediate values, 
adjusting the stack pointer,performing arithmetic operations, calling the printf function, 
and managing the function's return. The disassembly also shows part of the register_fini function,
which is likely responsible for cleaning up resources before program termination. From the assembly code,
one can gain an understanding of how the compiler translates high-level C constructs into the underlying machine 
instructions for this RISC-V architecture.

<details>
  <br>
  
![ Screenshot 1](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task2_1.png)
  
![ Screenshot 2](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task2_2.png)

![ Screenshot 3](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task2_3.png)

![ Screenshot 4](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task2_4.png)

</details>
---

### [Task 3: Decoding and Analyzing RISC-V Instruction Types and 32-Bit Patterns](https://github.com/Vishwachetankittali/Samsung-RISC-V-Talent-Development-Program/tree/main/TASK%203)  
**Description:** In this task, you will analyze and decode RISC-V assembly instructions using instruction type formats.

A. **Review RISC-V Instruction Formats:**  
   - Studying the official RISC-V software documentation to understand the following instruction types:  
     - **R-type**  
     - **I-type**  
     - **S-type**  
     - **B-type**  
     - **U-type**  
     - **J-type**  

B. **Analyze Application Code:**  
   - Use the `riscv-objdump` tool to analyze your application code.  
   - Identify 15 unique RISC-V instructions from the disassembled output.

     ### **Machine Code for each instruction**
![Alt text](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task3_r.png)
---

### 1. **I-Type: `addi sp, sp, -32`**

**Description**: Adds the immediate value `-32` to the contents of `sp` (x2), storing the result back in `sp` (x2).


**Binary Fields**:
- `opcode`: `0010011` (for addi)
- `funct3`: `000` (for addi)
- `rd`: `00010` (sp = x2)
- `rs1`: `00010` (sp = x2)
- `imm`: `111111111000` (12-bit immediate = -32)

**32-bit Instruction**:  
`111111111000 00010 000 00010 0010011`

**Hex**: 
`fe010113`
---
### 2. **S-Type: `sd ra, 24(sp)`**

**Description**: Stores the value in `ra` (x1) into memory at the address `sp + 24`.


**Binary Fields**:
- `opcode`: `0100011` (for store instructions like sd)
- `funct3`: `011` (for sd)
- `rs2`: `00001` (ra = x1)
- `rs1`: `00010` (sp = x2)
- `imm`: `24` (12-bit immediate split as imm[11:5] = `0000000`, imm[4:0] = `11000`)

**32-bit Instruction**:  
`0000000 00001 00010 011 11000 0100011`

**Hex**: `00113c23`
---
### 3. **I-Type: `li a5, 10` (Equivalent to `addi a5, x0, 10`)**

**Description**: Loads the immediate value `10` into register `a5` (x15).

**Binary Fields**:
- `opcode`: `0010011` (for addi)
- `funct3`: `000` (for addi)
- `rd`: `01111` (a5 = x15)
- `rs1`: `00000` (x0)
- `imm`: `10` (12-bit immediate: `000000000010`)

**32-bit Instruction**:  
`000000000010 00000 000 01111 0010011`
**Hex**: `00a00793`
---
### 4. **S-Type: `sw a5, -24(s0)`**

**Description**: Stores the contents of register `a5` (x15) into the memory address computed by adding `-24` to the value in register `s0` (x8).


**Binary Fields**:
- `opcode`: `0100011` (for store instructions like sw)
- `funct3`: `010` (for sw)
- `rs1`: `01000` (s0 = x8)
- `rs2`: `01111` (a5 = x15)
- `imm`: `-24` (12-bit immediate: `1111111111001000`)

**Split Immediate**:
- `imm[11:5]`: `1111111`
- `imm[4:0]`: `01000`

**32-bit Instruction**:  
`1111111 01111 01000 010 01000 0100011`
**Hex**: 'fef42423
---
### 5. **U-Type: `lui a5, 0x21`**

**Description**: Loads the upper immediate `0x21` into the upper 20 bits of register `a5`.


**Binary Fields**:
- `opcode`: `0110111` (for LUI)
- `rd`: `01111` (a5 = x15)
- `imm[31:12]`: `0000000000100001` (upper 20 bits of `0x21`)

**32-bit Instruction**:  
`0000000000100001 01111 0110111`

**Hexadecimal**:  
`000217b7`
---
### 6. **J-Type: `jal ra, 1058c <puts>`**

**Description**: Jump and link to the target address `1058c`, storing the return address in register `ra`.


**Binary Fields**:
- `opcode`: `1101111` (for jal)
- `rd`: `00001` (ra = x1)
- `imm[20]`: `0`
- `imm[10:1]`: `0111101100`
- `imm[11]`: `1`
- `imm[19:12]`: `00000100`

**32-bit Instruction**:  
`0 00000100 1 0111101100 00001 1101111`

**Hexadecimal**:  
`3e8000ef`
---
### 7. **J-Type: `j 101e4,<main+0x60>`**

**Description**: Unconditional jump to the target address `101e4`.


**Binary Fields**:
- `opcode`: `1101111` (for j)
- `rd`: `00000` (x0, no return address stored)
- `imm[20]`: `0`
- `imm[10:1]`: `0000110100`
- `imm[11]`: `0`
- `imm[19:12]`: `00000000`

**32-bit Instruction**:  
`0 00000000 0 0000110100 00000 1101111`

**Hexadecimal**:  
`0340006f`
---
### 8. **I-Type: `lw a4, -20(s0)`**

**Description**: Loads a word from memory at the address `s0 - 20` into register `a4`.


**Binary Fields**:
- `opcode`: `0000011` (for load instructions like lw)
- `funct3`: `010` (for lw)
- `rd`: `01110` (a4 = x14)
- `rs1`: `01000` (s0 = x8)
- `imm`: `11111111101100` (12-bit 2's complement for -20)

**32-bit Instruction**:  
`111111111011 01000 010 01110 0000011`


**Hexadecimal**:  
`fec42703`
---
### 9. **I-Type: `mv a5, a4`**

**Description**: The `mv` instruction is a pseudo-instruction in RISC-V, which is translated by the assembler into:
- `mv a5, a4 → addi a5, a4, 0`

This effectively copies the value in register `a4` to register `a5`.


**Binary Fields**:
- `opcode`: `0010011` (for addi)
- `funct3`: `000` (for addi)
- `rd`: `01111` (a5 = x15)
- `rs1`: `01110` (a4 = x14)
- `imm`: `000000000000` (immediate value 0)

**32-bit Instruction**:  
`000000000000 01110 000 01111 0010011`

**Hexadecimal**:  
`00070793`
---
### 10. **S-Type: `slliw a5, a5, 0x1`**

**Description**: The `slliw` instruction performs a logical left shift on a 32-bit value. The value in `a5` is shifted left by 1 bit, and the result is stored back in `a5`.


**Binary Fields**:
- `opcode`: `0011011` (for `slliw`)
- `funct3`: `001` (for `slliw`)
- `rd`: `01111` (a5 = x15)
- `rs1`: `01111` (a5 = x15)
- `imm`: `000000000001` (shift amount 1)

**32-bit Instruction**:  
`000000000001 01111 001 01111 0011011`

**Hexadecimal**:  
`0017979b`
---

### 11. **R-Type: `addw a5, a5, a4`**

**Description**: Adds the contents of `a5` and `a4` as 32-bit values, storing the result in `a5`.

**Binary Fields**:
- `opcode`: `0110011` (for `addw`)
- `funct7`: `0000000`
- `funct3`: `000`
- `rs1`: `01111` (a5 = x15)
- `rs2`: `01110` (a4 = x14)
- `rd`: `01111` (a5 = x15)

**32-bit Instruction**:  
`0000000 01110 01111 000 01111 0110011`


**Hexadecimal**:  
`00e787bb`
---

### 12. **I-Type: `addiw a5, a5, 1`**

**Description**: Adds the contents of `a5` and the immediate value `1` as 32-bit values, storing the result in `a5`.



**Binary Fields**:
- `opcode`: `0010011` (for `addiw`)
- `funct3`: `000`
- `rd`: `01111` (a5 = x15)
- `rs1`: `01111` (a5 = x15)
- `imm`: `000000000001` (Immediate value = 1)

**32-bit Instruction**:  
`000000000001 01111 000 01111 0010011`

**Hexadecimal**:  
`0017879b`
---
### 13. **I-Type: `sext.w a4, a4`**

**Description**: This instruction performs a sign extension of the word (`w` stands for word, i.e., 32 bits) in `a4` and stores the result back into `a4`.

**Binary Fields**:
- `opcode`: `0001011` (for `sext.w`)
- `funct3`: `100` (for `sext.w`)
- `rs1`: `01110` (a4 = x14)
- `rd`: `01110` (a4 = x14)
- `imm[11:0]`: `000000000000` (no immediate value as it's a sign extension)

**32-bit Instruction**:  
`000000000000 01110 100 01110 0001011`

**Hexadecimal**:  
`0007071b`
---
### 14. **B-Type: `bge a5, a4, 101b4 <main+0x30>`**

**Description**: This instruction performs a branch if greater than or equal. If the value in register `a5` is greater than or equal to the value in register `a4`, it branches to the address `101b4`.

**Binary Fields**:
- `opcode`: `1100011` (for `bge` and other branch instructions)
- `funct3`: `101` (for `bge`)
- `rs1`: `01110` (a5 = x15)
- `rs2`: `01101` (a4 = x14)
- `imm`: The offset is calculated as the difference between the target address (`101b4`) and the current PC.
- 
**32-bit Binary Format**:  
`0 000011 0100 0 0 01101 01110 101 000000 1100011`

**Hexadecimal**:  
`fce7d0e3`
---

### 15. **I-Type: `ld ra, 24(sp)`**

**Description**: This instruction loads a 64-bit word from the memory address `24` bytes above the stack pointer (`sp`) and stores it in the `ra` register.

**Binary Fields**:
- `opcode`: `0000011` (for load instructions like `ld`)
- `funct3`: `011` (for `ld` instruction)
- `rd`: `ra = x1 → 00001`
- `rs1`: `sp = x2 → 00010`
- `imm`: The immediate value is `24`, represented as `00000000011000` (12-bit immediate).

**32 bit Instructions**:  
`000000000110 00010 011 00001 0000011`

**Hexadecimal**:  
`01813083`
---



### [Task 4: Functional Simulation of RISC-V Core](https://github.com/Vishwachetankittali/Samsung-RISC-V-Talent-Development-Program/tree/main/TASK%204) 

**Description**:  
This task involves performing a functional simulation of a given RISC-V Core Verilog netlist and testbench to verify the core's functional correctness and document the results.

 **Objectives**  
- Simulate the RISC-V Core using the provided Verilog netlist and testbench.  
- Verify the functional correctness by analyzing the output signals.  
- Document the results with waveform snapshots and upload them to GitHub.  

#### Steps  

 **1. Download Files**  
 **2. Set Up Simulation Environment**  
 **3. Run Functional Simulation**  
 **4. Capture Waveforms**  
**5. Documentation to repository**  

# The Output Waveforms

- instruction 1 : addi

![Alt text](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task4_1.png)

-instruction 2 : sd

![Alt text](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task4_2.png)

-instruction 3 : sd

![Alt text](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task4_3.png)

-instruction 4 : addi

![Alt text](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task4_4.png)

-instruction 5 : li

![Alt text](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task4_5.png)

-instruction 6 : sw

![Alt text](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task4_6.png)

-instruction 7 : lui
![Alt text](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task4_7.png)

-compilation command
![Alt text](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task4_0.png)

-all waveforms appended
![Alt text](https://github.com/Pavan-2099/Samsumng-VSD/blob/main/screenshots/task4_all_waveforms.png)

-

