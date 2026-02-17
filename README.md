# 🌐 IPLoop Node Agent

**Earn proxy credits by sharing your unused bandwidth.**

[![Docker Hub](https://img.shields.io/docker/pulls/ultronloop2026/iploop-node)](https://hub.docker.com/r/ultronloop2026/iploop-node)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## Quick Start

```bash
docker run -d --name iploop-node --restart=always ultronloop2026/iploop-node:latest
```

That's it. You're now earning proxy credits.

## What It Does

- Shares your idle bandwidth through IPLoop's residential proxy network
- Earns credits: up to **2.4 GB/day** at Gold tier (see [REWARDS.md](REWARDS.md))
- Uses < 50MB RAM, near-zero CPU
- Auto-reconnects on network issues
- Works on Linux, macOS, Windows, Raspberry Pi

## Docker Compose

```yaml
version: '3'
services:
  iploop-node:
    image: ultronloop2026/iploop-node:latest
    container_name: iploop-node
    restart: always
```

## Check Your Credits

```bash
docker logs iploop-node | head -5  # Get your token
curl "https://gateway.iploop.io:9443/api/credits?token=YOUR_TOKEN"
```

## Use Your Credits as Proxy

```bash
curl -x "http://user:YOUR_API_KEY@gateway.iploop.io:8880" https://httpbin.org/ip
curl -x "http://user:YOUR_API_KEY-country-US@gateway.iploop.io:8880" https://example.com
```

## Standalone Binaries

Don't want Docker? Download from [Releases](https://github.com/iploop/iploop-node/releases).

| Platform | Binary |
|----------|--------|
| Linux amd64 | `iploop-node-linux-amd64` |
| Linux arm64 | `iploop-node-linux-arm64` |
| macOS Intel | `iploop-node-darwin-amd64` |
| macOS ARM | `iploop-node-darwin-arm64` |
| Windows x64 | `iploop-node-windows-amd64.exe` |
| Linux armv7 | `iploop-node-linux-armv7` |

## Network Stats

- **2,000,000+** residential IPs
- **19,000+** nodes online
- **50+** countries
- **Device types:** Android, Windows, Mac, Smart TV

## Links

- [Dashboard](https://iploop.io)
- [Docker Hub](https://hub.docker.com/r/ultronloop2026/iploop-node)
- [ProxyClaw Skill](https://github.com/iploop/proxyclaw)

## License

MIT — see [LICENSE](LICENSE)
