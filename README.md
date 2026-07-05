# Arithmetic Instructions Lab

## Objective

The purpose of this lab is to practice arithmetic instructions in Assembly language using NASM on a Linux Intel x86 system.

---

## Equation 1

### Formula
```
result = -var1 * 10
```

### Description
The program loads `var1` into a register, negates it using the `NEG` instruction, multiplies it by 10 using `IMUL`, and stores the answer in `result`.

Example values:
- var1 = 5
- result = -50

---

## Equation 2

### Formula
```
result = var1 + var2 + var3 + var4
```

### Description
The program adds the four initialized variables together and stores the total in `result`.

Example values:
- var1 = 2
- var2 = 3
- var3 = 4
- var4 = 5
- result = 14

---

## Equation 3

### Formula
```
result = (-var1 * var2) + var3
```

### Description
The program makes `var1` negative, multiplies it by `var2`, adds `var3`, and stores the answer in `result`.

Example values:
- var1 = 4
- var2 = 3
- var3 = 2
- result = -10

---

## Equation 4

### Formula
```
result = (var1 * 2) / (var2 - 3)
```

### Description
The program doubles `var1`, subtracts 3 from `var2`, divides the two values, and stores the quotient in `result`.

Example values:
- var1 = 10
- var2 = 5
- result = 10

---

# Flowchart

```
Start
   |
   v
Initialize variables
   |
   v
Load variables into registers
   |
   v
Perform arithmetic operation
   |
   v
Store answer in result
   |
   v
Exit program
```

---

# Challenges Encountered

The biggest challenge was learning how Assembly language performs arithmetic using CPU registers instead of variables like higher-level programming languages. Division required using the `EAX` and `EDX` registers correctly, and I also had to choose values for the final equation that produced an integer result. Debugging with GDB helped verify that each instruction produced the expected value in `result`.

---

# Debugging Commands

Use the following commands in GDB:

```gdb
layout asm
layout regs
watch (int) result
break _start
run
stepi
```

---

# Files Included

- equation1.asm
- equation2.asm
- equation3.asm
- equation4.asm
- README.md

---

# Compile and Run

Example for Equation 1:

```bash
nasm -f elf32 equation1.asm -o equation1.o
ld -m elf_i386 equation1.o -o equation1
gdb ./equation1
```

Repeat the same process for the remaining files.
