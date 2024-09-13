# Final Project: 32-bit Pipelined CPU with Advanced ALU Design

## Overview

This repository contains the final project completed for **ECE429 - VLSI Design**, under the guidance of Professor Ken Choi at Illinois Institute of Technology, Spring 2024. The goal of this project was to design a **32-bit Pipelined Central Processing Unit (CPU)** with an advanced **Arithmetic Logic Unit (ALU)** that incorporates several adder architectures and a custom comparator.

The project is divided into two case studies:

1. **Case Study 1**: 32-bit CPU with different Adder architectures
2. **Case Study 2**: 32-bit CPU with New ALU Architecture (including Comparator Design)

## Project Structure

The design and testing were done using **Verilog** and **Synopsys/Cadence** tools, with RTL and post-synthesis simulations performed to verify functionality and timing.

### Case Study 1: 32-bit CPU with Different Adder Architectures

In this case study, four different adder architectures were implemented and compared for performance:

- **Carry Ripple Adder (CRA)**
- **Carry Lookahead Adder (CLA)**
- **Carry Skip Adder (CSA)**
- **Carry Select Adder (CSeA)**

The performance of each design was evaluated in terms of path delay, power consumption, and maximum frequency after place and route (P&R).

#### Key Results:

- **Maximum Frequencies**:
  - CRA: 35.226 MHz
  - CLA: 34.096 MHz
  - CSA: 34.096 MHz
  - CSeA: 34.176 MHz

Simulations were performed using a testbench that verified basic operations like addition, subtraction, and memory store/load.

### Case Study 2: 32-bit CPU with New ALU Architecture

In this case study, a new ALU architecture was designed, including a **32-bit comparator**. The ALU supports standard arithmetic and logical operations such as:

- Multiplication
- Addition
- Subtraction
- AND, OR, XOR, XNOR operations
- 32-bit comparison (`A > B`, `A < B`, `A == B`)

The comparator design was implemented using a **tree structure** for efficient multi-bit comparison, reducing delay and improving overall performance.

## Key Features

- **32-bit Pipelined CPU**: Supports parallel instruction execution using pipelining.
- **ALU with multiple adders**: Implementations of Ripple Carry, Carry Lookahead, Carry Skip, and Carry Select adders.
- **32-bit Comparator**: Designed using a structural approach with tree-based comparison.
- **Physical Design**: Synthesized using Synopsys and routed using Cadence tools, achieving high-performance frequency and low power consumption.

## Setup and Usage

### Prerequisites

To run the project, you'll need the following tools installed:

- **Synopsys Design Compiler** for logic synthesis.
- **Cadence SOC Encounter** for place & route.
- **Cadence Simvision** for post-synthesis simulation.

### How to Run

1. Clone this repository.
2. Run the **RTL Simulation**:
   ```bash
   xrun tb_cpu.v cpu_XXX.v +access+r
