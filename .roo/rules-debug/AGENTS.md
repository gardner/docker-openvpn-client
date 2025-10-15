# Project Debug Rules (Non-Obvious Only)

- No specific debugging setup exists for this project
- Debugging would be done through manual verification of Docker container behavior
- OpenVPN logs can be viewed with `docker logs openvpn-client`
- Network connectivity issues can be diagnosed by exec'ing into the container and using standard network tools
- Kill switch functionality can be verified by checking iptables rules with `iptables -L`