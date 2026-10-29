# Routing and Policy Inspection

## Passive routing inventory

```routeros
/ip route print detail
/routing route print detail
/routing table print detail
/routing rule print detail
```

Availability and output vary by RouterOS major version, enabled packages, and permissions. Start with the commands that exist; do not create routing tables/rules merely to make a query possible.

## Interpret before proposing a change

For an affected destination, identify the selected route, candidate routes, gateway reachability/immediate gateway, distance, scope/target scope, routing table/VRF, and any routing rule or filter that can alter selection. Also inspect interface/address state and firewall/NAT only where they are part of the observed path.

## v6 / v7 distinction

- RouterOS **v7** substantially changed routing internals and routing-filter syntax. Its official documentation specifically warns that v6 AS-path regexp patterns are not directly portable to v7.
- Do not reuse v6 BGP/filter examples in v7, or reverse, without conversion and a staged verification plan.
- For a feature introduced in a later v7 release, verify exact release availability; “v7” alone is insufficient.

## Safety

Route, rule, filter, VRF, BGP, and OSPF changes can remove management reachability or alter traffic beyond the target prefix. Require explicit approval, an out-of-band recovery plan, a narrow scope, read-back, and a path-specific validation. A router-originated test does not prove client forwarding.

## Official sources

- [Route Selection and Filters](https://help.mikrotik.com/docs/spaces/ROS/pages/74678285/Route%2BSelection%2Band%2BFilters)
- [/routing/route reference](https://help.mikrotik.com/docs/spaces/ROS/pages/59965493/routing%2Broute)
- [Current RouterOS documentation portal](https://manual.mikrotik.com/docs/introduction/)
