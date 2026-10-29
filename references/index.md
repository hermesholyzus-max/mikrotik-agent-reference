# RouterOS Reference Index

## Source policy

Use current official documentation first: <https://manual.mikrotik.com/docs/introduction/>. The official `help.mikrotik.com` RouterOS archive remains useful for pages that redirect readers to the current portal; it is marked frozen on relevant pages. This package does not reproduce the manuals.

## Topic map

| Topic | Local file | Primary official sources |
|---|---|---|
| Version, preflight, rollback | [version-and-safety.md](version-and-safety.md) | [Configuration Management](https://help.mikrotik.com/docs/spaces/ROS/pages/328155/Configuration%2BManagement), [Backup](https://help.mikrotik.com/docs/spaces/ROS/pages/40992852/Backup) |
| Interfaces, bridge, VLAN, addresses | [interfaces-and-lan.md](interfaces-and-lan.md) | [Bridging and Switching](https://help.mikrotik.com/docs/spaces/ROS/pages/328068/Bridging%2Band%2BSwitching), [Interface Lists](https://help.mikrotik.com/docs/spaces/ROS/pages/47579180/Interface%2BLists) |
| Route inspection and policy | [routing.md](routing.md) | [Route Selection and Filters](https://help.mikrotik.com/docs/spaces/ROS/pages/74678285/Route%2BSelection%2Band%2BFilters), [/routing/route](https://help.mikrotik.com/docs/spaces/ROS/pages/59965493/routing%2Broute) |
| Firewall, NAT, VPN | [firewall-and-vpn.md](firewall-and-vpn.md) | [Connection Tracking](https://help.mikrotik.com/docs/spaces/ROS/pages/130220087/Connection%2Btracking), [WireGuard](https://help.mikrotik.com/docs/spaces/ROS/pages/69664792/WireGuard) |
| Passive diagnostics and APIs | [diagnostics.md](diagnostics.md) | [REST API](https://help.mikrotik.com/docs/spaces/ROS/pages/47579162/REST%2BAPI), [Files](https://help.mikrotik.com/docs/spaces/ROS/pages/2555971/Files) |

## Version rule

Confirm `/system resource print` and `/system package print` before selecting commands. RouterOS v6 and v7 are distinct configuration targets; do not migrate or paste routing/filter examples between them without reviewing the official version-specific documentation and the live device.

## Link validation record

On **2026-10-29**, all official URLs in this index returned HTTP 200 from this environment. The archive source may present content for a different page title than an assumed URL if page IDs are guessed; links here were selected by official search results and checked directly. Revalidate before using a time-sensitive feature or a new release.

## Search locally

```bash
rg -n -i 'safe mode|rollback|export' references/version-and-safety.md
rg -n -i 'bridge|vlan|interface list|address' references/interfaces-and-lan.md
rg -n -i 'v6|v7|route|filter|routing table' references/routing.md
rg -n -i 'firewall|nat|wireguard|ipsec' references/firewall-and-vpn.md
rg -n -i 'log|connection|monitor|rest' references/diagnostics.md
```
