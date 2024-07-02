# Chisel Formal Verification

针对Chisel和RISC-V的形式化验证工具链

[简体中文](./README_CN.md) [English](./README.md)

## 仓库内容 <!-- omit in toc -->

- [Chisel Formal Verification](#chisel-formal-verification)
  - [工具集合](#工具集合)
    - [CHA: 在 Chisel 中支持类似 SVA 断言的验证工具](#cha-在-chisel-中支持类似-sva-断言的验证工具)
    - [RISC-V Spec Core: RISC-V指令集一致性验证工具](#risc-v-spec-core-risc-v指令集一致性验证工具)
  - [验证示例](#验证示例)
    - [NutShell](#nutshell)

## 工具链

### CHA: 在 Chisel 中支持类似 SVA 断言的验证工具

[CHA](https://github.com/iscas-tis/CHA) 是一个建立在 ChiselTest 上的针对 Chisel 程序的断言语言和验证工具，其中使用类似于 SystemVerilog 断言（SVA）的时序运算符扩展了 Chisel 断言语言。
可以对 Chisel 硬件设计和一般时序性质进行形式化验证。

### RISC-V Spec Core: RISC-V 指令集一致性验证工具

[riscv-spec-core](https://github.com/iscas-tis/riscv-spec-core) 使用一个参考模型来表示 RISC-V 指令集规范文档的语义。
待验证的 Chisel 处理器设计应该和参考模型的功能一致。项目中还提供了帮助在参考模型和处理器设计间进行信号同步的工具。

## 验证示例

### NutShell

经验证的 NutShell 仓库见：[nutshell-fv](https://github.com/iscas-tis/nutshell-fv)。

在这个处理器设计的例子中，我们使用了工具链中的 [riscv-spec-core](https://github.com/iscas-tis/riscv-spec-core) 组成了一个包含参考模型和性质的可验证的系统，并通过 [ChiselTest](https://github.com/ucb-bar/chiseltest) 调用了 BMC 算法进行形式化验证。
