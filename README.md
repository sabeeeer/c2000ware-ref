# C2000Ware 源码快照（离线参照副本）

> [!WARNING]
> 本仓库不是完整 TI 安装包，不包含全部文档、预编译库或授权。
> 详见 [`IRREPLACEABLE.md`](IRREPLACEABLE.md)。

> **这是 TI C2000Ware Core SDK v26.00.00.00.STS 的源码快照**，只保留可阅读的源文件：
> `.c` `.h` `.cmd` `.asm` `.syscfg` `.projectspec`（已剔除编译产物 `.obj/.map/.mk/.pp` 与 PDF/HTML 文档）。
>
> 用途：给 [codebuddy-skills](https://github.com/sabeeeer/codebuddy-skills) 里的 **`ti-c2000-ccs-auto` skill**
> 当"离线参照库" —— 换电脑、重装系统、或原 SDK 目录丢失时，仍能查到 **TI 官方例程、driverlib API、库源码、cmd 链接脚本**。
>
> - 快照日期：2026-09-27
> - 原路径（本机）：`F:\c2000ware-core-sdk`
> - **官方完整包（推荐优先使用）**：https://www.ti.com/tool/C2000WARE  （含全部文档、工具、SysConfig、预编译库）
> - **恢复/校验方式**：见 [`RECOVER.md`](RECOVER.md)

## 内容

| 目录 | 说明 |
|---|---|
| `device_support/<器件>/` | bitfield（寄存器式）官方支持包：`examples/`（例程）、`headers/include/`（器件头 & 寄存器位定义）、`headers/cmd/`（Headers 链接脚本）、`common/{include,source,cmd}` |
| `driverlib/<器件>/` | driverlib（库式 API）：`driverlib/`（源码 + `inc/hw_*.h`）、`examples/`（例程，含 `.syscfg` / `.projectspec`） |
| `libraries/` | `math`（IQmath/CLAmath/FPUfastRTS/FASTINTDIV）、`dsp`（FixedPoint/FPU/VCU）、`control`（DCL）、`communications`（PMBus/USB）、`calibration`（hrpwm/hrcap）、`ai` —— 各库的 `source/` `include/` `examples/` `cmd/` |
| `utilities/` | clb_tool / cmd_tool / dcsm_tool / tools / transfer 等工具的源码 |
| `boards/` | LaunchPad / controlCARD 板级文件 |

器件覆盖：**22 个** device_support 器件（f2833x、f2823x、f2837xd、f2837xs、f2838x、f2807x、f28004x、f28003x…f28p65x、f280x/281x…）+
**13 个** driverlib 器件。

## 怎么用（配合 skill）

在 codebuddy-skills 的 `ti-c2000-ccs-auto` skill 里：

- 索引与速查表：`references/c2000ware-index.md`（"我要做 X → 用哪个库/例程"）
- 本机路径的定位：`scripts/c2000ware_find.ps1 -Keyword <关键词>`（默认指向 `F:\c2000ware-core-sdk`，
  用 `-SdkRoot` 可指到本仓库的克隆目录）
- 写法规范：`references/ti-official-style.md`、`references/c2000ware-guide.md`

## 许可

C2000Ware 各组件的许可为 **BSD-3-Clause**（见 TI 的 `manifest.html`，本仓库 `docs/manifest.html` 为原始副本）。
BSD-3-Clause 允许再分发，**每个源文件顶部的 TI 版权与许可声明均原样保留、未做任何改动**。
本仓库仅为个人开发参照用途，非 TI 官方发布；请以 TI 官网发布为准。
