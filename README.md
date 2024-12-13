Experiment 1: Understanding ARM Architecture

•	Objective

Understand the basic components of the ARM architecture.

•	Task

Research and draw the ARM processor architecture, labeling its components.

Answer

The ARM processor architecture consists of the following components:

- Registers (R0-R15)

- Program Counter (PC)

- Stack Pointer (SP)

- Link Register (LR)

- Arithmetic Logic Unit (ALU)

- Memory Management Unit (MMU)

Here is a simple diagram of the ARM processor architecture:

+---------------+

|  Registers   |

|  (R0-R15)   |

+---------------+

|  Program      |

|  Counter (PC) |

+---------------+

|  Stack        |

|  Pointer (SP) |

+---------------+

|  Link         |

|  Register (LR)|

+---------------+

|  Arithmetic   |

|  Logic Unit    |

|  (ALU)        |

+---------------+

|  Memory       |

|  Management    |

|  Unit (MMU)   |

+---------------+


Experiment 2: Basic Assembly Instructions

•	Objective

Write, execute, and debug basic ARM assembly instructions.



•	Tasks

1. Write a program to load and store data using LDR and STR.

2. Perform basic arithmetic operations (addition, subtraction) using ADD, SUB.



Answers

Task 1

Here is an example program that loads and stores data using LDR and STR:

arm

MOV R0, #10 ; load 10 into R0

LDR R1, [R0] ; load value from memory address in R0 into R1

STR R1, [R0] ; store value in R1 into memory address in R0



Task 2

Here is an example program that performs basic arithmetic operations (addition, subtraction) using ADD, SUB:

arm

MOV R0, #10 ; load 10 into R0

MOV R1, #5 ; load 5 into R1

ADD R2, R0, R1 ; add R0 and R1, store result in R2

SUB R3, R0, R1 ; subtract R1 from R0, store result in R3



Experiment 3: Conditional Execution

•	Objective

Use conditional execution in ARM assembly.

•	Tasks



1. Write a program to compare two numbers and output the larger number.

2. Implement a conditional block using CMP, BEQ, BNE.

Answers

Task 1

Here is an example program that compares two numbers and outputs the larger number:

arm

MOV R0, #10 ; load 10 into R0

MOV R1, #5 ; load 5 into R1

CMP R0, R1 ; compare R0 and R1

BGT larger ; branch to larger if R0 > R1

MOV R2, R1 ; move R1 into R2 (R1 is larger)

B exit ; branch to exit

larger:

MOV R2, R0 ; move R0 into R2 (R0 is larger)

exit:

Task 2

Here is an example program that implements a conditional block using CMP, BEQ, BNE:

arm

MOV R0, #10 ; load 10 into R0

MOV R1, #5 ; load 5 into R1

CMP R0, R1 ; compare R0 and R1

BEQ equal ; branch to equal if R0 == R1

BNE not_equal ; branch to not_equal if R0 != R1

equal:

MOV R2, #1 ; move 1 into R2 (R0 and R1 are equal)

B exit ; branch to exit

not_equal:

MOV R2, #0 ; move 0 into R2 (R0 and R1 are not equal)

exit:

Experiment 4: Loops in Assembly
•	Objective

Use loops to perform repetitive tasks.

•	Tasks

1. Write a program to calculate the sum of the first N natural numbers.

2. Implement a multiplication operation using iterative addition.

Answers

Task 1

Here is an example program that calculates the sum of the first N natural numbers:

arm

MOV R0, #10 ; load 10 into R0 (N)

MOV R1, #0 ; load 0 into R1 (sum)

loop:

ADD R1, R1, R0 ; add R0 to R1

SUB R0, R0, #1 ; decrement R0

CMP R0, #0 ; compare R0 to 0

BNE loop ; branch to loop if R0 != 0

Task 2

Here is an example program that implements a multiplication operation using iterative addition:

arm

MOV R0, #10; load 10 into R0 (multiplicand)

MOV R1, #5 ; load 5 into R1 (multiplier)

MOV R2, #0 ; load 0 into R2 (product)

loop:

ADD R2, R2, R0 ; add R0 to R2

SUB R1, R1, #1 ; decrement R1

CMP R1, #0 ; compare R1 to 0

BNE loop ; branch to loop if R1 != 0

Experiment 5: Arrays in Assembly
•	Objective
Work with arrays in ARM assembly language.

•	Tasks

1. Write a program to find the maximum value in an array.

2. Sort an array using the bubble sort algorithm.

Answers

Task 1

Here is an example program that finds the maximum value in an array:

arm

MOV R0, #5 ; load 5 into R0 (array size)

LDR R1, =array ; load address of array into R1

MOV R2, #0 ; load 0 into R2 (max value)

loop:

LDR R3, [R1], #4 ; load value from array into R3

CMP R3, R2 ; compare R3 to R2

BGT update_max ; branch to update_max if R3 > R2

SUB R0, R0, #1 ; decrement R0

CMP R0, #0 ; compare R0 to 0

BNE loop ; branch to loop if R0 != 0

update_max:

MOV R2, R3 ; move R3 into R2 (update max value)

B loop ; branch to loop

array:

DCD 10, 20, 30, 40, 50 ; define array

Task 2

