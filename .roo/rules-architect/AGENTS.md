# Project Architecture Rules (Non-Obvious Only)

- The container must be run with NET_ADMIN capability and access to /dev/net/tun device
- All OpenVPN configuration handling is done in entry.sh which is the single entrypoint
- Kill switch functionality is implemented as a separate script (killswitch.sh) that is called by OpenVPN
- The kill switch works by adding iptables rules that block all traffic except through tun0 interface
- Only specific subnets can be allowed outside the VPN tunnel using ALLOWED_SUBNETS environment variable
- OpenVPN server addresses are automatically extracted from config files and allowed through firewall