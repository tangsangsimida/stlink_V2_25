# ST-Link V2 下载器

[![License](https://img.shields.io/badge/license-GPL-blue.svg)](LICENSE)

基于 STM32F103CBT6 芯片的高性能 ST-Link V2 下载器，具有完善的安全保护功能。

## 项目简介

本项目是一个兼容 ST-Link V2 协议的下载器，使用 STM32F103CBT6 作为主控芯片。该下载器可以用于编程和调试 STM8 和 STM32 系列微控制器，支持 SWIM、JTAG 和 SWD 接口。

## 特性

- **主控芯片**：STM32F103CBT6 (ARM Cortex-M3, 72MHz, 128KB Flash, 20KB RAM)
- **接口支持**：
  - SWIM 接口（用于 STM8 系列）
  - JTAG 接口（用于 STM32 系列）
  - SWD 接口（用于 STM32 系列）
- **安全保护**：
  - 静电击穿防护（ESD Protection）
  - 反接保护（Reverse Polarity Protection）
  - 过流保护（Overcurrent Protection）
  - 过压保护（Overvoltage Protection）
- **电源**：USB 供电，5V 输入
- **指示灯**：电源指示、状态指示、通信指示
- **兼容性**：完全兼容 ST 官方 ST-Link V2 调试器

## 硬件设计特点

### 安全性设计

1. **静电击穿防护**
   - 在所有输入输出端口添加 TVS 管保护
   - PCB 布局优化，减少静电敏感区域
   - 关键芯片周围添加保护地环

2. **反接保护**
   - 电源输入端采用肖特基二极管防反接设计
   - 接口连接器采用防呆设计
   - 所有接口均具有反接保护电路

3. **其他保护功能**
   - 自恢复保险丝提供过流保护
   - 稳压二极管提供过压保护
   - 滤波电容提高电源稳定性

### 电路设计

- 采用低噪声 LDO 稳压器提供稳定的 3.3V 电源
- 所有接口均配备 ESD 保护器件
- 电源和地平面完整，降低噪声

## 使用说明

### 连接方法

1. 使用 USB 线将下载器连接到电脑
2. 将下载器的接口连接到目标板
3. 安装相应的驱动程序（如果需要）
4. 使用 ST Visual Develop (STVD)、ST Visual Program (STVP) 或 STM32CubeIDE 等软件进行编程

### 支持的软件

- STM32CubeIDE
- ST Visual Develop (STVD)
- ST Visual Program (STVP)
- Keil MDK
- IAR Embedded Workbench
- Atollic TrueSTUDIO

## 注意事项

1. 注意电源极性，避免反接
2. 工作环境应避免强静电干扰
3. 如发现异常发热，请立即断开电源检查
4. 长期不使用时，请断开所有连接并存放在干燥环境中

## 固件更新

本下载器支持固件更新，可以通过以下方式更新：

1. 使用 ST 官方提供的固件更新工具

## 硬件版本

- V1.0：初始版本

## 开源许可

本项目采用 GPL3.0 许可证，详情请参见 [LICENSE](LICENSE) 文件。

## 贡献

欢迎提交 Issue 和 Pull Request 来改进本项目。

## 联系方式

如有问题，请联系项目维护者。