# 4-Bit ALU Design using Verilog HDL

## Overview

This project implements a 4-bit Arithmetic Logic Unit (ALU) using Verilog HDL. The ALU performs arithmetic, logical, and bit-shift operations based on a 4-bit opcode.

The design was developed for learning RTL design, combinational logic, digital arithmetic, and functional verification using AMD Vivado.

## Features

- 4-bit input operands (`A` and `B`)
- Opcode-controlled operation selection
- Arithmetic addition and subtraction
- Bitwise AND, OR, XOR, and NOT operations
- Logical left and right shift operations
- Carry/borrow or shifted-out bit indication
- Zero flag to indicate a zero result
- Verilog testbench for functional simulation

## Tools and Technologies

- **Hardware Description Language:** Verilog HDL
- **Design and Simulation Tool:** AMD Vivado
- **Verification:** Verilog testbench
- **Target FPGA:** Not specified; simulation-focused design

## Project Structure

```text
4-bit-ALU-Verilog/
├── alu_4bit.v
├── tb_alu_4bit.v
└── README.md
```

## ALU Operations

The ALU selects an operation according to the opcode.

| Opcode | Operation | Description |
|---|---|---|
| `0000` | ADD | A + B |
| `0001` | SUB | A − B |
| `0010` | AND | Bitwise AND |
| `0011` | OR | Bitwise OR |
| `0100` | XOR | Bitwise XOR |
| `0101` | NOT | Bitwise NOT of A |
| `0110` | Shift Left | Logical left shift of A |
| `0111` | Shift Right | Logical right shift of A |

*Note: Confirm that these opcode assignments match your `alu_4bit.v` implementation.*

## Design Inputs and Outputs

### Inputs

- `A`: First 4-bit operand
- `B`: Second 4-bit operand
- `ALU_Sel`: Operation-selection input

### Outputs

- `Result`: 4-bit ALU result
- `Carry`: Carry-out, subtraction borrow indication, or shifted-out bit, depending on the selected operation
- `Zero`: Asserted when the 4-bit result is zero

*Signal names and flag behavior should match the actual RTL source code.*

## Design Architecture

```text
        +------------------+
 A ---->|                  |
        |                  |
 B ---->|     4-Bit ALU    |----> Result[3:0]
        |                  |----> Carry
 ALU -->| Operation Select |----> Zero
 Sel    |                  |
        +------------------+
```

The ALU receives two operands and an opcode. Based on the selected operation, the combinational logic produces the result and updates the status flags.

## How to Run in Vivado

1. Open AMD Vivado and create a new RTL project.
2. Add `alu_4bit.v` under **Design Sources**.
3. Add `tb_alu_4bit.v` under **Simulation Sources**.
4. Set `tb_alu_4bit` as the simulation top module.
5. Click **Run Simulation → Run Behavioral Simulation**.
6. Inspect the input operands, opcode, result, carry flag, and zero flag in the waveform.
7. Check that the observed outputs match the expected results for each operation.

## Verification

The testbench is intended to check the ALU's arithmetic, logical, and shift operations.

Recommended test cases include:

- Addition with and without carry-out
- Subtraction with zero and nonzero results
- AND, OR, XOR, and NOT operations
- Left and right shifts
- Zero-flag assertion
- Boundary values such as `4'b0000` and `4'b1111`

**Simulation status:** Update this section after running the testbench and checking the results in Vivado.

## Learning Outcomes

- Understanding combinational RTL design
- Implementing arithmetic and logic operations in Verilog
- Using `case` statements for opcode decoding
- Handling arithmetic results and status flags
- Writing Verilog testbenches
- Performing behavioral simulation and waveform analysis in Vivado

## Future Improvements

- Add overflow and negative flags
- Extend the ALU to 8-bit or 16-bit operands
- Add more arithmetic and logical operations
- Perform synthesis and inspect FPGA resource utilization
- Implement the ALU on an FPGA development board

## Author

**[Your Name]**  
M.Tech, Communication and Signal Processing  
Indian Institute of Technology Indore

## License

This project is intended for educational and learning purposes. Add a license file if you wish to specify how others may use, modify, and distribute the code.
