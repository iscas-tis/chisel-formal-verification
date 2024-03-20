# Chisel Formal Verification

Formal verification tools for Chisel and RISC-V.

## Contents <!-- omit in toc -->

- [Tools](#tools)
  - [CHA: a verification tool supports SVA-like assertions in Chisel](#cha-a-verification-tool-supports-sva-like-assertions-in-chisel)
  - [RISC-V Spec Core: instruction set consistency verification for RISC-V](#risc-v-spec-core-instruction-set-consistency-verification-for-risc-v)
- [Verification Example](#verification-example)
  - [NutShell](#nutshell)

## Tools

### CHA: a verification tool supports SVA-like assertions in Chisel

[CHA](https://github.com/iscas-tis/CHA) is an assertion language and
verification tool for Chisel programs built on top of ChiselTest, where we
extend the Chisel assertion language with SystemVerilog assertions (SVA)-like
temporal operators.
This enables formal verification of Chisel hardware designs against general
temporal properties.

### RISC-V Spec Core: instruction set consistency verification for RISC-V

[riscv-spec-core](https://github.com/iscas-tis/riscv-spec-core) use a reference
model as the formal semantics of RISC-V ISA document.
The Chisel processor design to be verified should behave the same as the
reference model.
Tools to help with signal synchronization between reference model and processor
design are also included in this project.

## Verification Example

### NutShell

See [nutshell-fv](https://github.com/iscas-tis/nutshell-fv).

In this example of processor design, we use
[riscv-spec-core](https://github.com/iscas-tis/riscv-spec-core) to obtain a
verifiable system with reference model.
And then perform formal verification using BMC through
[ChiselTest](https://github.com/ucb-bar/chiseltest).
