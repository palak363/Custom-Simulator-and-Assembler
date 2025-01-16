# RISC-V Assembler and Simulator

## Overview

This project is a **RISC-V assembler and simulator** designed to convert assembly language programs into machine code and simulate their execution. It supports a wide range of RISC-V instructions, including **R-type**, **I-type**, **S-type**, **B-type**, **U-type**, and **J-type** formats. The tool also includes memory simulation, label handling, and immediate value processing, making it ideal for learning, experimentation, and developing RISC-V-based systems.

---

## Features

### Assembler
- **Instruction Parsing**: Supports various RISC-V instruction formats.
- **Immediate Value Handling**: Converts immediate values to appropriate binary formats (12-bit, 16-bit, 20-bit, etc.).
- **Register Mapping**: Includes mappings for all 32 RISC-V registers.
- **Label Resolution**: Parses and resolves labels for branch and jump instructions.
- **Virtual Halt Detection**: Ensures the program ends with a `beq zero, zero, 0` instruction.

### Simulator
- **Memory Simulation**: Simulates program memory, stack memory, and data memory.
- **Binary Translation**: Converts assembly instructions into corresponding binary machine code.
- **Output Management**: Writes the generated machine code to an output file for further processing.

### Compatibility
- **Instruction Set Support**: Includes major RISC-V instructions:
  - **R-Type**: `add`, `sub`, `sll`, `slt`, `xor`, `srl`, `or`, `and`
  - **I-Type**: `lw`, `addi`, `jalr`, `sltiu`
  - **S-Type**: `sw`
  - **B-Type**: `beq`, `bne`, `blt`, `bge`, `bltu`, `bgeu`
  - **U-Type**: `lui`, `auipc`
  - **J-Type**: `jal`

---

## How It Works

1. **Input Assembly Program**: 
   Provide a text file containing assembly instructions.

2. **Assembler Processing**:
   - Parses each instruction.
   - Converts assembly code to binary machine code.
   - Resolves labels and calculates relative offsets.

3. **Output**:
   - Generates a binary machine code file.
   - Ensures program ends with a virtual halt instruction.

---

## Setup and Usage

### Prerequisites
- Python 3.x
- A text editor for writing assembly programs.

### Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/riscv-assembler-simulator.git
   cd riscv-assembler-simulator
   ```

2. Install dependencies (if any):
   ```bash
   pip install -r requirements.txt
   ```

### Usage
1. **Write Your Assembly Program**:
   Save your assembly code in a file, e.g., `input.txt`.

2. **Run the Assembler**:
   ```bash
   python3 assembler.py
   ```

3. **Output**:
   - The binary machine code will be saved to `output.txt`.

4. **Virtual Halt Validation**:
   Ensure your program ends with the instruction `beq zero, zero, 0`.

---

## Example

### Input (`input.txt`)
```asm
lui a0, 0x1
addi a0, a0, 10
beq zero, zero, 0
```

### Output (`output.txt`)
```
00000000000000000001000010110111
00000000101000000000001010010011
00000000000000000000000011100011
```

---
The project is a valuable resource for learning RISC-V architecture, offering a simple yet effective way to assemble and simulate RISC-V programs. It is particularly useful for educational purposes and developers working with RISC-V systems. 
