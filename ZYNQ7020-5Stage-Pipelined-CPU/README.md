# 基于 ZYNQ7020 的五阶段流水线 CPU 设计 (5-Stage Pipelined CPU on ZYNQ7020)

本项目实现了一个经典的五级流水线（取指 IF、译码 ID、执行 EX、访存 MEM、写回 WB）处理器。采用 Verilog/SystemVerilog 编写，并在 Xilinx ZYNQ7020 FPGA 平台上进行了综合与上板验证。

## 🌟 项目特性 (Features)
* **经典五级流水线**：完整实现了 IF, ID, EX, MEM, WB 五个阶段。
* **指令集架构 (ISA)**：实现了 XXX 指令集（*注：这里可以填入你使用的指令集，比如基于 RISC-V RV32I 的基础指令，或者 MIPS*）。
* **数据冒险与控制冒险处理**：实现了完整的数据旁路（Forwarding）机制和分支预测/流水线冲刷（Flush）逻辑。
* **AXI 总线封装**：通过 `zynq_wrapper` 将 CPU 核心挂载到 ZYNQ 的 PS（处理系统）端，实现软硬件协同。
* **外设支持**：集成了基本的 GPIO 和 UART 通信模块。

## 📂 目录结构 (Repository Structure)

```text
ZYNQ7020-5Stage-CPU/ 
├── doc/              # 设计文档、指令集说明、流水线架构图 
├── rtl/              # Verilog/SystemVerilog 源代码 
│   ├── core/         # CPU 核心逻辑 (ALU, 寄存器堆, 控制器等)
│   ├── periph/       # 外设 (UART, GPIO 等) 
│   └── zynq_wrapper/ # AXI 总线封装 
├── sim/              # 仿真文件 (Testbench) 
├── tools/            # 汇编器、16进制转换脚本 (用于生成指令内存初始化文件)
├── vivado_project/   # Vivado 工程配置 (仅包含 .xpr, 约束文件和 tcl 脚本)
└── README.md           