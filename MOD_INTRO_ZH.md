# 🐾 Meow Console

**面向 Fabric 与 NeoForge 的专用服务器运维工具箱。**

让控制台更清晰，让服务器状态更直观，让管理员的日常操作更快完成。Meow Console 专为专用服务端设计，玩家客户端无需安装。

[![Modrinth 下载](https://img.shields.io/badge/Modrinth-%E4%B8%8B%E8%BD%BD-1bd96a?style=flat-square&logo=modrinth&logoColor=white)](https://modrinth.com/mod/meowconsole) [![GitHub Wiki 文档](https://img.shields.io/badge/GitHub-Wiki%20%E6%96%87%E6%A1%A3-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/xiaoyiluck666/meowconsole/wiki) [![GitHub 源码](https://img.shields.io/badge/GitHub-%E6%BA%90%E7%A0%81-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/xiaoyiluck666/meowconsole) [![提交 Issue](https://img.shields.io/badge/GitHub-%E6%8F%90%E4%BA%A4%20Issue-d73a4a?style=flat-square&logo=github&logoColor=white)](https://github.com/xiaoyiluck666/meowconsole/issues/new/choose)

💖 **支持项目开发：** [PayPal](https://www.paypal.com/paypalme/neworldcn) · [爱发电](https://afdian.com/a/xiaoyiluck)

## ✨ 它能解决什么问题？

- 🖥️ **控制台更清晰**：Paper-like 彩色输出、终端宽度自适应面板、本地命令补全、持久命令历史和安全的控制台日志过滤。
- 📊 **排查问题更快**：健康状态、TPS/MSPT、分页实体统计、模组列表、告警和更新检查集中查看。
- 👋 **玩家体验工具**：自定义加入/离开消息、达到门槛自动跳夜、飞行保护。
- 🔌 **适配托管环境**：Velocity / FabricProxy-Lite 辅助配置，并兼容 MCDR 与常见面板宿主的 stdout、原版控制台输入。
- 🛠️ **远程管理方便**：Fabric 与 NeoForge 通用管理员/RCON 命令，包括 `status`、`health`、`alerts`、`tps`、`mspt`、`mods`、`entities`、`console`、`reload`、`update`；在 Loader 权限 API 可用时提供原生权限节点，并保留 OP 等级回退。
- 🧩 **纯服务端模组**：适合专用服务器、代理网络和长期运行的生存服，玩家无需安装。

## 🧭 内置工具

本地控制台提供 `health`、`alerts`、`entities`、`messages`、`mcdr`、`sleep`、`flight`、`velocity`、`mods`、`tps`、`mspt`、`console`。彩色启动面板可按终端宽度自动切换紧凑/完整布局；健康状态包含运行时间、堆内存、玩家数、世界数、TPS 与 MSPT；远程操作在 Loader 权限 API 可用时提供独立的只读与管理权限节点，并明确回退到 OP 2/4。配置写入带保护，支持重载和校验，更新检查不会阻塞服务器主线程。

## 📦 兼容版本与下载

- Minecraft：`26.1`、`26.1.1`、`26.1.2`、`26.2`、`26.3`
- Loader：Fabric、NeoForge
- Java：`25` 或更高版本
- 环境：专用服务端

⚠️ **请下载同时匹配 Minecraft 版本和 Loader 的 JAR。** 每个版本都经过独立构建与测试，不保证跨版本二进制兼容。

## 🚨 反矿透是独立模组

从 `Meow Console 1.3.0` 开始，本项目专注控制台与服务端运维，**不再内置反矿透**。

需要反矿透保护？请将 **MeowAnti-Xray** 与 Meow Console 一起安装：

👉 https://modrinth.com/mod/meowanti-xray

两个模组刻意分开维护，你可以按服务器实际需求选择安装。

## 🔗 链接

- 源码与反馈：https://github.com/xiaoyiluck666/meowconsole
- 问题反馈：https://github.com/xiaoyiluck666/meowconsole/issues
