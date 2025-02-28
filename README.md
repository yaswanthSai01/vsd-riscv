### VSDSquadron RISC-V Mini Internship  
**Instructor**: Kunal Ghosh  
**Organization**: VSD  

#### 📌 Overview  
This repository contains my tasks for the VSDSquadron RISC-V mini internship. The internship focuses on RISC-V architecture, software and hardware aspects, and compilation techniques.

---

## 🔥 Task 1: Setting Up RISC-V Compilation & Analyzing Assembly Code  

### **🔧 Environment Setup**  
- Installed **Oracle VirtualBox** and set up an **Ubuntu-based virtual machine**.  
- Used `gedit` as the text editor.  

### **📝 Lab Session 1: GCC Compilation**  
- Wrote a basic C program to compute the sum of numbers from `1` to `n`.  
- Compiled the code using **GCC** and verified output.  

### **📝 Lab Session 2: RISC-V Compilation & Optimization**  
1. **First Compilation (`-O1` optimization level)**  
   - Compiled the C program using:  
     ```sh
     riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
     ```
   - Checked the assembly code and observed **15 instructions** for the `main()` function.  
   - Instruction range: **10184h to 101c0h**.  

2. **Second Compilation (`-Ofast` optimization level)**  
   - Compiled with:  
     ```sh
     riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
     ```
   - Observed that the number of instructions reduced to **12 instructions**.  
   - Instruction range: **100b0h to 100e0h**.  

### **📌 Key Observations**  
- Higher optimization (`-Ofast`) significantly reduced the instruction count, improving efficiency.  
- RISC-V assembly analysis provides insight into compiler optimizations.  

---

## 💁️ Repository Structure  
```
/VSDSquadron-RISCV-Internship
│── /Task_1
│── /Task_2
│── /Task_3
│── /Task_4
│── README.md
```

