# Half-Precision Runge-Kutta Accelerator on Zynq ZC702 FPGA

This repository implements a hardware accelerator for solving **Ordinary Differential Equations (ODEs)** using **Runge-Kutta numerical methods**. Specifically, this work focuses on implementing **RK2**, **RK3**, and **RK4** solvers on an FPGA, using **half-precision floating-point arithmetic** to optimize power consumption and resource utilization.

The accelerator has been implemented using the **VHDL** programming language and deployed on the **Zynq ZC702 FPGA** evaluation board. The design uses Xilinx Vivado's **16-bit half-precision floating-point** IP to perform arithmetic operations efficiently.

## Overview

Runge-Kutta methods are a family of iterative methods used for solving ODEs. The **RK2**, **RK3**, and **RK4** solvers are widely employed for approximating solutions to ODEs. This work specifically targets the **fourth-order Runge-Kutta (RK4)** solver, which exhibits higher power consumption at clock frequencies up to **80 MHz** when compared to other methods.

### Key Findings:
- The **RK4 solver** consumes the most power when compared to **RK2** and **RK3** solvers.
- This study includes an in-depth evaluation of **on-chip power consumption**, **FPGA resource utilization**, and **timing performance**.
  
The results of this study contribute to enhancing the efficiency of ODE solutions in high-performance computing (HPC) applications.

This work was presented at **IEEE ICEACE 2023**. For more information, you can access the publication: [IEEE ICEACE 2023 Paper](https://ieeexplore.ieee.org/document/10442673).

## Hardware Resource Specifications

The following hardware resources are utilized by the Runge-Kutta solvers, based on half-precision (16-bit) floating-point arithmetic:

| FPU_Add | FPU_Sub | FPU_Mul | MAC Unit |
|---------|---------|---------|----------|
| 5       | 5       | 5       | 10       |

## ODE Solver Example

The accelerator can be used to solve an ODE of the form:

\[
f(x, y) = -2x - y
\]

This example equation demonstrates the use of the accelerator for solving differential equations with the Runge-Kutta method.

## Implementation Details

### Half-Precision Floating-Point Arithmetic

The design uses **16-bit half-precision floating-point** format for efficient computational operations. This allows for reduced power consumption while maintaining acceptable accuracy for solving ODEs. 
