# 基于 ZYNQ7020 的五阶段流水线 CPU 设计
本项目实现了一个经典的五级流水线（取指 IF、译码 ID、执行 EX、访存 MEM、写回 WB）处理器。
采用 Verilog 编写，并在 ZYNQ7020 FPGA 平台上进行验证。
ZYNQ7020-5Stage-CPU/
├── doc/                # 设计文档、指令集说明、流水线架构图
├── rtl/                # Verilog/SystemVerilog 源代码
│   ├── core/           # CPU 核心逻辑
│   ├── periph/         # 外设（UART, GPIO等）
│   └── zynq_wrapper/   # AXI总线封装
├── sim/                # 仿真文件 (Testbench)
├── tools/              # 汇编器、16进制转换脚本
├── vivado_project/     # Vivado 工程文件 (建议只上传约束和脚本)
└── README.md           

