# Project Documentation Rules (Non-Obvious Only)

- Configuration files must be mounted to `/config` volume with appropriate file permissions
- OpenVPN configuration files must have .conf or .ovpn extension to be detected
- The kill switch is enabled by default but can be disabled by setting `KILL_SWITCH` to a falsy value
- Authentication credentials can be provided via Docker secrets using `AUTH_SECRET` variable
- Network connectivity for other containers is achieved by using `network_mode: service:openvpn-client` in compose files
- The project is archived in favor of a WireGuard version, as noted in README.md