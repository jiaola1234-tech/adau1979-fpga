# ADAU1979-FPGA 工程库清单

目标工程：`adau1979-fpga.PrjPcb`

## 已加入项目的库

| 项目文档 | 类型 | 主要内容 | 来源 |
|---|---|---|---|
| `ADAU1979_Core.SchLib` | 原理图库 | `adau1979wbcpz-rl`、24.576 MHz 振荡器、LP5907、磁珠、连接器、阻容 | DSP 工程 `24位AD小板子.SCHLIB` |
| `ADAU1979_Core.PcbLib` | PCB 封装库 | ADAU1979 QFN-40、振荡器、LP5907、磁珠、连接器、阻容封装 | DSP 工程 `24位ad小板子.PcbLib` |
| `OPA192.SchLib` / `OPA192.PcbLib` | 原理图/PCB | OPA192 运放及封装 | DSP 工程 |
| `REF2030.SchLib` / `REF2030.PcbLib` | 原理图/PCB | REF2030 基准源及封装 | DSP 工程 |
| `FerriteBead.SchLib` / `FerriteBead.PcbLib` | 原理图/PCB | L0603 磁珠及封装 | DSP 工程 |
| `FPGA_Baseboard.SchLib` / `FPGA_Baseboard.PcbLib` | 原理图/PCB | FPGA 底板相关器件/封装 | FPGA/DSP 工程底板库 |

## 使用说明

1. 在 Altium 中关闭后重新打开 `adau1979-fpga.PrjPcb`，工程面板应显示上述 10 个库文档。
2. 原理图放置器件时搜索 `adau1979wbcpz-rl`；封装应为 QFN-40 6 mm × 6 mm、0.5 mm 间距。
3. ADAU1979 的模拟电源、基准源、时钟和去耦仍需按数据手册布线；库文件只提供器件图形和封装。
4. 该工程没有加入 `光耦.SCHLIB/PcbLib`。原 FPGA 板已有的 `ISO7221AD` 是数字隔离器，不是光耦；只有确定要保留 DSP 工程的 24 V 外部控制隔离接口时才另行加入 PC817。
5. 目标是尽量少改 FPGA 主板，建议把 ADAU1979 放在独立子板，通过已有 FPGA 接口连接。


### 核对结果

`24位AD小板子.SCHLIB` 包含 29 个原理图符号，`24位ad小板子.PcbLib` 包含 15 个 PCB 封装；不是单器件库。`ADAU1979_Core.SchLib/PcbLib` 是同内容的 ASCII 备份副本。关闭并重新打开目标工程后，在库编辑器中应能看到完整器件列表。


原理图库器件索引：
`2MS1T2B2VS2QES`、`AMS1117-3.3_C6186`、`C`、`CAP`、`CAP_2`、`C_1`、`C_2`、`C_3`、`C_4`、`Cap_1`、`R`、`R_1`、`R_2`、`R_3`、`R_4`、`R_5`、`R_6`、`R_7`、`R_10`、`R_10_1`、`TEST-POINT`、`adau1979wbcpz-rl`、`cl31b106kahnnne`、`db125-2.54-10p-gn-s`、`db125-2.54-2p-gn-s`、`fs32x106k101egg`、`lp5907mfx-3.3_nopb`、`mpz1608s221ata00`、`ot2el4c4ji-111olp-24.576m`。