Here is an example program that sorts an array using the bubble sort algorithm:

arm

MOV R0, #5 ; load 5 into R0 (array size)

LDR R1, =array ; load address of array into R1

loop1:

MOV R2, #0 ; load 0 into R2 (inner loop counter)

LDR R3, [R1], #4 ; load value from array into R3

loop2:

CMP R2, R0 ; compare R2 to R0

BGE exit_loop2 ; branch to exit_loop2 if R2 >= R0

LDR R4, [R1], #4 ; load next value from array into R4

CMP R3, R4 ; compare R3 to R4

BGT swap ; branch to swap if R3 > R4

ADD R2, R2, #1 ; increment R2

B loop2 ; branch to loop2

swap:

STR R4, [R1, #-4] ; store R4 into previous memory location

STR R3, [R1], #4 ; store R3 into current memory location

ADD R2, R2, #1 ; increment R2

B loop2 ; branch to loop2

exit_loop2:

SUB R0, R0, #1 ; decrement R0

CMP R0, #0 ; compare R0 to 0

BNE loop1 ; branch to loop1 if R0 != 0

array:

DCD 10, 20, 30, 40, 50 ; define array

DCD 10, 20, 30, 40, 50 ; define array

Task 2

Here is an example program that sorts an array using the bubble sort algorithm:

arm

MOV R0, #5 ; load 5 into R0 (array size)

LDR R1, =array ; load address of array into R1

loop1:

MOV R2, #0 ; load 0 into R2 (inner loop counter)

LDR R3, [R1], #4 ; load value from array into R3

loop2:

CMP R2, R0 ; compare R2 to R0

BGE exit_loop2 ; branch to exit_loop2 if R2 >= R0

LDR R4, [R1], #4 ; load next value from array into R4

CMP R3, R4 ; compare R3 to R4

BGT swap ; branch to swap if R3 > R4

ADD R2, R2, #1 ; increment R2

B loop2 ; branch to loop2

swap:

STR R4, [R1, #-4] ; store R4 into previous memory location

STR R3, [R1], #4 ; store R3 into current memory location

ADD R2, R2, #1 ; increment R2

B loop2 ; branch to loop2

exit_loop2:

SUB R0, R0, #1 ; decrement R0

CMP R0, #0 ; compare R0 to 0

BNE loop1 ; branch to loop1 if R0 != 0

array:

DCD 10, 20, 30, 40, 50 ; define array



Assessment Questions

1. Describe the difference between RISC and CISC architectures.

Answer: RISC (Reduced Instruction Set Computing) architectures have a smaller number of instructions, each executing in a single clock cycle. CISC (Complex Instruction Set Computing) architectures have a larger number of instructions, each executing in multiple clock cycles.


2. Explain the role of the program counter (PC) in ARM architecture.

Answer: The program counter (PC) is a register that stores the address of the current instruction being executed.

3. What is the significance of condition codes in ARM assembly?

Answer: Condition codes are used to control the flow of a program based on the result of a comparison or arithmetic operation.

4. How does the ARM pipeline improve performance?

Answer: The ARM pipeline improves performance by breaking down the instruction execution process into several stages, allowing for concurrent execution of multiple instructions.

5. Compare direct and indirect addressing modes in ARM assembly.

Answer: Direct addressing mode uses the register value as the memory address, while indirect addressing mode uses the register value as a pointer to the memory address.

6. What is the difference between LDR and LDM instructions?

Answer: LDR (Load Register) loads a single value from memory into a register, while LDM (Load Multiple Registers) loads multiple values from memory into multiple registers.

7. Explain the use of the stack pointer (SP) in subroutine calls.

Answer: The stack pointer (SP) is used to store the return address and local variables of a subroutine.

8. How are interrupts handled in ARM architecture?

Answer: Interrupts are handled by the ARM processor using the Interrupt Request (IRQ) and Fast Interrupt Request (FIQ) signals.

9. What are the advantages of using thumb instructions in ARM?

Answer: Thumb instructions provide improved code density, reduced memory usage, and faster execution.

10. Write a code snippet for swapping two numbers without using a third variable.

Answer:

MOV R0, #10 ; load 10 into R0

MOV R1, #5 ; load 5 into R1

ADD R2, R0, R1 ; add R0 and R1, store result in R2

SUB R0, R2, R1 ; subtract R1 from R2, store result in R0

SUB R1, R2, R0 ; subtract R0 from R2, store result in R1


11. Define the term "endianess" and its impact on memory storage in ARM.

Answer: Endianess refers to the order in which bytes are stored in memory. ARM processors support both little-endian and big-endian modes.

12. How does the barrel shifter in ARM instructions work?

Answer: The barrel shifter is a hardware component that shifts bits within a register, allowing for efficient implementation of shift and rotate instructions.

13. Why is pipelining important in ARM processors?

Answer: Pipelining improves performance by breaking down the instruction execution process into several stages, allowing for concurrent execution of multiple instructions.

14. Explain how floating-point operations differ from integer operations.

Answer: Floating-point operations involve calculations with fractional numbers, while integer operations involve calculations with whole numbers.

15. What are the advantages of inline assembly in ARM-based C programming?

Answer: Inline assembly allows developers to write optimized assembly code within C programs, improving performance and reducing code size.

