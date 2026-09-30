# Meow Console

Meow Console is a server-side Minecraft mod for Fabric and NeoForge, focused on a cleaner console experience and practical server-management utilities.

Starting with Meow Console 1.3.0 and continuing in later versions, anti-xray is no longer bundled here. It is maintained as the standalone `MeowAnti-Xray` mod instead.

## Compatibility

- Minecraft `26.1`, `26.1.1`, `26.1.2`, `26.2`, and `26.3`.
- Fabric and NeoForge dedicated servers.
- Java `25` or newer.
- Use the JAR whose Minecraft version and loader match the server. Cross-version binary compatibility is not assumed.

## Features

- Paper-like colorful interactive console with local command completion and terminal-width-aware compact/full dashboards.
- Persistent local command history with duplicate reduction and a configurable entry limit.
- Safe console-only log filtering by text or regular expression; disk logs and error events remain visible.
- Multiplayer sleep acceleration and night-skip utilities.
- Custom join/leave message handling.
- Flight guard utilities.
- Velocity / FabricProxy-Lite helper configuration.
- MCDR compatibility options for stdout and vanilla console input preservation.
- Startup dashboard, alerts, update checks, TPS/MSPT snapshots, and mod list helpers.
- Local console utility commands such as `health`, `alerts`, `entities`, `messages`, `mcdr`, `sleep`, `flight`, `velocity`, `mods`, `tps`, and `mspt`.
- Cross-loader administrator/RCON commands: `/meowconsole status`, `health`, `alerts`, `tps`, `mspt`, `mods`, `entities`, `console`, `reload`, and `update`.

## Console Configuration

Interactive console settings live in the `console:` section of `config/meowconsole-features.yml`:

```yaml
console:
  history-enabled: true
  history-max-entries: 500
  layout-mode: auto
  compact-width-threshold: 100
  log-filter-enabled: false
  log-filter-include-warnings: false
  log-filter-contains: []
  log-filter-regex: []
  health-warn-tps: 18.0
  health-warn-mspt: 45.0
```

`layout-mode` accepts `auto`, `compact`, or `full`. Auto mode selects the compact startup dashboard below the configured terminal width and reports the effective layout in `console status`.

Log filters only suppress matching lines in the interactive terminal. They never remove entries from `latest.log`, and `ERROR`/`FATAL` events are always shown. Prefix a local command with a space to keep it out of persistent history.

Use `entities <world> [filter] [page]` locally or `/meowconsole entities <world> [filter] [page]` through RCON to inspect loaded entity counts without a profiler.

Use `console reload` locally or `/meowconsole console reload` remotely to reload these settings. History file changes take effect after a server restart. Use `console validate` or `/meowconsole console validate` to report invalid regular expressions, values, and unknown console keys.

Remote commands expose native Fabric Permission API v1 nodes when that Fabric API module is available, and native NeoForge Permission API nodes. Fabric uses the `meowconsole:command.*` namespace and NeoForge uses `meowconsole.command.*`. Available suffixes are:

- `status`, `health`, `alerts`, `tps`, `mspt`, `mods`, and `entities`
- `console.status`, `console.validate`, and `console.reload`
- `reload` and `update`

Permission providers may override each operation independently. Older Fabric API versions without the v1 permission module use the same vanilla fallback directly. Read-only diagnostics fall back to command permission level 2; configuration reloads and manual update checks fall back to level 4. `/meowconsole status` reports the active permission backend.

## Build

```powershell
.\gradlew.bat buildAllLoaders
```

Fabric only:

```powershell
.\gradlew.bat build
```

NeoForge only:

```powershell
.\gradlew.bat :neoforge:build
```

Build and test every supported Minecraft/loader combination:

```powershell
.\scripts\build_supported_versions.ps1
```

Versioned release JARs and `SHA256SUMS.txt` are written to `dist\supported-versions`.
The shared version matrix is maintained in `gradle/supported_versions.json` and is also used by GitHub Actions.

Publish the complete verified matrix to Modrinth (requires a `MODRINTH_TOKEN` with version-create access):

```powershell
.\scripts\publish_modrinth_versions.ps1
```

The publisher creates one listed release for each Minecraft version and loader, and skips versions already present on the project.

## Anti-Xray Split

Meow Console 1.3.0 and later versions do not include anti-xray features. If your server still needs anti-xray protection, install the standalone `MeowAnti-Xray` mod alongside Meow Console.

Standalone anti-xray download: https://modrinth.com/mod/meowanti-xray

## Support Development

- PayPal: https://www.paypal.com/paypalme/neworldcn
- Afdian: https://afdian.com/a/xiaoyiluck

## Changelog

See [docs/release/20260930170000000_v1.5.0_更新日志.md](docs/release/20260930170000000_v1.5.0_更新日志.md) for release notes.
