# VSDSquadron Mini Research Internship

## Task 1

### Objective:
1. To compile a C program.
2. To compile and dissemble the same program using RISCV GCC Compiler.

### Execution:
1. To compile a C program.

Install leafpad GTK+ text editor.
```bash
sudo apt install leafpad
```
Create a new C file using leafpad editor.
```bash
leafpad sum1ton.c
```
![1](https://github.com/user-attachments/assets/4c17ecd5-55bc-4fd7-808b-b454babe8754)
![2](https://github.com/user-attachments/assets/4f07e808-4f7e-44a5-bbb1-81cef3b0c7c8)


Compile the C program using GCC.
```bash
gcc sum1ton.c
```
To get the output.
```bash
./a.out
```
![3](https://github.com/user-attachments/assets/345569a0-66f6-4fab-adc5-d91ab38e3def)


**2. To comppile and dissemble the program using RISCV GCC Compiler**

To see the program.
```bash
cat sum1ton.c
```
The compiler performs optimization based on the knowledge it has of the program. Compiling multiple files at once to a single output file mode allows the compiler to use information gained from all of the files when compiling each of them.</br>

Turning on optimization flags makes the compiler attempt to improve the performance and/or code size at the expense of compilation time and possibly the ability to debug the program.</br>

Depending on the target and how GCC was configured, a slightly different set of optimizations may be enabled at each -O level.</br>

**To optimize the program using -O1 function with RISCV GCC Compiler**</br>
-O1 : Optimizing compilation takes somewhat more time, and a lot more memory for a large function.

With -O, the compiler tries to reduce code size and execution time, without performing any optimizations that take a great deal of compilation time.</br>

Compile the program using RISCV GCC.
```bash
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.0 sum1ton.c
```
![4](https://github.com/user-attachments/assets/5bb9b0e4-08e0-4311-9fab-ca131593285d)

Dissemble the program.
```bash
riscv64-unknown-elf-objdump -d sum1ton.o
```
![5](https://github.com/user-attachments/assets/27e49e61-da01-4413-8a05-8dfdbb38ba7a)

To see the number of instructions in the main programs.
```bash
riscv64_unknown-elf-objdump -d sum1ton.0 | less
```
![VirtualBox_vsdinternship_riscv_21_10_2024_16_16_27](https://github.com/user-attachments/assets/a4193ae4-3227-44a8-a59b-45beeebb4997)

There are ***15 instructions*** in main() with -O1 fumction.

**To optimize the program using -Ofast function with RISCV GCC Compiler**</br>
-Ofast disregard strict standards compliance. -Ofast enables all -O3 optimizations. It also enables optimizations that are not valid for all standard-compliant programs. It turns on -ffast-math, -fallow-store-data-races and the Fortran-specific -fstack-arrays, unless -fmax-stack-var-size is specified, and -fno-protect-parens. It turns off -fsemantic-interposition.</br>

Compile the program using RISCV GCC.
```bash
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.0 sum1ton.c
```
![6](https://github.com/user-attachments/assets/82de7c0f-a2c1-4913-937c-d571e984c9e7)

Dissemble the program.
```bash
riscv64-unknown-elf-objdump -d sum1ton.o
```
![5](https://github.com/user-attachments/assets/0b46476d-7cfe-4f8d-a194-69faf0d4399c)

To see the number of instructions in the main programs.
```bash
riscv64_unknown-elf-objdump -d sum1ton.0 | less
```
![VirtualBox_vsdinternship_riscv_21_10_2024_16_19_46](https://github.com/user-attachments/assets/ecbbd90e-10b3-4540-a968-6abd920c3391)

There are ***12 instructions*** in main() with -Ofast function.
