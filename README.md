# Rocky Linux Xray Deployment

Deploy an Xray client on Rocky Linux using Docker Compose.

## Features

- Docker Compose deployment
- VLESS over WebSocket example configuration
- SOCKS, HTTP, and transparent TCP inbounds
- Separate example configuration with placeholders
- Firewall setup documented separately

## Requirements

- Rocky Linux 9 or compatible distribution
- Docker Engine
- Docker Compose plugin
- Root or sudo privileges

## Quick Start

1. Clone this repository.
2. Copy the example configuration:

   ```bash
   cp config.example.json config.json
   ```

3. Edit `config.json` and replace all placeholder values with your own VLESS server details.
4. Validate the JSON with `python3 -m json.tool config.json`.
5. Start Xray with `docker compose up -d`.
6. Check logs with `docker logs --tail 100 v2ray-client`.

## Security

- Never commit your real `config.json`, UUIDs, server credentials, private keys, or backups.
- Replace all placeholders before deployment.
- Review firewall rules and network exposure before deployment.
- SOCKS and HTTP example listeners bind to localhost by default.
- Transparent proxying requires additional host firewall configuration and careful testing.

## Firewall

Firewall rules are system-specific and are not applied automatically. Review interfaces, routes, exclusions, and the firewall backend before enabling rules.

## Disclaimer

Use this project only on systems and networks you are authorized to administer.
