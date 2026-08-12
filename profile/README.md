<p align="center">
  <img src="profile/basalt-logo.png" alt="Basalt" width="360">
</p>

<h2 align="center">Basalt</h2>

<p align="center">
  <strong>Minecraft server software rewritten from scratch in Kotlin/Native. No JVM.</strong>
</p>

<p align="center">
  <img alt="Minecraft" src="https://img.shields.io/badge/Minecraft-26.2-62B47A?logo=minecraft&logoColor=white">
  <img alt="Kotlin" src="https://img.shields.io/badge/Kotlin%2FNative-2.4.10-7F52FF?logo=kotlin&logoColor=white">
  <img alt="License" src="https://img.shields.io/badge/license-GPL--3.0-green">
  <img alt="Website" src="https://img.shields.io/badge/basaltmc.org-62B47A">
</p>

Basalt is a complete reimplementation of Minecraft: Java Edition server software,
written entirely in Kotlin/Native and shipped as native binaries. There is no JVM
anywhere in the runtime: no bundled JRE, no embedded VM, no hidden Java process.

Two rules decide everything else:

- **Vanilla parity.** A Basalt server with no plugins behaves exactly like the
  official one. Same seed, same world. Same drops, same damage, same redstone,
  bugs included. Parity is the acceptance criterion for every system, not a
  long-term aspiration.
- **No JVM, no exceptions.** Not for a feature, not for compatibility, not for
  convenience. Where a Java library would normally be reached for, the
  functionality is written instead.

## Repositories

| | |
|---|---|
| [**Server**](https://github.com/BasaltProject/Server) | The Minecraft server: worlds, entities, gameplay, and the BSMod plugin API |
| [**Proxy**](https://github.com/BasaltProject/Proxy) | The proxy: one address in front of many servers, and it works with any of them, Basalt or not |
| [**Wire**](https://github.com/BasaltProject/Wire) | The network layer both of them build on. One implementation of the protocol, not two |
| [**Website**](https://github.com/BasaltProject/Website) | The project site, at [basaltmc.org](https://basaltmc.org) |

## Status

**Early development.** Nothing here is ready to run a server anyone depends on.
The server accepts real clients, generates worlds and streams chunks; the proxy
has just been started. Each repository keeps an honest status table in its own
README, and none of them rounds up.

## Plugins

Plugins are written in Lua and packaged as single files: `.bsmod` for the server,
`.bpmod` for the proxy. They run sandboxed with an instruction budget, so a
broken plugin cannot take a server down, and the same runtime ships everywhere
Basalt runs with no native Lua dependency to install.

## License

Basalt is distributed under the GNU General Public License v3.0.

Basalt is not affiliated with Mojang Studios or Microsoft. Minecraft is a
trademark of Mojang Studios.
