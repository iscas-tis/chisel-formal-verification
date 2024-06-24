# Chisel Formal Verification

针对Chisel和RISC-V的形式化验证工具链

[简体中文](./README_CN.md) [English](./README.md)
## 仓库内容
- [工具](#tools)
  - [CHA: 在 Chisel 中支持类似 SVA 断言的验证工具](#cha-a-verification-tool-supports-sva-like-assertions-in-chisel)
  - [RISC-V Spec Core: RISC-V指令集一致性验证工具](#risc-v-spec-core-instruction-set-consistency-verification-for-risc-v)
- [验证示例](#verification-example)
  - [NutShell](#nutshell)

## 工具集合

### CHA: 在 Chisel 中支持类似 SVA 断言的验证工具

[CHA](https://github.com/iscas-tis/CHA) 提供了针对 Chisel 程序的断言语言和验证工具，它建立在 ChiselTest 的基础上，并使用用类似于 SystemVerilog 断言（SVA）的时序运算符扩展了 Chisel 断言语言。
这使得 Chisel 硬件设计可以根据一般时态属性进行形式验证。
    
### RISC-V Spec Core: RISC-V指令集一致性验证工具

[riscv-spec-core](https://github.com/iscas-tis/riscv-spec-core) 设计了一个参考模型，使用形式化语义来描述RISC-V ISA文档。
使用Chisel设计处理器需要与参考模型保持严格的一致性，工具中还提供了帮助参考模型和处理器设计之间实现信号同步的部分。

## 验证示例

### NutShell

经验证的NutShell仓库见： [nutshell-fv](https://github.com/iscas-tis/nutshell-fv).

在这个处理器设计的例子中，我们使用了工具链中的参考模型[riscv-spec-core](https://github.com/iscas-tis/riscv-spec-core)，并通过[ChiselTest](https://github.com/ucb-bar/chiseltest)调用了BMC算法进行形式化验证。
