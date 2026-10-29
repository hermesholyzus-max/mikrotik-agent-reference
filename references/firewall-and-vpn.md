# Firewall, NAT, and VPN Inspection

## Passive inventory

```routeros
/ip firewall filter print detail
/ip firewall nat print detail
/ip firewall mangle print detail
/ip firewall connection tracking print
/ip ipsec peer print detail
/ip ipsec active-peers print detail
/interface wireguard print detail
/interface wireguard peers print detail
```

Commands and menus differ by version, installed package, license, hardware, and configured services. An unavailable menu may be a version/capability distinction; do not enable or install anything to inspect it.

## Agent review model

For a reported flow, distinguish management/input traffic, traffic through the router, and locally originated traffic. Record relevant rule order, matching conditions, interface lists, address lists, connection state/marks, NAT position, route, and tunnel state. Do not disclose peer endpoints, keys, PSKs, identities, or sensitive comments in reports.

## v6 / v7 note

Do not assume modern VPN features or the exact v7 routing relationship exist on RouterOS v6. WireGuard, for example, requires RouterOS v7-era support; verify the installed version and official feature documentation rather than offering it as a v6 remedy.

## Safety

Firewall/NAT/VPN changes can expose management services, break established traffic, or strand remote access. No rule reorder, disable/enable action, NAT edit, key generation, peer edit, or service exposure is allowed without explicit approval and a rollback/recovery path.

## Official sources

- [Connection Tracking](https://help.mikrotik.com/docs/spaces/ROS/pages/130220087/Connection%2Btracking)
- [WireGuard](https://help.mikrotik.com/docs/spaces/ROS/pages/69664792/WireGuard)
- [Bridging and Switching — bridge firewall scope](https://help.mikrotik.com/docs/spaces/ROS/pages/328068/Bridging%2Band%2BSwitching)
- [Current RouterOS documentation portal](https://manual.mikrotik.com/docs/introduction/)
