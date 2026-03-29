# Chisel Formal Verification

针对Chisel和RISC-V的形式化验证工具链

[简体中文](./README_CN.md) [English](./README.md)

## 仓库内容 <!-- omit in toc -->

- [工具链](#工具链)
  - [CHA](#cha)
  - [ChiRVFormal](#chirvformal)
  - [BMCFuzz](#bmcfuzz)
  - [VerinferWidth](#verinferwidth)
  - [Chicala](#chicala)
  - [LLM4Ind](#llm4ind)
- [验证示例](#验证示例)

## 工具链

### CHA

**在 Chisel 中支持类似 SVA 断言的验证工具。**

[CHA](https://github.com/iscas-tis/CHA) 是一个建立在 ChiselTest 上的针对 Chisel 程序的断言语言和验证工具，其中使用类似于 SystemVerilog 断言（SVA）的时序运算符扩展了 Chisel 断言语言。
可以对 Chisel 硬件设计和一般时序性质进行形式化验证。

*SEFM 2022: CHA: Supporting SVA-Like Assertions in Formal Verification of Chisel Programs (Tool Paper)* [Link](https://link.springer.com/chapter/10.1007/978-3-031-17108-6_20) | [BibTex](https://citation-needed.springer.com/v2/references/10.1007/978-3-031-17108-6_20?format=bibtex&flavour=citation)

### ChiRVFormal

**RISC-V 指令集一致性形式化验证工具。**

[ChiRVFormal](https://github.com/iscas-tis/ChiRVFormal) 使用一个参考模型来表示 RISC-V 指令集规范文档的语义。
待验证的 Chisel 处理器设计应该和参考模型的功能一致。项目中还提供了帮助在参考模型和处理器设计间进行信号同步的工具。

*SETTA 2024: Formal Verification of RISC-V Processor Chisel Designs* [Link](https://link.springer.com/chapter/10.1007/978-981-96-0602-3_8) | [BibTex](https://citation-needed.springer.com/v2/references/10.1007/978-981-96-0602-3_8?format=bibtex&flavour=citation)  
*JSA 2026: χRVFormal: Formal Verification of RISC-V Processor Chisel Designs* [Link](https://doi.org/10.1016/j.sysarc.2026.103761) | [BibTex](https://www.sciencedirect.com/sdfe/arp/cite?pii=S1383762126000792&format=text%2Fx-bibtex&withabstract=true)

### BMCFuzz

**通过有界模型检测与模糊测试协同实现处理器混合验证。**

[BMCFuzz](https://github.com/iscas-versys/BMCFuzz) 是一个面向有界模型检测流程的模糊测试框架。
该工具结合限界模型检测（BMC）和覆盖引导模糊测试（CGF）进行处理器验证。
BMC 与 CGF 具有互补性：前者在给定界限内可穷尽搜索但面临状态空间爆炸问题，后者可扩展性更好但依赖种子质量。
BMCFuzz 通过双向协同流程整合两者，并在 NutShell、Rocket 和 BOOM 上进行了更高覆盖率的验证，并发现了 3 个新漏洞。

*ICCAD 2025: BMCFuzz: Hybrid Verification of Processors by Synergistic Integration of Bound Model Checking and Fuzzing* [Link](https://ieeexplore.ieee.org/document/11240887)

### VerinferWidth

**使用 Coq 形式化验证 FIRRTL 编译过程。**

[VerinferWidth](https://github.com/iscas-tis/coq-firrtl)
针对三个 Chisel 关键编译步骤，完成了形式化定义和正确性证明，并对官方编译器
firtool 中的位宽推断算法进行了改进，提出了完备的位宽推断算法，并进行了实现和正确性证明。

*ESOP 2026: A Formally Verified Procedure for Width Inference in FIRRTL*

### Chicala

**基于 Chisel 到 Scala 翻译与 Stainless 的高层 Chisel 验证方法。**

[Chicala](https://github.com/iscas-tis/chicala) 通过 Scala 编译器插件将 Chisel
硬件设计代码翻译为 Scala 程序，并结合 Scala 软件验证工具 Stainless 进行演绎验证。
该方法能够利用 Chisel 层面的参数和结构信息，支持对算术电路设计的参数化位宽进行证明。

*DAC 2024: Formally Verifying Arithmetic Chisel Designs for All Bit Widths at Once* [Link](https://dl.acm.org/doi/10.1145/3649329.3657311) | [BibTex](https://dblp.org/rec/conf/dac/FengL0J0W24.html?view=bibtex)

### LLM4Ind

**LLM 辅助归纳定义结构的求解。**

[LLM4Ind](https://github.com/fengwz17/LLM4Ind) 是一个利用大语言模型辅助求解含归纳
（递归）定义约束的项目。
该方法通过结构化提示词引导 LLM 生成辅助引理，并与 SMT 求解器相结合，形成神经符号融合的验证工具。
在代数数据类型和递推关系相关测试集上，该方法相较于现有 SMT/CHC 求解器可多解决约
25% 的证明任务。

*FM 2026: Can LLM Aid in Solving Constraints with Inductive Definitions?*

## 验证示例

- [XiangShan-fv (Nanhu)](https://github.com/chenjie35335/XiangShan-fv)
- [Zhoushan-fv](https://github.com/chenjie35335/Zhoushan-fv)
- [nutshell-fv](https://github.com/iscas-tis/nutshell-fv)
- [riscv-boom-sim (formal branch)](https://github.com/iscas-versys/riscv-boom-sim/tree/formal)
- [riscv-mini-formal](https://github.com/SeddonShen/riscv-mini-formal)
