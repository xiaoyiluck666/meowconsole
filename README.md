# MeowConsole (Fabric 26.1 / Java 25)

`MeowConsole` is a server-side Fabric mod focused on two goals:

1. A Paper-like terminal console experience for dedicated servers.
2. A high-performance anti-xray pipeline optimized for Minecraft `26.1`.

---

## English

### Highlights

- Paper-like console input loop (server terminal)
- `Tab` completion for vanilla commands and local console commands
- Command syntax highlighting in terminal
- Local management commands:
  - `mods` / `mods user|all|loaded|unloaded|system [keyword]`
  - `antixray status`
  - `antixray reload`
  - `antixray profile`
  - `tps`
  - `mspt`
  - `entities <world> [keyword]`
- Anti-xray design tuned for Fabric 26.1:
  - Chunk-packet obfuscation before send
  - Section-batched reveal updates
  - Fast exposure checks using nearby section snapshots
  - Dimension-specific config support

### Performance Notes

This project has been iteratively profiled with Spark under heavy movement/chunk-loading scenarios.
Current versions significantly reduce anti-xray overhead compared to early builds by:

- replacing per-block update spam with section-batched packets
- reducing global scans in tick-time reveal logic
- skipping sections that cannot contain target blocks

### Config

Config file path:

`config/meowconsole-paper.yml`

Behavior:

- On first run, a full default config is generated.
- On subsequent reload/load, only missing keys are supplemented in place; existing values and surrounding content are not rewritten wholesale.
- Default `max-block-height` is `64`.

### Compatibility

- Minecraft: `26.1`
- Fabric Loader: `0.18.4+`
- Java: `25`
- Environment: `server`

### Repository / Issues

- Repository: `https://github.com/xiaoyiluck666/meowconsole`
- Issues: `https://github.com/xiaoyiluck666/meowconsole/issues`

---

## 中文说明

### 功能亮点

- 服务端终端控制台增强（接近 Paper 的体验）
- 支持 `Tab` 补全（原版命令 + 本地命令）
- 控制台命令高亮
- 内置本地命令：
  - `mods` / `mods user|all|loaded|unloaded|system [关键词]`
  - `antixray status`
  - `antixray reload`
  - `antixray profile`
  - `tps`
  - `mspt`
  - `entities <世界> [关键词]`
- 面向 Fabric 26.1 的 anti-xray 优化：
  - 区块发送前进行混淆
  - 按 section 批量回真
  - 使用邻接 section 快速判定暴露
  - 支持按维度独立配置

### 性能说明

本项目基于 Spark 在“高速跑图/高区块吞吐”场景持续迭代。
相较早期版本，当前已明显降低 anti-xray 对主线程的影响，主要通过：

- 从逐方块更新改为 section 批量发送
- tick 回真逻辑从全量扫描改为邻域定向扫描
- 对不可能含目标矿物的 section 直接跳过

### 配置文件

配置路径：

`config/meowconsole-paper.yml`

配置行为：

- 首次启动自动生成完整默认配置
- 后续加载/重载只会增量补齐缺失项，不再整份重写已有配置与周边内容
- 默认 `max-block-height` 为 `64`

### 兼容要求

- Minecraft：`26.1`
- Fabric Loader：`0.18.4+`
- Java：`25`
- 运行环境：`server`

### 仓库 / Issues

- 仓库：`https://github.com/xiaoyiluck666/meowconsole`
- 问题反馈：`https://github.com/xiaoyiluck666/meowconsole/issues`

---

## Author

- `xiaoyiluck`


---
