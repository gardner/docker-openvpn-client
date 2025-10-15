# AGENTS.md

This file provides guidance to agents when working with code in this repository.

## Build Commands
- To build the Docker image: `docker build -t ghcr.io/gardner/openvpn-client https://github.com/wfg/docker-openvpn-client.git#:build`
- To build locally: `docker build -t openvpn-client ./build`

## Project Specifics
- Uses Alpine 3.22 as base image
- Entry point is `entry.sh` which must be in `/usr/local/bin`
- Kill switch functionality implemented with `iptables` in `killswitch.sh`
- Configuration files must be mounted to `/config` volume
- OpenVPN config files must have .conf or .ovpn extension

## Critical Environment Variables
- `KILL_SWITCH=on` by default (set to any truthy value to enable)
- `CONFIG_FILE` - specific config file or pattern to use
- `ALLOWED_SUBNETS` - comma-separated subnets to allow outside VPN
- `AUTH_SECRET` - Docker secret containing VPN credentials

## Code Style
- Bash strict mode (`set -o errexit`, `set -o nounset`, `set -o pipefail`)
- Functions should handle cleanup signals properly
- Use parameter expansion with defaults
- Scripts must work with both IPv4 and IPv6