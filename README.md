# Chisel Formal Verification

Formal verification tools for Chisel and RISC-V.

[简体中文](./README_CN.md) [English](./README.md)

## Contents <!-- omit in toc -->

- [Tools](#tools)
  - [CHA](#cha)
  - [ChiRVFormal](#chirvformal)
  - [BMCFuzz](#bmcfuzz)
  - [VerinferWidth](#verinferwidth)
  - [Chicala](#chicala)
  - [LLM4Ind](#llm4ind)
- [Verification Examples](#verification-examples)

## Tools

### CHA

**A verification tool that supports SVA-like assertions in Chisel.**

[CHA](https://github.com/iscas-tis/CHA) is an assertion language and
verification tool for Chisel programs built on top of ChiselTest, where we
extend the Chisel assertion language with SystemVerilog assertions (SVA)-like
temporal operators.
This enables formal verification of Chisel hardware designs against general
temporal properties.

*SEFM 2022: CHA: Supporting SVA-Like Assertions in Formal Verification of Chisel Programs (Tool Paper)* [Link](https://link.springer.com/chapter/10.1007/978-3-031-17108-6_20) | [BibTex](https://citation-needed.springer.com/v2/references/10.1007/978-3-031-17108-6_20?format=bibtex&flavour=citation)

### ChiRVFormal

**Instruction set consistency verification for RISC-V.**

[ChiRVFormal](https://github.com/iscas-tis/ChiRVFormal) uses a reference
model as the formal semantics of the RISC-V ISA document.
The Chisel processor design to be verified should behave the same as the
reference model.
This project also includes tools for signal synchronization between the
reference model and the processor design.

*SETTA 2024: Formal Verification of RISC-V Processor Chisel Designs* [Link](https://link.springer.com/chapter/10.1007/978-981-96-0602-3_8) | [BibTex](https://citation-needed.springer.com/v2/references/10.1007/978-981-96-0602-3_8?format=bibtex&flavour=citation)  
*JSA 2026: χRVFormal: Formal Verification of RISC-V Processor Chisel Designs* [Link](https://doi.org/10.1016/j.sysarc.2026.103761) | [BibTex](https://www.sciencedirect.com/sdfe/arp/cite?pii=S1383762126000792&format=text%2Fx-bibtex&withabstract=true)

### BMCFuzz

**A two-way hybrid verification approach that synergistically integrates bounded model checking and coverage-guided fuzzing.**

[BMCFuzz](https://github.com/iscas-versys/BMCFuzz) is a fuzzing framework for
processor verification that combines bounded model checking (BMC) and
coverage-guided fuzzing (CGF).
BMC and CGF are complementary: BMC is exhaustive within a bound but suffers
from state-space explosion, while CGF is scalable but seed-dependent.
BMCFuzz integrates both in a two-way workflow and is evaluated on NutShell,
Rocket, and BOOM, reporting higher coverage and three previously unknown
vulnerabilities.

*ICCAD 2025: BMCFuzz: Hybrid Verification of Processors by Synergistic Integration of Bound Model Checking and Fuzzing* [Link](https://ieeexplore.ieee.org/document/11240887)

### VerinferWidth

**Formally verifying the FIRRTL compilation flow in Coq.**

[VerinferWidth](https://github.com/iscas-tis/coq-firrtl) formalizes and proves
the correctness of three key FIRRTL compilation steps.
It also improves the width inference algorithm in the official compiler
`firtool` by proposing a complete procedure, together with its implementation
and mechanized correctness proof.

*ESOP 2026: A Formally Verified Procedure for Width Inference in FIRRTL*

### Chicala

**A high-level Chisel verification method based on Chisel-to-Scala translation
and Stainless.**

[Chicala](https://github.com/iscas-tis/chicala) translates Chisel hardware
designs into Scala programs via a compiler plugin, enabling deductive
verification with Scala software verification tool Stainless.
It supports reasoning with Chisel-level parameter and structure information,
including proofs for arithmetic designs across bit widths.

*DAC 2024: Formally Verifying Arithmetic Chisel Designs for All Bit Widths at Once* [Link](https://dl.acm.org/doi/10.1145/3649329.3657311) | [BibTex](https://dblp.org/rec/conf/dac/FengL0J0W24.html?view=bibtex)

### LLM4Ind

**A neuro-symbolic approach for solving constraints with inductive definitions.**

[LLM4Ind](https://github.com/fengwz17/LLM4Ind) is a project on leveraging
large language models to help solve constraints involving inductive
(recursive) definitions.
It uses structured prompts to generate auxiliary lemmas, then iteratively
combines LLM conjecture generation with SMT solver checking in a
neuro-symbolic loop.
On benchmarks from algebraic data types and recurrence relations, it reports
around 25% more solved proof tasks than state-of-the-art SMT/CHC solvers.

*FM 2026: Can LLM Aid in Solving Constraints with Inductive Definitions?*

## Verification Examples

- [XiangShan-fv (Nanhu)](https://github.com/chenjie35335/XiangShan-fv)
- [Zhoushan-fv](https://github.com/chenjie35335/Zhoushan-fv)
- [nutshell-fv](https://github.com/iscas-tis/nutshell-fv)
- [riscv-boom-sim (formal branch)](https://github.com/iscas-versys/riscv-boom-sim/tree/formal)
- [riscv-mini-formal](https://github.com/SeddonShen/riscv-mini-formal)
