### 📌 **Task 1: Setting Up RISC-V Compilation & Analyzing Assembly Code**  

## **🔧 Step 1: Installed VirtualBox and Set Up Ubuntu**  
We installed **Oracle VirtualBox** and configured an **Ubuntu-based virtual machine** for the development environment.  

![VirtualBox Setup](../images/virtualbox_setup.png)  

---

## **📝 Step 2: Writing a Simple C Program**  
We wrote a basic C program to compute the sum of numbers from `1` to `n` using the **gedit** text editor.  

### **C Code (`sum1ton.c`)**  
```c
#include <stdio.h>

int main() {
    int n = 10;  // Change this value to test with different numbers
    int sum = 0;
    
    for(int i = 1; i <= n; i++) {
        sum += i;
    }

    printf("Sum of numbers from 1 to %d is %d\n", n, sum);
    return 0;
}
```

![Gedit C Program](../images/gedit_c_program.png)  

---

## **📝 Step 3: Compiling and Running the Program using GCC**  
We compiled the code using **GCC** and executed it.  

### **Compilation & Execution Commands**  



![GCC Compilation](../images/gcc_compilation.png)  

---

## **📝 Step 4: Compiling the Program using RISC-V and Checking Assembly Code**  
The same **sum1ton.c** program was compiled using the **RISC-V GCC toolchain**, and we examined the assembly output.  

### **RISC-V Compilation Command**
```sh
riscv64-unknown-elf-gcc -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
riscv64-unknown-elf-objdump -d sum1ton.o > sum1ton.dump
```

![RISC-V Compilation](../images/riscv_compilation.png)  

---

## **📝 Step 5: Optimization Analysis (`-O1` vs. `-Ofast`)**  
We compiled the program with different optimization flags to observe instruction count differences.

### **First Compilation (`-O1` Optimization Level)**
```sh
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
riscv64-unknown-elf-objdump -d sum1ton.o > sum1ton_O1.dump
```
- The `main()` function took **15 instructions**.  

![O1 Optimization](../images/o1_optimization.png)  

---

### **Second Compilation (`-Ofast` Optimization Level)**
```sh
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
riscv64-unknown-elf-objdump -d sum1ton.o > sum1ton_Ofast.dump
```
- The `main()` function took **12 instructions**.  

![Ofast Optimization](../images/ofast_optimization.png)  

---

## **📌 Key Observations**
- The **`-Ofast` optimization** reduced the number of instructions in `main()`, making execution more efficient.  
- The difference in **instruction count** highlights how compiler optimizations impact execution.  

![Instruction Count Comparison](../images/instruction_count.png)  

---


