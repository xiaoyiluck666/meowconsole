# MeowConsole 模组简介

`MeowConsole` 是一款专为 **Fabric 26.1 + Java 25** 设计的服务端增强模组。  
它把你熟悉的 Paper 体验带到 Fabric：更好用的控制台、更实战的 Anti-Xray、更稳定的高负载表现。

---

## 为什么选择 MeowConsole

### 1. 控制台更好用，运维效率更高

- 支持终端命令高亮
- 支持 `Tab` 补全（原版命令 + 本地命令）
- 支持本地管理命令：`mods`、`antixray status/reload/profile/debug`、`tps`、`mspt`、`entities <世界> [关键词]`
- 新增 Velocity 接入管理命令：`velocity status`、`velocity reload`（可自动桥接 FabricProxy-Lite 配置）
- 支持实体统计别名：`entitycount`、`mobs`
- 控制台接管更早，服务端启动阶段更快进入可操作状态
- 启动日志信息更清晰，便于快速确认模块状态与当前配置来源

### 2. Anti-Xray 更实战，专治透视

- 区块发送前混淆（不是简单后置假矿补丁）
- 支持按维度独立配置（主世界/下界/末地可分开调）
- 支持回真机制与更新半径控制
- `engine-mode 2` 方向优化，兼顾防透视效果与性能
- 修复“开始挖掘目标方块时未立即回真”的材质错位问题
- 修复“挖掉遮挡块后，邻近假矿未及时回真”的一类显示残留问题
- 新增 `antixray debug`，便于直接排查某个方块是真矿、假矿还是应回真状态

### 3. 性能优化可验证

模组经过多轮 Spark 实测优化，核心改进包括：

- 从逐方块更新改为 section 批量处理
- 暴露判定走快速路径（邻接 section）
- 跳过不可能含目标矿的 section
- 减少 tick 阶段无效遍历

在“高速跑图/高区块吞吐”场景下，Anti-Xray 开销已明显下降，适合长期运行。

---

## 适用人群

- 想用 Fabric 生态，但又希望获得接近 Paper 的服主体验
- 有反透视需求，且希望性能可控
- 需要更高效服务端控制台与运维命令支持的管理员

---

## 核心命令

```bash
mods
mods user|all|loaded|unloaded|system [keyword]
antixray status
antixray reload
antixray profile
antixray debug <world> <x> <y> <z>
velocity status
velocity reload
tps
mspt
entities <world> [keyword]
entitycount <world> [keyword]
mobs <world> [keyword]
```

---

## 配置特点

- 配置文件：`config/meowconsole-paper.yml`
- Velocity 桥接配置：`config/meowconsole-velocity.yml`
- 可自动写入 FabricProxy-Lite 配置：`config/FabricProxy-Lite.toml`
- 首次自动生成完整配置
- 后续仅增量补齐缺失项，不整份重写已有配置
- 默认 `max-block-height: 64`
- `antixray status` / `antixray reload` 会显示配置来源与当前生效摘要
- 如果配置文件读取失败，会明确告警并回退默认配置

---

## Velocity 接入说明

- `FabricProxy-Lite` 为 **Velocity 子功能的软依赖**（功能级依赖）
- 不使用 Velocity 网络时，可不安装 `FabricProxy-Lite`，MeowConsole 其余功能照常可用
- 需要接入 Velocity（尤其 `modern forwarding`）时，必须在 Fabric 服务端安装 `FabricProxy-Lite`
- `velocity status` 可快速确认当前桥接是否生效、配置是否加载成功
- `velocity reload` 可重载桥接配置并同步写入 `FabricProxy-Lite.toml`（若启用自动写入）

---

## 一句话总结

**MeowConsole = Fabric 服务器的“控制台体验升级 + Anti-Xray 性能化落地方案”。**  
更省心、更好管、更能扛。

---

## 仓库与反馈

- 仓库：`https://github.com/xiaoyiluck666/meowconsole`
- Issues：`https://github.com/xiaoyiluck666/meowconsole/issues`


---
