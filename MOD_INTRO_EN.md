# MeowConsole Mod Introduction

`MeowConsole` is a server-side enhancement mod built for **Fabric 26.1 + Java 25**.  
It brings a Paper-like experience to Fabric servers: a better console, practical anti-xray, and strong performance under real gameplay load.

---

## Why Choose MeowConsole

### 1. Better Console, Better Operations

- Terminal command highlighting
- `Tab` completion support (vanilla commands + local commands)
- Built-in local commands: `mods`, `antixray status/reload/profile/debug`, `tps`, `mspt`, `entities <world> [keyword]`
- Entity-stat aliases: `entitycount`, `mobs`
- Earlier console takeover during server startup, so the terminal becomes usable sooner
- Clear startup logs for quick operational checks, including config source visibility

### 2. Practical Anti-Xray for Real Servers

- Obfuscation is applied before chunk packet delivery
- Per-dimension anti-xray configuration (Overworld / Nether / End)
- Reveal behavior with controlled update radius
- Engine-mode-2 oriented optimization for both protection and performance
- Fixes the visual mismatch where the mined target block did not reveal immediately
- Fixes one class of stale fake-ore visuals after breaking nearby cover blocks
- Adds `antixray debug` for direct block-state troubleshooting

### 3. Proven Performance Improvements

This mod has been optimized through repeated Spark profiling in high-throughput scenarios (fast movement and heavy chunk streaming), including:

- replacing per-block update spam with section-batched updates
- using fast nearby-section exposure checks
- skipping sections that cannot contain target blocks
- reducing unnecessary tick-time scans

The result is a significantly lower anti-xray overhead compared to early versions.

---

## Who Is It For

- Server owners who want Fabric ecosystem + Paper-like admin experience
- Servers that need anti-xray with controllable performance impact
- Operators who value a more productive terminal workflow

---

## Core Commands

```bash
mods
mods user|all|loaded|unloaded|system [keyword]
antixray status
antixray reload
antixray profile
antixray debug <world> <x> <y> <z>
tps
mspt
entities <world> [keyword]
entitycount <world> [keyword]
mobs <world> [keyword]
```

---

## Configuration Behavior

- Config path: `config/meowconsole-paper.yml`
- Full config is generated on first run
- Missing keys are supplemented in place on load/reload without rewriting the whole existing file
- Default `max-block-height` is `64`
- `antixray status` / `antixray reload` show config source and active summary
- Config read failures now log a clear warning before falling back to defaults

---

## One-Line Summary

**MeowConsole = Paper-like console experience + production-grade anti-xray optimization for Fabric servers.**

---

## Repository & Issues

- Repository: `https://github.com/xiaoyiluck666/meowconsole`
- Issues: `https://github.com/xiaoyiluck666/meowconsole/issues`

---

## Author

- `xiaoyiluck`

