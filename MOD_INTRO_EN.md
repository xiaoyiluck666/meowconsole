# 🐾 Meow Console

**A focused server-side operations toolkit for Fabric and NeoForge.**

Keep your console readable, your server health visible, and routine admin work fast. Meow Console is built for dedicated-server owners who want practical tools without installing anything on players' clients.

[![Modrinth Download](https://img.shields.io/badge/Modrinth-Download-1bd96a?style=flat-square&logo=modrinth&logoColor=white)](https://modrinth.com/mod/meowconsole) [![GitHub Wiki](https://img.shields.io/badge/GitHub-Wiki-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/xiaoyiluck666/meowconsole/wiki) [![GitHub Source](https://img.shields.io/badge/GitHub-Source-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/xiaoyiluck666/meowconsole) [![Submit Issue](https://img.shields.io/badge/GitHub-Submit%20Issue-d73a4a?style=flat-square&logo=github&logoColor=white)](https://github.com/xiaoyiluck666/meowconsole/issues/new/choose)

💖 **Support development:** [PayPal](https://www.paypal.com/paypalme/neworldcn) · [Afdian](https://afdian.com/a/xiaoyiluck)

## ✨ What makes it useful?

- 🖥️ **Console clarity**: Paper-like colorful output, terminal-width-aware dashboards, local command completion, persistent history, and safe console log filtering.
- 📊 **Fast diagnostics**: Health status, TPS/MSPT, paged entity counts, mod lists, alerts, and update checks in one place.
- 👋 **Player experience tools**: Custom join/leave messages, threshold-based night skipping, and flight guard utilities.
- 🔌 **Hosting compatibility**: Velocity / FabricProxy-Lite helpers plus MCDR and common panel-host support for stdout and vanilla console input.
- 🛠️ **Remote administration**: Cross-loader administrator/RCON commands including `status`, `health`, `alerts`, `tps`, `mspt`, `mods`, `entities`, `console`, `reload`, and `update`, with native permission nodes when the loader API provides them and vanilla operator-level fallbacks.
- 🧩 **Server-side only**: Made for dedicated servers, proxy networks, and long-running survival servers; clients do not need the mod.

## 🧭 Included tools

The local console includes `health`, `alerts`, `entities`, `messages`, `mcdr`, `sleep`, `flight`, `velocity`, `mods`, `tps`, `mspt`, and `console`. The colorful startup dashboard automatically switches between compact and full layouts based on terminal width. Health output covers uptime, heap use, players, worlds, TPS, and MSPT. Remote operations have separate read-only and administrative permission nodes where the loader API supports them, with clear OP 2/4 fallbacks. Guarded configuration writes, validation, reload support, and non-blocking update checks make routine maintenance safer and less disruptive.

## 📦 Compatibility and downloads

- Minecraft: `26.1`, `26.1.1`, `26.1.2`, `26.2`, and `26.3`
- Loaders: Fabric and NeoForge
- Java: `25` or newer
- Environment: dedicated server

⚠️ **Choose the JAR that matches both your Minecraft version and loader.** These builds are tested separately; cross-version binary compatibility is not assumed.

## 🚨 Anti-Xray is a separate mod

Since `Meow Console 1.3.0`, this project focuses on console and server operations and **does not include anti-xray**.

Need anti-xray protection? Install **MeowAnti-Xray** alongside Meow Console:

👉 https://modrinth.com/mod/meowanti-xray

The two mods are intentionally separate, so you can install exactly the server features you need.

## 🔗 Links

- Source and feedback: https://github.com/xiaoyiluck666/meowconsole
- Issues: https://github.com/xiaoyiluck666/meowconsole/issues
