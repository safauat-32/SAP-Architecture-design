# Modified SAP Architecture Implementation in Logisim

This project demonstrates the schematic modeling and implementation of a **Modified Simple-As-Possible (SAP) Architecture** in **Logisim**, designed as part of the VLSI Laboratory course in the Department of Electronics and Telecommunication Engineering at CUET.

---

## 🚀 Objectives

- Understand the structure and function of the **BUS** in a microprocessor.
- Gain familiarity with **RAM addressing** and memory design.
- Learn the steps of the **fetch-decode-execute cycle**.
- Manually simulate program execution in a custom-built processor architecture.

---

## 🧠 Project Theory Summary

This project simulates the working of a basic processor using the classical **instruction cycle** (fetch-decode-execute). It models key components such as:

- **Program Counter (PC)**
- **Memory Address/Data Registers (MAR/MDR)**
- **Instruction Register (IR)**
- **Control Unit**
- **Arithmetic Logic Unit (ALU)**
- **SRAM-based RAM**
- **4x16 Decoder**

The CPU's operation is manually simulated using control signals, emulating how a real control unit would behave.

---

## 🛠️ Design Components

### 1. **4-to-16 Decoder**
Used to select one of 16 memory addresses based on a 4-bit input.

### 2. **SRAM Cell**
Basic building block for the RAM. Includes control for read and write operations via `wr_en`, `rd_en`, and `cs` (chip select).

### 3. **RAM**
A collection of SRAM cells, addressed via the decoder. Used for instruction and data storage.

### 4. **Instruction Register (IR)**
Splits an 8-bit instruction into:
- Opcode (higher 4 bits)
- Operand (lower 4 bits)

### 5. **Complete Processor Layout**
Combines all submodules and uses a central **BUS** for interconnection.

---

## 🧪 Manual Programming and Execution

### Programming RAM

Example instruction: `0001 1010` → Load Register A from memory location `10`.

Steps:
- Use debug mode to set `MAR` and load instructions into RAM.
- Load `0111` (data) into memory location `1010`.

### Running the Program

**Fetch Stage:**
- T1: PC → MAR
- T2: Read from RAM → IR
- T3: PC++

**Decode Stage:**
- Manual (for now)

**Execute Stage (LDA Instruction):**
- T1: IR operand → MAR
- T2: RAM → Register A
- T3: N/A

---

## 🔧 Tools Used

- [Logisim](http://www.cburch.com/logisim/)
- Custom-built logic circuits
- Manual control pin toggling for simulating control unit behavior

---

## 📦 Instruction Set

Currently supports:
- `LDA`: Load A from memory

With this framework, you can extend the instruction set up to 16 custom instructions by assigning new opcodes and execution flows.

---

## 📚 References

1. [Instruction Cycle - Wikipedia](https://en.wikipedia.org/wiki/Instruction_cycle)  
2. [FutureLearn: How Computers Work](https://www.futurelearn.com/info/courses/how-computers-work/0/steps/49284)  
3. [Ben Eater’s 8-bit Computer Series](https://www.youtube.com/playlist?list=PLowKtXNTBypGqImE405J2565dvjafglHU)

---

## 📌 Notes

- This design **does not include** a fully automatic control unit. You simulate it manually to better understand internal processor operations.
- You are encouraged to implement a control unit/sequencer to automate the cycle.

---

## ❤️ Acknowledgements

Developed as part of the VLSI Laboratory at **CUET (Chittagong University of Engineering and Technology)**.

---

> “Hard Work Beats Talent.”  

