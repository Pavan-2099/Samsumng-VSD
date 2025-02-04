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

### [Task 5: Implementation of 3-bit Binary to Gray Code Converter using VSDSquadron Mini](https://github.com/Vishwachetankittali/Samsung-RISC-V-Talent-Development-Program/tree/main/TASK%205)

**Description**:   
This task involves implementing a **3-bit Binary to Gray Code Converter** using the **VSDSquadron Mini (RISC-V-based SoC)**. The system takes a 3-bit binary number as input from push buttons, processes the conversion using **XOR logic**, and displays the Gray code output on LEDs. The objective is to utilize **GPIO operations** for real-time digital logic applications.  

 **Objectives**  
- Implement a **3-bit Binary to Gray Code Converter** on the **VSDSquadron Mini**.  
- Utilize **GPIO** for reading push button inputs and driving LED outputs.  
- Apply **XOR logic** to compute the Gray code equivalent.  
- Verify correct operation by comparing the LED outputs to the expected Gray code.  

#### Steps  
1. **Circuit Setup** – Connect push buttons for binary input and LEDs for Gray code output.  
2. **GPIO Configuration** – Initialize and configure GPIO pins for input and output.  
3. **Gray Code Conversion Logic** – Implement XOR-based conversion in RISC-V firmware.  
4. **Testing & Verification** – Check the LED outputs against expected Gray code values.  
5. **Documentation to Repository** – Upload circuit schematics, firmware code, and results to GitHub.  
