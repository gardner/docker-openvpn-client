# Project Coding Rules (Non-Obvious Only)

- All scripts must use bash strict mode (`set -o errexit`, `set -o nounset`, `set -o pipefail`)
- The `is_enabled()` function in `entry.sh` is a custom utility for checking truthy environment variable values
- The killswitch script in `build/killswitch.sh` implements custom iptables rules for VPN security
- OpenVPN configuration files must have .conf or .ovpn extension to be detected by entry.sh
- All scripts should handle cleanup signals properly through trap commands
- Network management in killswitch.sh specifically handles eth0 interface for routing