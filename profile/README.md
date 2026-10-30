<p align="center">
  <a href="https://raw.githubusercontent.com/BasaltProject/.github/main/assets/basalt-logo-white.svg#gh-dark-mode-only">
    <img src="https://raw.githubusercontent.com/BasaltProject/.github/main/assets/basalt-logo-white.svg" alt="Basalt" width="360">
  </a>
  <a href="https://raw.githubusercontent.com/BasaltProject/.github/main/assets/basalt-logo-black.svg#gh-light-mode-only">
    <img src="https://raw.githubusercontent.com/BasaltProject/.github/main/assets/basalt-logo-black.svg" alt="Basalt" width="360">
  </a>
</p>

<h2 align="center">Basalt</h2>

<p align="center">
  <strong>Minecraft server software rewritten from scratch in C++23. No JVM.</strong>
</p>

<p align="center">
  <img alt="Minecraft" src="https://img.shields.io/badge/Minecraft-26.3-62B47A?logo=minecraft&logoColor=white">
  <img alt="C++" src="https://img.shields.io/badge/C%2B%2B-23-00599C?logo=cplusplus&logoColor=white">
  <img alt="License" src="https://img.shields.io/badge/license-GPL--3.0-green">
  <img alt="Website" src="https://img.shields.io/badge/basaltmc.org-62B47A">
</p>

Basalt is a complete reimplementation of Minecraft: Java Edition server software,
written entirely in C++23 and shipped as native binaries. The core needs no JVM
installed on the host. Bukkit, Spigot and Paper plugins run through
[Shim](https://github.com/BasaltProject/Shim), a JVM in C++ that is built into the
binary and only starts when a Java plugin is present.

Two rules decide everything else:

- **Vanilla parity.** A Basalt server with no plugins behaves exactly like the
  official one. Same seed, same world. Same drops, same damage, same redstone,
  bugs included. Parity is the acceptance criterion for every system, not a
  long-term aspiration.
- **No external JVM.** Not for a feature, not for compatibility, not for
  convenience. Where a Java library would normally be reached for, the
  functionality is written instead.

## Repositories

| | |
|---|---|
| [**Server**](https://github.com/BasaltProject/Server) | The Minecraft server: worlds, entities, gameplay, Lua plugins, Bukkit plugins through Shim, and a REST/WebSocket management API |
| [**Proxy**](https://github.com/BasaltProject/Proxy) | The proxy: one address in front of many servers, and it works with any of them, Basalt or not |
| [**Wire**](https://github.com/BasaltProject/Wire) | The network layer both of them build on. One implementation of the protocol, not two |
| [**Shim**](https://github.com/BasaltProject/Shim) | A lightweight, embeddable JVM in C++ targeting modern Java LTS releases, forked from Avian |
| [**Kiln**](https://github.com/BasaltProject/Kiln) | Compiler and verifier for Lua plugins |
| [**DevTools**](https://github.com/BasaltProject/DevTools) | Editor extensions and API autocompletion for plugin authors |
| [**Metamorph**](https://github.com/BasaltProject/Metamorph) | World conversion between Anvil and Linear, and upgrades from older versions |
| [**Quarry**](https://github.com/BasaltProject/Quarry) | Extracts the data Basalt needs from the official server jar |
| [**Swarm**](https://github.com/BasaltProject/Swarm) | Bot swarm and stress testing for Minecraft servers |
| [**ServerPlugin-Example**](https://github.com/BasaltProject/ServerPlugin-Example) | A reference plugin for the Server plugin API |
| [**Website**](https://github.com/BasaltProject/Website) | The project site, at [basaltmc.org](https://basaltmc.org) |

## Status

**Early development.** Most of vanilla's gameplay is in place in the server and
Java plugins run, but some systems are still incomplete and little of it has seen
long-term use, so back up your worlds before trusting it with a public server.
Older Java clients and Bedrock clients are served through translation layers that
are still maturing. The proxy relays real connections and switches servers, but
has only been exercised on Linux with bots. Shim modernizes its VM core toward
Java 25 LTS. Each repository keeps an honest status in its own README, and none
of them rounds up.

## Plugins

Native plugins are written in Lua and packaged as single files: `.bspkg` for the
server, `.bppkg` for the proxy. They run sandboxed with an instruction budget, so
a broken plugin cannot take a server down, and the same runtime ships everywhere
Basalt runs: the official Lua, built into the binary, with nothing to install
alongside it. Kiln and DevTools cover building and writing them. The server also
runs Bukkit, Spigot and Paper plugins through Shim.

## License

Basalt is distributed under the GNU General Public License v3.0 (Shim and Website
are MIT; see individual repositories).

Basalt is not affiliated with Mojang Studios or Microsoft. Minecraft is a
trademark of Mojang Studios.
