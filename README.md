# VSDSquadron RISC-V Mini Internship

## 📌 Overview
This repository contains my tasks for the **VSDSquadron RISC-V Mini Internship** under **Kunal Ghosh**. The internship focuses on **RISC-V architecture, software and hardware aspects, and compiler optimizations.**

---

## 📂 Repository Structure
```
/VSD_mini_internship
│── /Task_1
│── /Task_2
│── /Task_3
│── /Task_4
│── README.md
│── LICENSE
│── /images
```

Each task folder contains relevant code, documentation, and results.

---

## 🔥 Internship Tasks

### 📝 Task 1: Setting Up RISC-V Compilation & Assembly Analysis
- Installed **Oracle VirtualBox** and set up an **Ubuntu-based virtual machine**.
- Compiled a simple C program using **GCC**.
- Recompiled using **RISC-V GCC** with `-O1` and `-Ofast` optimization levels.
- Analyzed assembly code and instruction count reduction.

![Task 1 Assembly](images/task1_assembly.png)

➡️ [Task 1 Details](Task_1/README.md)

---

### 📝 Task 2: SPIKE Simulation & RISC-V Object Dump Analysis
- Reviewed the provided **SPIKE Simulation video**.
- Ran SPIKE simulation and observed performance with `-O1` and `-Ofast` compiler optimizations.
- Wrote a **basic C program**.
- Compiled the program using **RISC-V GCC/SPIKE** with both `-O1` and `-Ofast` flags.
- Generated and analyzed the **RISC-V object dump** for both optimization levels.
- Uploaded snapshots of:
  - The compiled **C code**.
  - The **RISC-V object dump** for both `-O1` and `-Ofast`.

![Task 2 SPIKE Simulation](images/task2_spike.png)

➡️ [Task 2 Details](Task_2/README.md)

---

### 📝 Task 3: RISC-V Instruction Analysis
- Reviewed **RISC-V software documentation** to understand the `R`, `I`, `S`, `B`, `U`, and `J` instruction types.
- Examined a **sample GitHub repository** for a visual guide on decoding RISC-V instructions.
- Extracted **15 unique RISC-V instructions** from the `riscv-objdump` of the application code.
- Identified the **exact 32-bit instruction codes** for these instructions in their respective formats.
- Uploaded the **32-bit instruction patterns** to the repository.

![Task 3 Instruction Analysis](images/task3_instructions.png)

➡️ [Task 3 Details](Task_3/README.md)

---

## Task 4: Functional Simulation of RISC-V Core  

### Objective  
Simulate the RISC-V Core using a Verilog netlist and testbench to verify its functionality.  

### Steps  
- Download the Verilog netlist and testbench.  
- Set up a Verilog simulator like **iverilog** or **ModelSim**.  
- Run the simulation and observe waveform from GTKWave.

![Task 4 Image](images/task4.png)

➡️ [Task 4 Details](Task_4/README.md)

---

## 📜 License
This project is licensed under the **MIT License**.

---

## 🤝 Acknowledgments
- **Instructor**: Kunal Ghosh
- **Organization**: VLSI System Design (VSD)
- **Internship Program**: VSDSquadron RISC-V Mini Internship

