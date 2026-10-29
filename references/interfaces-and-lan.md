# Interfaces, Bridge, VLAN, and LAN Inspection

## Passive inventory

```routeros
/interface print detail
/interface bridge print detail
/interface bridge port print detail
/interface vlan print detail
/interface list print detail
/interface list member print detail
/ip address print detail
/ip dhcp-server print detail
/ip dhcp-client print detail
```

Read the actual interface names and bridge membership; do not assume an `ether1`, `bridge`, WAN, or LAN convention. Treat dynamic records separately from intended static configuration.

## Agent checks before a LAN change

- Identify the current management interface/IP and the path used to reach it.
- Determine whether the traffic is routed, bridged, VLAN-tagged, hardware-offloaded, or a mixture.
- Inspect bridge ports, VLAN interface attachment, bridge VLAN settings, and firewall/interface-list dependencies together.
- Confirm switch-chip or wireless limitations from the exact model documentation before changing bridge/VLAN behavior.

## Safety notes

- A bridge/firewall rule can affect only bridged traffic while routed traffic follows IP firewall processing; do not assume one rule set covers both.
- Do not toggle bridge VLAN filtering, change PVID/tagging, move a management port, or alter DHCP without a tested recovery path.
- Passive inspection is not proof that clients can pass traffic. Client-side validation must be separately approved and performed from the applicable path.

## Official sources

- [Bridging and Switching](https://help.mikrotik.com/docs/spaces/ROS/pages/328068/Bridging%2Band%2BSwitching)
- [Interface Lists](https://help.mikrotik.com/docs/spaces/ROS/pages/47579180/Interface%2BLists)
- [Current RouterOS documentation portal](https://manual.mikrotik.com/docs/introduction/)
