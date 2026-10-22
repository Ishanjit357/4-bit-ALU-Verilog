# 4-bit ALU using Verilog and Vivado

## Overview
A 4-bit Arithmetic Logic Unit (ALU) designed using
Verilog HDL and AMD Vivado.

## Features
- Addition and subtraction
- Bitwise AND, OR, XOR, and NOT
- Logical left and right shifts
- Carry/borrow and zero flags

## Tools
- Verilog HDL
- AMD Vivado
- Vivado Simulator

## Files
- `alu_4bit.v` — synthesizable RTL design
- `tb_alu_4bit.v` — simulation testbench

## Verification
Includes directed test cases for arithmetic,
logic operations, shifts, and status flags.

## How to Run
1. Create an RTL project in Vivado.
2. Add `alu_4bit.v` under Design Sources.
3. Add `tb_alu_4bit.v` under Simulation Sources.
4. Set `tb_alu_4bit` as the simulation top.
5. Run Behavioral Simulation.

## Status
Simulation and synthesis results should be
documented after running the project.
