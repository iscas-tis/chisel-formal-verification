# RISC-V Chisel Fromal Verification

Formal verification of instruction set consistency for RTL design of RISC-V
processors in Chisel.

## Included Projects

### Reference Model

[riscv-spec-core](https://github.com/iscas-tis/riscv-spec-core)  
We use a reference model as the formal semantics of RISC-V ISA document. The
Chisel processor design to be verified should behave the same as the reference
model. Tools to help with signal synchronization between reference model and
processor design are also included in this project

### Verification Example

[nutshell-fv](https://github.com/iscas-tis/nutshell-fv)  
In this example of processor design, we modified the code to get a verifiable
system with reference model. And then perform formal verification using BMC
through [ChiselTest](https://github.com/ucb-bar/chiseltest).
